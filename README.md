# UC-HW-GPS-Card — GPS-only card hardware

The GPS-only card: a GNSS receiver on the same dedicated UART link and in the same 45 mm housing as the 4G card. Receiver still open: GPS only (L76K class) or with NavIC (LC29H / L89HA class).

This repo holds its schematics, PCBs, bill of materials, mechanical CAD and production guidelines. Requirements live in the umbrella repo `Universal-Controller_Hardware`, in `docs/arch/docs/01_Requirements_PRD.md` (D-40); the shared interfaces (stack bus, 4G UART link, battery socket, power stage, enclosure family) in `docs/arch/docs/02_Specifications.md`.

## Status

Design not started.

## Folders

| Folder | Contents |
|---|---|
| `lib/` | Shared library `UC-HW-Lib` (git submodule, pinned) |
| `docs/` | Design spec: block diagram, pin maps, calculations, power budget, design reviews |
| `bom/` | BOM per board (generated from KiCad), module BOM (boards + housing + fixings + packaging), `prices.csv` |
| `mech/` | build123d (Python) sources for cut-outs, front label and fit check; exports STEP / DXF / PDF / PNG |
| `production/` | Production guidelines: fab notes, assembly, programming, test, QC, labelling, packaging |
| `fab/` | Generated fab outputs — not in git; zipped into each release |

## Getting it

    git clone --recurse-submodules <repo URL>

Inside the umbrella repo it is checked out at `modules/gps-card/`.

## Releases

Each board has its own revision letter (A, B, …) in its title block and on its silkscreen, and its own git tag per fab release (`<board>-rev-<letter>`), with the fab zip attached. Release notes state the minimum firmware version.
