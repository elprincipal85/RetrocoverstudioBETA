# Third-party software, service and artwork notices — Beta 8

The project's own software is licensed under MIT (see [LICENSE](LICENSE)). This does **not** grant rights to game artwork, logos, trademarks, or third-party code.

## macOS

The native macOS app uses system-provided Apple platform frameworks including SwiftUI, AppKit, Foundation, PDFKit and CoreGraphics. The inspected macOS ZIP contains no third-party runtime binary; Apple's developer terms and the rights to the app's bundled icon/resources still apply.

## Windows portable folder

The **Beta 8 Windows 10/11 x64** download is a `--onedir` ZIP with its own MIT license and third-party license/notice files under `RetroCoverStudio/LICENSES/`. The release assembly includes a dependency-license check. Notices cover CPython 3.12 and incorporated components, Tcl/Tk, OpenSSL 3, libffi, zlib, Pillow, ReportLab, Requests, pypdfium2/PDFium (including component BUILD_LICENSES), and other packaged dependencies.

**No separately bundled Microsoft Visual C++/UCRT/API-set DLLs** occur anywhere in the actual new ZIP. Windows 10/11 supplies UCRT. Users install the official **Microsoft Visual C++ x64 Redistributable** directly from Microsoft when needed; it is a prerequisite, not part of our download. Microsoft's redistribution license for separately packaged VC++ DLLs therefore does not apply to any such DLL in our shipped folder. Embedded Microsoft-linked code within CPython binaries retains the original additional Microsoft conditions, included verbatim and referenced in `README_FIRST_WINDOWS.txt`.

[Read the previous Beta 5 license audit](LICENSE_AUDIT_BETA5.md) and [Microsoft runtime download instructions](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist/). The Beta 8 Windows archive passed the build's license inventory and CI runtime smoke checks, and the project author confirmed a local Defender check of the release candidate. This is not a security certification; users should verify release hashes and use up-to-date operating-system security protections.

## Linux x86-64 AppImage

The Beta 8 Linux AppImage is packaged as a single self-contained x86-64 application, built on Ubuntu 22.04 from the Python/Tkinter codebase. The automatic build and runtime smoke checks passed. Earlier Linux versions were functionally tried on Bazzite; platform-specific compatibility of the new version still depends on the user's desktop.

The AppImage includes the project's MIT license and `THIRD_PARTY_NOTICES.md` under its internal `usr/share/doc/RetroCoverStudio/`, as well as:
- CPython 3.12, incorporated software notices, Tcl/Tk, OpenSSL, libffi, and zlib terms in `runtime-licenses/`
- Pillow, ReportLab, Requests and related package notices, PyInstaller bootloader licensing information, and PDFium/third-party component license texts in `python-licenses/`

The AppImage does not bundle downloaded game artwork or an individual user's SteamGridDB API key. Linux preferences and artwork are stored outside the executable, under `~/.config/RetroCoverStudio/` by default. The AppImage is unsigned and unnotarized. These notices are a packaging review, not a guarantee of rights to third-party images or compatibility with every Linux system.

## Optional online services

- **SteamGridDB:** users provide their own API keys. Provider terms and the rights of individual artwork creators still apply; keys do not grant redistribution rights.
- **Wikidata:** factual metadata is queried subject to service terms and applicable identification requirements.
- No third-party artwork, account API keys or retailer logos are intentionally distributed with the project.

Retro Cover Studio is an independent tool with no affiliation to game publishers, storefronts, or artwork providers.
