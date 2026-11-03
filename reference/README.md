# Human-readable reference tables

`cuba_administrative_geographic_names.csv`: all 183 administrative name objects (15 provinces, 167 municipalities and one special municipality), with the original columns, names, administrative levels, CoDPA codes, province context, coordinates and project/source IDs, moved unchanged from `dev/`. The `id` column links to [Administrative Geographic Names](../data/administrative-geographic-names/). Coordinates are the existing name-point locations in EPSG:4326. Blank province fields mean no parent province applies. Read CoDPA codes as text to preserve their formatting.

`cuba_water_names_reference.csv`: one row per name object, with accepted label, detailed
type, alternatives, sources, readable associations, geography and project UUID.
Associated names are distinguished from aliases of the object itself.

`cuba_onei_river_correspondence.csv`: one row per ONEI river, linked to a current
consolidated object. Matching uses recorded names and assigned-geometry province
intersections, then preferred-name agreement, highest assigned Strahler order
and upstream drainage area. These are inferred correspondences, not independently
verified drainage-coast identities. Equal-ranking matches stay blank. Mani-Mani
has no matching consolidated name. Internal matching diagnostics are not included.
`Watershed MAIN_BAS` references the matched object's drainage system; several
ONEI rivers can share a watershed without becoming the same river object.

Province intersections and representative coordinates describe geometry under
the explicit Location basis in the names table; the ONEI table describes assigned river geometry. Representative points are display aids, not naming seeds. Length is
the sum of assigned reaches, including tributaries where applicable; it must not
be equated with ONEI main-channel length. IDs provide direct dataset lookup.

Alternative name object IDs and labels refer to distinct objects sharing assigned geometry, not aliases. The names dataset records the exact geometry scope for each reference.

## Dataset lookup

Use the Object ID to locate a record in [Water Geographic Names](../data/water-geographic-names/). Reach geometry is in [River and Channel Centerlines](../data/river-centerlines/). [Water-body geometry](../data/water-body-geometry/) is available in the repository. These tables cover the complete name registry; ONEI matching status is explicit; unresolved rows carry no selected object ID.

License and attribution: [per-table terms](LICENSE.md).
