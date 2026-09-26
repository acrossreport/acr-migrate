# ACR Migrate

A set of tools that convert ActiveReports (RPX) and Microsoft RDL/RDLC report definition files into [ACR (Across Report Renderer)](https://acrossreport.com) report definition files (`.acr`).

Two converters are provided as Windows binaries.

| Tool | Converts from | Accuracy |
|------|----------------|----------|
| `rpx2json.exe` | ActiveReports `.rpx` | High-fidelity (absolute coordinates — little to no position adjustment needed) |
| `rdl2json.exe` | Microsoft RDL / RDLC `.rdlc` | Best-effort (table-like elements use estimated coordinates; layout review in ACR Designer is expected) |

Both tools are free to use and redistribute. The source code is not published, but execution and redistribution are unrestricted.

---

## Supported platform

Windows only (x64). Since ActiveReports Designer and RDL designers themselves are Windows-only, there are no current plans to support other platforms.

---

## Download

Download the latest zip from [Releases](../../releases). No installation is required — just extract and run.

---

## Usage

### rpx2json.exe (from ActiveReports RPX)

```
rpx2json.exe input.rpx
```

Creates a `.acr` file with the same name, in the same folder.

```
rpx2json.exe Report.rpx
# → Report.acr is created
```

Because RPX sections use absolute coordinates, little to no position adjustment is needed after conversion.

### rdl2json.exe (from Microsoft RDL/RDLC)

```
rdl2json.exe input.rdlc
```

Creates a `.acr` file with the same name, in the same folder.

```
rdl2json.exe report.rdlc
# → report.acr is created
```

Because RDL resolves table-like (Tablix) layout at render time, the converted file is marked as having estimated coordinates for those elements. **Open the result in ACR Designer to review and adjust the layout.** Subreports are not currently supported.

---

## Opening the converted file

The resulting `.acr` file can be opened in [ACR Designer](https://acrossreport.com) for printing, PDF export, and layout adjustment. If you don't have ACR Designer, download it from [acrossreport.com](https://acrossreport.com).

---

## Support

These tools are provided free of charge with no warranty or support obligation. If you need assistance with migration work (layout adjustment after conversion, bulk migration of many files, etc.), paid support is available on request. Contact: across.support@gmail.com

---

## License

Copyright (C) 2026 Across Systems Corporation.

Free to run and redistribute. Decompilation and modification are prohibited. See the included LICENSE.txt for details.
