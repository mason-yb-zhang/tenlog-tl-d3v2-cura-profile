# Tenlog TL-D3V2 Cura Profile

Official Tenlog Cura resources for the TL-D3V2 dual-extruder IDEX 3D printer.

This repository contains printer definitions, extruder definitions, the build
plate model, and Tenlog material profiles. It does not contain executables,
patches, cracks, or proprietary Cura installers.

## Printer Parameters

The `tenlog_d3v2.def.json` definition specifies:

- Build volume: `300 x 300 x 350 mm`
- Build plate: `TENLOG-D3V2.stl`
- Extruders: `2`
- Nozzle size: `0.4 mm`
- Filament diameter: `1.75 mm`
- Cura nozzle offsets: `X=0`, `Y=0` for both extruders
- Prime tower position: `X=155`, `Y=155`
- Heated bed: enabled in `tenlog_printer.def.json`
- G-code flavor: Marlin-compatible G-code

The base definition also provides the Tenlog start/end G-code and defaults
such as 60 mm/s print speed, 20 mm/s first-layer speed, 500 mm/s^2
acceleration, and 8 mm extruder-switch retraction.

## Installation

1. Exit Cura completely.
2. Open Cura's installation directory, for example:

   `C:\Program Files\UltiMaker Cura 5.13.0\share\cura\resources`

3. Copy files into the matching resource directories:

   - `definitions/*.def.json` -> `resources/definitions/`
   - `extruders/*.def.json` -> `resources/extruders/`
   - `materials/*.fdm_material` -> `resources/materials/`
   - `meshes/TENLOG-D3V2.stl` -> `resources/meshes/`

4. Start Cura and add `Tenlog TL-D3V2` from the non-networked printer list.

## Source

The files were obtained from the local Tenlog Cura resource package supplied
with the printer software:

`D:\BaiduNetdiskDownload\双喷头打印机\3.cura切片软件安装及使用\3.破解文件`

The resource package contains definitions for several Tenlog models. This
repository intentionally includes only the TL-D3V2 dependencies and the
matching Tenlog material profiles.

## License

The files retain their upstream licensing and copyright notices, if any.
This repository does not relicense the upstream Tenlog resources.
