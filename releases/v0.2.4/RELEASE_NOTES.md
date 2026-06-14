# GeoChem Explorer Release Notes

## Next Release

### Surface Samples

- Added first-class support for surface sample datasets such as soils, rock chips, grab samples, and other point geochemistry.
- Surface sample files can be auto-detected from common names such as `surface_samples.csv`, `SurfaceSamples.csv`, `surface.csv`, and `soils.csv`.
- Surface sample import requires Sample ID, X, and Y. Optional RL/elevation, from/to, prospect, and dataset/sample type columns are used when present.
- If surface sample depths are not supplied, intervals default to `0` to `0.1 m`, so point samples can participate in the existing interval table without forcing users to maintain drillhole-style depths.
- Surface samples are translated internally into synthetic collar, survey, and assay rows with `hole_type = SURFACE_SAMPLE`, but the UI displays them separately from drillholes.

### Plan View

- Added a `Layers` selector for `Both`, `Surface`, and `Drill Holes`, allowing users to inspect surface geochemistry without drill traces or assay bars.
- Surface samples now render as their own marker layer with `Surface Sample` hover text.
- Added independent surface sample analyte controls. Surface samples can follow the drill colour analyte or use a different analyte, such as drill Cu with soil Mg or Au.
- Added independent scale controls for drillholes and surface samples.
- Surface samples default to `Auto Jenks 6`, calculated from the currently filtered surface-sample values for the selected analyte.
- Existing `Analyte Colouring` presets can now be used directly in Plan View through `Drill Scale` and `Surface Scale > Saved Preset`.
- Surface samples and drillholes have separate ID filters. `Hole ID` lists drillholes only, while `Surface Sample ID` lists surface samples only.
- Plan View legends now adapt to available space: compact views show one scale when both drill and surface layers are visible, while maximized views can show separate drill and surface scales.
