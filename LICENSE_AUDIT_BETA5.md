# Retro Cover Studio v0.95.0-beta.5 — runtime license audit

Audit date: 2026-10-31. Based on the **actual built macOS and Windows ZIP archives** from private GitHub Actions run 41229763027, not just `requirements.txt`.

**Disposition: HOLD PUBLIC RELEASE.** This is a technical inventory and preliminary license analysis, not a legal opinion. Security scanning and SteamGridDB provider/content terms are separate open gates.

## macOS Universal ZIP

Contents examined: `Retro Cover Studio.app/Contents/MacOS/Retro Cover Studio`, `Resources/AppIcon.icns`, `Resources/Assets.car`, `Info.plist` and `PkgInfo`. No separately packaged Python, OpenSSL, Tcl/Tk, PDFium, or other third-party runtime binaries. Uses system-provided Apple SwiftUI/AppKit/Foundation/PDFKit/CoreGraphics frameworks.

- No extra third-party runtime license files identified for this macOS ZIP.
- Confirm authorship/right to distribute the app icon and all custom resources.
- Apple's Xcode/macOS distribution terms still apply; unsigned/not-notarized launch behavior is a separate security and usability gate.
- Own application source is MIT licensed. Include the project's own LICENSE in the release.

Official references: https://help.apple.com/xcode/mac/current/en.lproj/dev31de635e5.html ; https://developer.apple.com/support/terms/apple-developer-program-license-agreement/

## Windows portable folder ZIP

**Confirmed runtime files in `RetroCoverStudio/_internal/`:**

| Component | Found in archive | License and required action |
| --- | --- | --- |
| CPython 3.12 | `python312.dll`, `_*.pyd` | PSF License v2; ship Python 3.12 LICENSE and appropriate incorporated-software notices |
| Tcl/Tk | `tcl86t.dll`, `tk86t.dll`, `tcl8/`, `_tk_data/` | Tcl/Tk BSD-like license; `_tk_data/license.terms` is present; include applicable Tcl/Tk notices |
| OpenSSL 3 | `libssl-3.dll`, `libcrypto-3.dll` | Apache License 2.0; include text and applicable notices |
| libffi | `libffi-8.dll` | MIT-style license; include copyright and full text |
| zlib | `zlib1.dll` | zlib license; retain applicable notices |
| Microsoft Visual C++ | `VCRUNTIME140.dll`, `VCRUNTIME140_1.dll` | **Unresolved redistribution/provenance verification:** Microsoft REDIST eligibility and terms |
| Microsoft UCRT / API sets | `ucrtbase.dll`, `api-ms-win-*.dll` | **Unresolved redistribution/provenance verification:** Windows 10/11 normally provide UCRT; confirm which bundled copies can or should be shipped |
| pypdfium2/PDFium | `pypdfium2_raw/pdfium.dll` and license data | Apache/BSD and PDFium dependency notices; PDFium bundle's detailed BUILD_LICENSES are present in the collected third-party license archive |
| Pillow, Requests, ReportLab, certifi etc. | bundled Python runtime dependencies | Collected package license inventory is available separately; include relevant texts in the final release |

**Updated package check (run 41229763027):** The Windows folder ZIP now contains 60 third-party and runtime license files under `RetroCoverStudio/LICENSES/`, including full CPython 3.12 and its incorporated-software notices, CPython's Microsoft CRT conditions, Tcl/Tk, OpenSSL 3, libffi, zlib, and collected Python package/PDFium component licenses. The ZIP passed an automated file-presence check and an independent archive-integrity check. This alone is not proof of compliance with separate Microsoft redistribution obligations.

**Important:** PyInstaller is used to build the executable. Its own official special GPL exception allows packaging and distributing proprietary or commercial programs without forcing the resulting app under GPL; third-party runtime terms still apply.

**Microsoft runtime decision needed:** identify the precise originating Windows SDK/CPython runtime binaries, verify permissible REDIST items/terms for this distribution, and decide whether the redundant UCRT/API-set copies should be excluded from a newly tested build. Do not remove DLLs from the existing tested ZIP without rebuilding, testing, and recalculating checksums.

## Mandatory release actions

1. **Done:** include CPython 3.12 and its incorporated software licenses, Tcl/Tk, OpenSSL 3, libffi, zlib and full Python package/PDFium notices in the actual portable folder ZIP.
2. Review and document Microsoft's **Visual C++/UCRT redistribution rights** for the exact binaries distributed, including the Python Windows build's additional CRT terms.
3. **Done for currently identified components:** exact Windows ZIP embeds the source MIT license, third-party notice index and 60 runtime/package license files under `LICENSES/`.
4. **Done:** rebuilt the licensed folder ZIP and verified SHA-256 `779ff372b23e0c08dba265d30765214b68c69b2ed2de0db3abfe8e26e04ab1d7`. **Still required:** Microsoft Defender scan on the exact new ZIP extracted to a clean Windows system.
5. Separately resolve SteamGridDB API/content terms and the initial-launch safety testing before public release.

## Primary licenses and documentation

- Python 3.12: https://docs.python.org/3.12/license.html
- CPython Windows CRT conditions: https://github.com/python/cpython/blob/3.12/PC/crtlicense.txt
- Microsoft redistribution: https://learn.microsoft.com/en-us/cpp/windows/redistributing-visual-cpp-files?view=msvc-170
- Microsoft DLL identification: https://learn.microsoft.com/en-us/cpp/windows/determining-which-dlls-to-redistribute?view=msvc-170
- OpenSSL 3: https://openssl-library.org/source/license/index.html
- Tcl/Tk: https://github.com/tcltk/tk/blob/main/license.terms
- libffi: https://github.com/libffi/libffi/blob/master/LICENSE
- zlib: https://zlib.net/zlib_license.html
- PDFium notices: https://pypdfium2.readthedocs.io/en/stable/readme.html
- PyInstaller exception: https://www.pyinstaller.org/en/stable/license.html
