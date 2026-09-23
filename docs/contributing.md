# Contributing

Contributions that improve the accuracy, documentation, or usability of the published datasets are welcome.

## Reporting data issues

If you find a possible error in a geographic name, administrative classification, location, source cross-reference, or geometry, please open an issue describing:

- the affected feature or CoDPA code;
- the field or geometry that may be incorrect;
- the proposed correction;
- the source supporting the correction, when available.

Links to official documents, authoritative geographic databases, or other verifiable sources are particularly useful.

## Geographic names and administrative units

The administrative inventory, official names, codes, levels, and province–municipality relationships are based on the **Código de la División Político-Administrativa (CoDPA)**.

Corrections to these attributes should therefore be supported by an authoritative source rather than by spelling preference, proximity, or name similarity alone.

Records from GNS, GeoNames, Overture Maps, and other geographic databases are used as source cross-references. A shared name does not by itself establish that two records represent the same geographic feature.

## Geometry

Geometry issues may include incorrect boundaries, missing areas, invalid geometry, or incorrect links between geometry and geographic-name records.

When possible, reports should identify the affected administrative unit and provide the source or evidence used to identify the problem.

## Documentation and examples

Corrections and improvements to documentation and usage examples are also welcome.

Examples should use the published datasets and be reproducible from the repository without depending on unpublished local files.

## Development

Published datasets are generated through a separate development workflow rather than edited manually in this repository.

Changes to the data should therefore be reproducible and supported by source evidence. Accepted corrections are incorporated into the development workflow and included in a subsequent published dataset release.

For information about how the current datasets were produced, see [Data development](data_development.md).
