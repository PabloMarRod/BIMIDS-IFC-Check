# BIMIDS-IFC-Check

An interactive, single-file dashboard for exploring **BIMids** use cases against the **Level of Information Need (LOIN)** concept, and comparing a selected BIMids configuration with a real **IFC** model uploaded straight in the browser.

Everything runs client-side. There is no server, no build step, and no data leaves the machine (keeps your data confidential): the IFC file is parsed locally in JavaScript.

## What it does

- **Browse and select use cases.** ~100 BIMids use cases are listed with their information score, density and geometry / property / document breakdown. Selecting cases builds a configuration and updates the metrics live.
- **Incremental / marginal analysis.** Each unselected use case shows its marginal contribution and percentage of unique objects relative to the current selection.
- **Upload an IFC model.** Drop a `.ifc` file (or click to browse). A pure-JavaScript IFC/STEP parser reads the file, counts entities and maps IFC entity types to BIMids object names.
- **Compare BIMids vs IFC.** When both a selection and an IFC model are present, the dashboard shows a side-by-side comparison, geometry/property/document splits, and flags IFC entity types that are not mapped to a BIMids object.
- **Charts.** Score and phase-allocation charts are rendered with Chart.js.

## Usage

No installation required. This runs on your browser.

## IFC parsing notes

The IFC reader is a lightweight, dependency-free STEP parser. It indexes entities by type and maps common IFC classes (walls, slabs, doors, MEP elements, etc.) to BIMids object names. It is intended for **quick inspection and comparison**, not as a full IFC toolkit: it does not perform geometry processing, schema validation, or property-set resolution beyond the mapping used by the dashboard. Entity types with no BIMids mapping are counted and reported separately so nothing is silently dropped.

## Data

The BIMids use-case data (scores, densities, object counts, phase allocation) is embedded in the html file. To update it, edit the `USE_CASES`, `INCREMENTAL`, `OBJECTS` and related arrays near the top of the `<script>` block.

## Citation

If you use this tool, please cite:

> Martinez, P. and Bolpagni, M. (2026). *Object-level multi-dimensional analysis of level of information requirements across project lifecycle*.
> In: Proceedings of the 2026 European Conference on Computing in Construction (EC3).
> https://doi.org/10.35490/EC3.2026.219

## Authors

- **Pablo Martinez** — Northumbria University, Newcastle upon Tyne, United Kingdom
- **Marzia Bolpagni** — Northumbria University, Newcastle upon Tyne, United Kingdom

## License

Licensed under the **Creative Commons Attribution 4.0 International (CC BY 4.0)**
license. You may share and adapt the material, including commercially, provided you
give appropriate credit and cite the reference above. See [`LICENSE`](LICENSE) for
details.
