# Tenlog TL-D3V2 Cura Profile

## 项目简介 | Overview

本仓库提供 Tenlog TL-D3V2 双喷头 IDEX 3D 打印机的 Cura 配置资源。

This repository provides Cura resources for the Tenlog TL-D3V2 dual-extruder
IDEX 3D printer.

仓库内容包括打印机定义、挤出机定义、打印平台模型和 Tenlog 材料配置。
不包含可执行程序、破解补丁、破解文件或 Cura 安装程序。

The repository contains printer definitions, extruder definitions, the build
plate model, and Tenlog material profiles. It does not contain executables,
cracks, patches, or proprietary Cura installers.

## 打印机参数 | Printer Parameters

`definitions/tenlog_d3v2.def.json` 中的主要参数如下：

The main parameters in `definitions/tenlog_d3v2.def.json` are:

- 成型尺寸 / Build volume: `300 x 300 x 350 mm`
- 打印平台模型 / Build plate model: `TENLOG-D3V2.stl`
- 挤出机数量 / Extruders: `2`
- 喷嘴直径 / Nozzle size: `0.4 mm`
- 耗材直径 / Filament diameter: `1.75 mm`
- Cura 喷嘴偏移 / Cura nozzle offsets: `X=0`, `Y=0` for both extruders
- 塔位置 / Prime tower position: `X=155`, `Y=155`
- 加热床 / Heated bed: enabled in `tenlog_printer.def.json`
- G-code 风格 / G-code flavor: Marlin-compatible G-code

基础定义文件还包含 Tenlog 的开始/结束 G-code，以及以下默认切片参数：

The base definition also contains Tenlog start/end G-code and the following
default slicing parameters:

- 打印速度 / Print speed: `60 mm/s`
- 首层打印速度 / First-layer speed: `20 mm/s`
- 加速度 / Acceleration: `500 mm/s^2`
- 换料回抽量 / Extruder-switch retraction: `8 mm`
- 换料回抽速度 / Extruder-switch retraction speed: `60 mm/s`

## 文件结构 | File Structure

```text
definitions/
  tenlog_d3v2.def.json
  tenlog_printer.def.json
extruders/
  tl_dual_0.def.json
  tl_dual_1.def.json
materials/
  Tenlog PLA, TPU, and PVA material profiles
meshes/
  TENLOG-D3V2.stl
```

## 安装方法 | Installation

### 中文说明

1. 完全退出 Cura，包括后台进程。
2. 在 Cura 安装目录中找到 `share/cura/resources` 目录。
3. 将本仓库中的文件复制到对应的 Cura 资源目录：

   - `definitions/*.def.json` -> `resources/definitions/`
   - `extruders/*.def.json` -> `resources/extruders/`
   - `materials/*.fdm_material` -> `resources/materials/`
   - `meshes/TENLOG-D3V2.stl` -> `resources/meshes/`

4. 重新启动 Cura。
5. 在添加非联网打印机列表中选择 `Tenlog TL-D3V2`。

### English Instructions

1. Exit Cura completely, including any background process.
2. Locate the `share/cura/resources` directory inside the Cura installation.
3. Copy the repository files into the matching Cura resource directories:

   - `definitions/*.def.json` -> `resources/definitions/`
   - `extruders/*.def.json` -> `resources/extruders/`
   - `materials/*.fdm_material` -> `resources/materials/`
   - `meshes/TENLOG-D3V2.stl` -> `resources/meshes/`

4. Restart Cura.
5. Select `Tenlog TL-D3V2` from the non-networked printer list.

不同操作系统和 Cura 安装方式的实际安装路径可能不同，请以本机 Cura
安装目录为准。

The installation path may differ by operating system and Cura installation
method. Use the actual Cura installation directory on your system.

## 材料配置 | Material Profiles

仓库包含以下 Tenlog 材料配置：

The repository includes the following Tenlog material profiles:

- `tlblue_pla.xml.fdm_material`
- `tlgreen_pla.xml.fdm_material`
- `tlred_pla.xml.fdm_material`
- `tlwhite_pla.xml.fdm_material`
- `tlyellow_pla.xml.fdm_material`
- `tl_tpu.xml.fdm_material`
- `tl_pva.xml.fdm_material`

## 来源说明 | Source

这些文件来自 Tenlog Cura 资源包中的 TL-D3V2 配置。资源包同时包含其他
Tenlog 机型的定义；本仓库只保留 TL-D3V2 所需的基类、双挤出机定义、
平台模型和匹配的材料配置。

These files originate from the Tenlog Cura resource package containing the
TL-D3V2 configuration. The package also includes definitions for other Tenlog
models; this repository keeps only the TL-D3V2 base definition, dual-extruder
definitions, build plate model, and matching material profiles.

## 许可证 | License

文件保留其上游许可证和版权声明（如果有）。本仓库不对上游 Tenlog
资源重新授权，也不声明拥有这些上游资源的版权。

The files retain their upstream licenses and copyright notices, if any. This
repository does not relicense the upstream Tenlog resources or claim ownership
of their copyrights.

## 参考资料包 | Reference Package

`reference-package/` 保留了 Tenlog 双喷头打印机原始资料包的目录结构，
用于保存说明书、调试资料、测试模型、测试 G-code、打印机 STL、Cura
资源、Wi-Fi 资料和联机打印工具。

The `reference-package/` directory preserves the original directory structure
of the Tenlog dual-extruder printer package. It contains manuals, debugging
documents, test models, test G-code, printer STL files, Cura resources, Wi-Fi
documentation, and online-printing tools.

资料包中上传了 63 个文件。为避免上传大型安装介质和视频，以下文件被
明确排除：

The package includes 63 uploaded files. The following files are intentionally
excluded to avoid distributing large installation media and videos:

- `3.cura切片软件安装及使用/2.Ultimaker/Ultimaker-Cura-5.1.0-win64.exe`
- 根目录下的 3 个 `.mp4` 视频文件 / The three `.mp4` videos in the package root

其他安装程序没有被排除，包括 CH340 串口驱动和 Repetier-Host 工具。

Other installers were not excluded, including the CH340 serial driver and the
Repetier-Host tool.

### 资料包目录 | Package Contents

- `2.安装教程/`：整机安装指导书 / Printer assembly manual
- `3.cura切片软件安装及使用/`：Cura 文档、驱动和 Tenlog 配置资源 / Cura documentation, driver, and Tenlog resources
- `4.机器调试/`：设备调试、平台调平和平台调试说明 / Machine setup and bed-leveling documents
- `5.测试打印文件/`：喷头距离、单头、双色、复制、镜像和支撑测试 / Nozzle-distance, single-extruder, dual-color, duplicate, mirror, and support tests
- `6.常见问题/`：常见打印问题说明 / Common printing issue documentation
- `7.STL/`：配套 STL 文件 / Related STL files
- `8.联机打印/`：Repetier-Host 工具和使用说明 / Repetier-Host tool and instructions
- `9wifi/`：Wi-Fi 模块使用说明 / Wi-Fi module instructions
