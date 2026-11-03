# References

Sources for the published administrative datasets and the coastline and land-polygon products now in the repository. Bibliographic entries are formatted in APA 7 style. References identify the source resources; the source-identification notes document what is known about the actual extracts used. Development methods are described in [Data development](data_development.md).

## Source references

GeoNames. (2026, September 10). *GeoNames geographical database: Cuba daily extract* [Data set]. Retrieved September 10, 2026, from [GeoNames data downloads](https://download.geonames.org/export/dump/)

National Geospatial-Intelligence Agency. (n.d.). *Geographic Names Server* [Data set]. Retrieved September 10, 2026, from [Geographic Names Server](https://geonames.nga.mil/geonames/GNSHome/index.html)

Natural Earth. (2022, May 8). *Land* (Version 5.1.1) [Data set]. Retrieved September 10, 2026, from [1:10 million land polygons](https://www.naturalearthdata.com/downloads/10m-physical-vectors/10m-land/)

Oficina Nacional de Estadísticas. (2010, October 25). *Resolución No. 129/2010* [Resolution and annex: Codificador de la División Político-Administrativa (CoDPA)]. [Original document](https://onei.gob.cu/sites/default/files/servicios/2022-02/Resoluci%C3%B3n%20129.pdf)

Overture Maps Foundation. (2026, August 19). *Divisions* (Data release 2026-08-19.0; schema version [v1.18.0](https://github.com/OvertureMaps/schema/releases/tag/v1.18.0)) [Data set]. Retrieved September 11, 2026, from [Release notes](https://docs.overturemaps.org/blog/2026/08/19/release-notes/)

## Identification of the sources used

**CoDPA.** The source is *Resolución No. 129/2010* and its annex, *Codificador de la División Político-Administrativa (CoDPA)*, issued by the Oficina Nacional de Estadísticas on October 25, 2010. The resolution entered into effect on January 1, 2011.

**GNS.** The source is the Cuba country extract from the Geographic Names Server. The file was retrieved on September 10, 2026, as recorded by its retained download metadata. A snapshot or release date is not available.

**GeoNames.** The source is the Cuba country file, `CU.txt`, from the daily GeoNames extract of September 10, 2026. The file was retrieved on the same date.

**Natural Earth.** The source is the 1:10 million Land dataset, version 5.1.1, retrieved on September 10, 2026. The retained package identifies version 5.1.1 and dates it to May 8, 2022. The online Natural Earth changelog gives May 12, 2022 for the same version; the reference above follows the date recorded in the retained source package.

**Overture Maps.** The source is the `division` and `division_area` feature types from Overture Maps release `2026-08-19.0`, using schema `v1.18.0`. The local extract was created on September 11, 2026. Source metadata within the extracted features identifies an OpenStreetMap source version of July 23, 2026.

Retrieval dates refer to the retained source files or local extraction records and are expressed in the America/Los_Angeles time zone. `n.d.` is used where no publication or snapshot date could be established. No DOI is included unless one has been verified for the cited resource.


## Coastline and land-polygon source identification

**Project nonmarine classification.** Both products derive from the canonical H3 resolution-11 feature table. Cells classified as nonmarine are dissolved without coarsening into the land polygons, including inland water. The coastline consists of their exterior rings; it excludes interior rings. These products are not DEM elevation contours or surveyed shorelines.

**Overture ocean geometry.** The canonical table's retained schema metadata defines the marine flag using permanent-water classification and intersections with Overture water polygons (`subtype=ocean`, `is_salt=1`). Its recorded source is the project's retained `cuba_overture.gpkg`. The exact water-theme release date is not independently asserted here from the administrative Divisions citation. Credit: Overture Maps Foundation and OpenStreetMap contributors; see [Overture attribution](https://docs.overturemaps.org/attribution/) and [OpenStreetMap copyright](https://www.openstreetmap.org/copyright).

**Permanent-water processing.** The source workflow records NASADEM permanent-water inputs to the canonical classification. The retained boundary provenance does not establish a separate NASADEM granule/version citation, so none is invented here. Product metadata retains the available derivation record and limitations.

The coastline and land polygons carry ODbL 1.0 under the project's licensing decision. Product UUIDs and geometry coordinates are unchanged from the verified publication candidate. Neither product is identified by the v1.0.0 release DOI.
