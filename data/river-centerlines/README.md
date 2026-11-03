# Cuba River and Channel Centerlines

Modeled river and channel drainage centerlines with drainage topology, direct name references and naming status. Flagged coastal extensions are project-derived. These lines do not represent surveyed channel boundaries or water-surface widths. Detailed feature types are retained in the referenced name objects.

[GeoParquet](cuba_river_centerlines.parquet) · [GeoJSON](cuba_river_centerlines.geojson.gz) · [GeoPackage](cuba_river_centerlines.gpkg.gz)

## Use

Use the field definitions to interpret identifiers, relationships and status values before analysis.

The GeoPackage table/layer is `cuba_river_centerlines`. Alternative formats represent the same product.

## Documentation

- [Metadata](metadata.xml): description, coverage, lineage, limitations, license and source attribution. This is the authoritative product metadata.
- [Field definitions](fields.json): logical types, null semantics, units, controlled values and relationship targets.
- [Checksums](checksums.json): filenames, byte sizes and SHA-256 hashes for download verification.

Cross-product references identify related records; they do not require copying another product into this folder.

The GeoJSON distribution uses lossless gzip compression; decompress it before opening in tools without gzip support.

## Human-readable reference tables

See [water names](../../reference/cuba_water_names_reference.csv) and [ONEI river correspondence](../../reference/cuba_onei_river_correspondence.csv), with [reading guidance](../../reference/README.md).

This repository addition is not part of the existing release. Detailed feature types are retained in the name registry. Water-body geometry and the referenced geometry IDs are available in `../water-body-geometry/`. Metadata passes ISO 19115-3 XML Schema validation.

All distributed geometries pass validity checks. Duplicate source identifiers and constant per-feature validity fields are omitted; original source validity and repair provenance, where applicable, remain recorded.
Preferred labels are obtained through `gazetteer_id` in the names dataset. `naming_status` retains applicability and uncertainty; alternative and contender references retain their distinct roles.

Files ending in `.gz` use lossless gzip compression. Decompress them before use in software that does not support the compressed distribution directly.
