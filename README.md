# Cuba Geographic Data

![División político-administrativa de Cuba](administrative_map.png)

Open geographic datasets for Cuba, compiled from authoritative and openly available sources.

The project provides cleaned and documented geographic data in formats suitable for GIS, spatial analysis, and programmatic use.

[![DOI](https://zenodo.org/badge/1375041188.svg)](https://doi.org/10.5281/zenodo.22927747)

## Available data

### Administrative Geographic Names

Official geographic names of Cuban provinces, municipalities, and the special municipality of Isla de la Juventud, based on the **Codificador de la División Político-Administrativa (CoDPA)**, with point locations and cross-references to external geographic databases.

Available as:

- GeoParquet
- GeoJSON
- GeoPackage

[`data/administrative-geographic-names/`](data/administrative-geographic-names/)

### Administrative Geometry

Administrative polygons for Cuban provinces, municipalities, and the special municipality of Isla de la Juventud, identified by CoDPA codes and linked to the geographic names dataset.

Available as:

- GeoParquet
- GeoJSON
- GeoPackage

[`data/administrative-geometry/`](data/administrative-geometry/)

### Cuba Coastline

Line geometry of Cuba’s coastal boundary, derived from the exterior rings of the land polygons. Available as GeoParquet, GeoJSON, and GeoPackage under ODbL 1.0.

[`data/coastline/`](data/coastline/)

### Cuba Land Polygons

Polygon footprint covering land, islands, and inland water. Available as GeoParquet, GeoJSON, and GeoPackage under ODbL 1.0.

[`data/land-polygons/`](data/land-polygons/)

These two products are now present in the repository but are not included in the v1.0.0 release. Their release version and DOI will be assigned separately.

### Water Geographic Names

3,687 consolidated name objects with detailed feature types, preferred labels, recorded alternatives and source evidence. Available as Parquet, CSV and GeoPackage attribute tables.

[`data/water-geographic-names/`](data/water-geographic-names/)

### River and Channel Centerlines

56,594 modeled drainage centerline reaches with drainage topology, direct name-object references and naming status. Geographic uncertainty and withheld assignments are explicit columns. Available as GeoParquet, gzip-compressed GeoJSON and GeoPackage.

[`data/river-centerlines/`](data/river-centerlines/)

These additions are not part of v1.0.0; no new release or DOI has been assigned.

## Human-readable reference tables

[Administrative geographic names](reference/cuba_administrative_geographic_names.csv), [Water names](reference/cuba_water_names_reference.csv) and [ONEI river correspondence](reference/cuba_onei_river_correspondence.csv) include readable descriptions and project object IDs. See [reading guidance and limitations](reference/README.md).

## Additional hydrographic products

- [Water-body geometry](data/water-body-geometry/): 1,148 HydroLAKES polygons with direct name references. One source ring defect repaired without boundary displacement; detailed feature types remain in the name registry.
- [River catchments](data/river-catchments/): 56,594 reach-linked catchment polygons. The 979 source ring defects have been repaired without boundary displacement; beta-source limitations remain documented.
- [Supplementary water geometry](data/supplementary-water-geometry/): 372 valid source observations representing 370 source features outside reference coverage. Multiple observations of a source feature are retained; these are not consolidated reference-network objects.

These additions are not part of v1.0.0. No new release or DOI has been assigned. Metadata schema validation and remaining field-documentation improvements are still pending.

## Examples

The [`examples/`](examples/) directory contains Jupyter notebooks demonstrating how to explore, visualize, and use the published datasets.

## Documentation

- [Data development](docs/data_development.md)
- [References](docs/references.md)
- [Contributing](docs/contributing.md)

## Citation

- **Version 1.0.0:** [10.5281/zenodo.22927748](https://doi.org/10.5281/zenodo.22927748). Use this DOI when citing this release.
- **Project (all versions):** [10.5281/zenodo.22927747](https://doi.org/10.5281/zenodo.22927747). This concept DOI is also used by the badge above.

## License

Unless otherwise indicated, data in this repository are available under **CC BY 4.0**.

`cuba_administrative_geometry.*`, `cuba_coastline.*`, and `cuba_land_polygons.*`, `cuba_water_geographic_names.*`, `cuba_river_centerlines.*`, and the hydrography reference CSVs are available under the **Open Database License (ODbL) 1.0**.

See [LICENSE.md](LICENSE.md) for details.

## Support

This is an independent project. If you find it useful and would like to support the work behind it, you can [buy me a coffee](https://buymeacoffee.com/NotTheMapGuy).
