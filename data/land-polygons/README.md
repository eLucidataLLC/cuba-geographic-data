# Cuba Land Polygons

[GeoParquet](cuba_land_polygons.parquet) · [GeoJSON](cuba_land_polygons.geojson) · [GeoPackage](cuba_land_polygons.gpkg)

## Use

Use the polygon geometry for area coverage or masking. The footprint includes inland water; do not interpret every included area as dry land. Its exterior rings are also available in the coastline product.

The GeoPackage table/layer is `cuba_land_polygons`. Alternative formats represent the same product.

## Documentation

- [Metadata](metadata.xml): description, coverage, lineage, limitations, license and source attribution. This is the authoritative product metadata.
- [Field definitions](fields.json): logical types, null semantics, units, controlled values and relationship targets.
- [Checksums](checksums.json): filenames, byte sizes and SHA-256 hashes for download verification.

Cross-product references identify related records; they do not require copying another product into this folder.

Repeated validity diagnostics and internal processing fields are omitted from the public table. Relevant derivation details are documented in metadata; retained repair methods and naming status remain explicit.
