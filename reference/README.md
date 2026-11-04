# Human-readable reference tables

`cuba_administrative_geographic_names.csv`: all 183 administrative name objects (15 provinces, 167 municipalities and one special municipality), with the original columns, names, administrative levels, CoDPA codes, province context, coordinates and project/source IDs, moved unchanged from `dev/`. The `id` column links to [Administrative Geographic Names](../data/administrative-geographic-names/). Coordinates are the existing name-point locations in EPSG:4326. Blank province fields mean no parent province applies. Read CoDPA codes as text to preserve their formatting.

`cuba_water_names_reference.csv`: one row per name object, with accepted label, detailed
type, alternatives, sources, readable associations, geography and project UUID.
Associated names are distinguished from aliases of the object itself.

`cuba_onei_river_correspondence.csv`: one row per ONEI river, linked to a current
consolidated object. Matching uses recorded names and the province coverage of the
**complete connected river system**, then preferred-name agreement and physical
system length, stream order and drainage area. A name's locally assigned extent
does not determine province eligibility. All 39 entries have inferred matches;
these are not independently verified drainage-coast identities. Internal matching
diagnostics are retained in the workflow audit, not in this table.
`Watershed MAIN_BAS` references the matched object's system. Several named rivers
can share a watershed without becoming the same river object.

Province intersections and representative coordinates describe geometry under
the explicit Location basis in the names table; the ONEI table links final name objects to complete-system context. Representative points are display aids, not naming seeds. Length is
the sum of assigned reaches, including tributaries where applicable; it must not
be equated with ONEI main-channel length. IDs provide direct dataset lookup.

Alternative name object IDs and labels refer to distinct objects sharing assigned geometry, not aliases. The names dataset records the exact geometry scope for each reference.

## Dataset lookup

Use the Object ID to locate a record in [Water Geographic Names](../data/water-geographic-names/). Reach geometry is in [River and Channel Centerlines](../data/river-centerlines/). [Water-body geometry](../data/water-body-geometry/) is available in the repository. The water-name table covers the complete registry, including valid source-only names. ONEI associations remain inferred.

License and attribution: [per-table terms](LICENSE.md).



Name objects contain one Point location and a source reference for the preferred name only (`other` when none is documented). Alternative names are strings. River reaches and water-body polygons link directly through `gazetteer_id` to the name object’s `id`; system context and full observation evidence remain outside the name-object schema.
