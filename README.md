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

`cuba_administrative_geometry.*` is available under the **Open Database License (ODbL) 1.0**.

See [LICENSE.md](LICENSE.md) for details.

## Support

This is an independent project. If you find it useful and would like to support the work behind it, you can [buy me a coffee](https://buymeacoffee.com/NotTheMapGuy).
