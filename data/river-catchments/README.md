# Cuba River Catchments

[GeoParquet](cuba_river_catchments.parquet.gz) · [GeoJSON](cuba_river_catchments.geojson.gz) · [GeoPackage](cuba_river_catchments.gpkg.gz)

## Use

Use the field definitions to interpret identifiers, relationships and status values before analysis.

The GeoPackage table/layer is `cuba_river_catchments`. Alternative formats represent the same product.

## Documentation

- [Metadata](metadata.xml): description, coverage, lineage, limitations, license and source attribution. This is the authoritative product metadata.
- [Field definitions](fields.json): logical types, null semantics, units, controlled values and relationship targets.
- [Checksums](checksums.json): filenames, byte sizes and SHA-256 hashes for download verification.

Cross-product references identify related records; they do not require copying another product into this folder.

GeoJSON is losslessly gzip-compressed; decompress it for tools without gzip support.

This product is now present in the repository but is not part of the existing release. Metadata passes ISO 19115-3 XML Schema validation.

GeoPackage is also losslessly gzip-compressed; decompress it before opening in GIS software. GeoParquet is also gzip-compressed; decompress it before use.

All distributed geometries pass validity checks. Duplicate source identifiers and constant per-feature validity fields are omitted; the repair method, where applicable, remains recorded; original validity diagnostics stay in the internal audit.

Source `Shape_Length` and `Shape_Area` measurements are omitted; they remain available from the original HydroSHEDS dataset.

Files ending in `.gz` use lossless gzip compression. Decompress them before use in software that does not support the compressed distribution directly.

Repeated validity diagnostics and internal processing fields are omitted from the public table. Relevant derivation details are documented in metadata; retained repair methods and naming status remain explicit.
