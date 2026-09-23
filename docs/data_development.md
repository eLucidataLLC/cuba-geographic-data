# Data development

The two published datasets share a CoDPA administrative inventory. **Administrative Geographic Names** provides names, source cross-references, and point locations. **Administrative Geometry** provides polygons for the same units and links each one to its geographic-name record.

## CoDPA backbone and source roles

The **Código de la División Político-Administrativa (CoDPA)** defines the administrative inventory: official names, codes, levels, and province–municipality relationships. Source matches enrich this inventory rather than replace its names or hierarchy.

GNS and GeoNames supply geographic-name records and administrative classifications. GNS also supplies the published point coordinates. Overture Maps supplies division identities, parent relationships, and administrative polygons. Natural Earth land geometry is used to clip province outlines and, during Overture extraction, the geometry of Isla de la Juventud.

## Cross-referencing administrative names

Source records are first brought into a common working table while retaining their original identifiers and attributes. The CoDPA cross-reference then selects administrative features using normalized names, compatible classifications, and parent-province checks. Name normalization handles accents, case, punctuation, and administrative prefixes; explicitly accepted equivalents cover differences such as “Lajas” and “Santa Isabel de las Lajas.” Published names remain those from CoDPA.

Ordinary provinces are matched to GNS/GeoNames `ADM1` features and Overture `region` divisions; ordinary municipalities use `ADM2` and `county`. Parent checks distinguish municipalities with the same name in different provinces. Natural Earth names are excluded from this administrative cross-reference because the reviewed candidates represented populated places rather than equivalent administrative units.

The resulting cross-reference records `gns_id`, `geonames_id`, and `overture_id` for each CoDPA entry. The names builder resolves the GNS identifier to its original coordinates and writes matching `lat`, `lon`, and Point geometry. Coordinates are not averaged or replaced by polygon centroids.

## Geometry construction

Geometry is selected through established Overture identifiers and CoDPA codes, without rematching polygon names.

- **Provinces:** the corresponding Overture division-area polygons are dissolved by CoDPA province and intersected with Natural Earth land geometry.
- **Ordinary municipalities:** the final builder groups the extracted Overture rows by `codpa_code` and applies `unary_union` to their geometries. This produces one geometry per unit; a single Polygon result is wrapped as a MultiPolygon.
- **Isla de la Juventud:** during extraction, every Overture geometry associated with `40.01` is intersected with the union of Natural Earth land polygons. The extraction script documents this as a correction for an erroneous rectangular component; it does not detect and delete a rectangle separately. The final builder consumes this corrected extraction and applies the same per-code union used for municipalities.

The final builder combines these geometries into a single product, represented as MultiPolygons in EPSG:4326. Because provinces and ordinary municipalities follow different construction paths, their outlines are not necessarily identical along the coast.

Isla de la Juventud remains one record, `40.01`, with level `special_municipality` and no parent province. It participates at both municipality and province levels when selecting units for a map; it is not duplicated in either product.

## Identity and the relationship between products

Each product has its own persistent UUIDv7 `id`. The names identifier belongs to the geographic-name record; the geometry identifier belongs to the administrative unit, independently of the polygon source. `overture_id` remains a source cross-reference.

The geometry product’s `gazetteer_id` points to `id` in the names product. This is the link used to obtain label text and point locations for a polygon. CoDPA codes connect the administrative inventory during construction, while the two products retain distinct identities.

On rebuild, each builder reuses previous UUIDv7 IDs by `codpa_code` and allocates an ID when none is available for that code. This includes a first build, missing previous products, or an older product without an ID column. Previous products must therefore be retained to preserve identity. Changed or reassigned codes need explicit review: the builders do not detect all such identity changes. The geometry builder stops if a required name ID is missing or a previous non-null `gazetteer_id` differs from the current name ID.

## Build and publication

Development takes place in a separate repository. The names product is built first from CoDPA and the resolved source cross-reference. The geometry product then combines the polygon inputs and links them to the names. The builders perform the following checks:

- **Names:** unique CoDPA codes and matching cross-reference coverage; unambiguous, resolved GNS coordinates; one-to-one GNS links; and Point geometry. Export read-back checks compare CoDPA codes and name IDs.
- **Geometry:** CoDPA coverage, Overture identifiers, administrative levels and parent relationships, and required gazetteer links. Polygon checks reject missing, empty, invalid, or non-polygon geometry and require a CRS. Export read-back checks compare CoDPA coverage and `id`, `overture_id`, and `gazetteer_id`, and recheck polygon validity.

This repository publishes the resulting datasets and usage examples. For record-level metadata, see the [names metadata](../data/administrative-geographic-names/metadata.xml) and [geometry metadata](../data/administrative-geometry/metadata.xml). Bibliographic details belong in [References](references.md), and usage terms in [LICENSE.md](../LICENSE.md).
