# Cuba Water Geographic Names

Water name objects with an ID, preferred name, string-array alternatives, feature type, preferred-name source reference and one Point location in EPSG:4326.

**9,343 name objects.** Available as GeoParquet, GeoJSON and GeoPackage.

## Fields

- `id`: consolidated name object identifier.
- `preferred_name`: selected, type-complete label.
- `alternative_names`: an array of strings, such as `["name 1", "name 2"]`.
- `object_type`: detailed feature type.
- `source_observations`: source references supporting only the preferred name; `other` if none is documented.
- `geometry`: one Point in EPSG:4326.

Name identities, preferred labels, alternative strings and detailed types are preserved. Each object has one Point selected from observations supporting its preferred-name source. A recorded point takes precedence over a representative point derived from the original source line or polygon. Equivalent observations are selected deterministically by source feature/name identifiers and coordinates; points are never averaged. If the preferred name has no documented source, its source is other, with no invented source identifier, and an existing object location is selected. System scopes, alternative-object cross-references and source-location collections are not part of the public name schema. Detailed evidence and the recorded/derived point-selection method remain in the workflow audit. Physical water bodies and river reaches link directly through gazetteer_id; no reverse geometry references are stored on names.

A name Point is a location, not the geometry or extent of the river, lake or other named feature. Water-body polygons and river centerlines retain their own geometry and link to this list by `gazetteer_id` → `id`.

## License and metadata

**ODbL 1.0**, across all formats. Attribution, source lineage and limitations are in [metadata.xml](metadata.xml); definitions are in [fields.json](fields.json).

Readable reference: [water names](../../reference/cuba_water_names_reference.csv). [Example notebook](../../examples/water_geographic_names.ipynb).
