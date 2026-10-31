# Third-party software, service and artwork notices — Beta 5

The project's own software is licensed under MIT (see [LICENSE](LICENSE)). This does **not** grant rights to game artwork, logos, trademarks, or third-party code.

## macOS

The native macOS app uses system-provided Apple platform frameworks including SwiftUI, AppKit, Foundation, PDFKit and CoreGraphics. The inspected macOS ZIP contains no third-party runtime binary; Apple's developer terms and the rights to the app's bundled icon/resources still apply.

## Windows portable folder

The current **verified Windows 10/11 x64 candidate from GitHub Actions run 41230818790** is a `--onedir` ZIP, with its own MIT license and **63 third-party license/notice files** under `RetroCoverStudio/LICENSES/`. These cover CPython 3.12 and incorporated components, Tcl/Tk, OpenSSL 3, libffi, zlib, Pillow, ReportLab, Requests, pypdfium2/PDFium (including component BUILD_LICENSES), and other packaged dependencies.

**No separately bundled Microsoft Visual C++/UCRT/API-set DLLs** occur anywhere in the actual new ZIP. Windows 10/11 supplies UCRT. Users install the official **Microsoft Visual C++ x64 Redistributable** directly from Microsoft when needed; it is a prerequisite, not part of our download. Microsoft's redistribution license for separately packaged VC++ DLLs therefore does not apply to any such DLL in our shipped folder. Embedded Microsoft-linked code within CPython binaries retains the original additional Microsoft conditions, included verbatim and referenced in `README_FIRST_WINDOWS.txt`.

[Read the exact binary license audit](LICENSE_AUDIT_BETA5.md) and [Microsoft runtime download instructions](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist/). The ZIP has passed program-archive integrity and CI runtime smoke checks. A clean-machine Windows/Defender test and independent provider/content terms review are separate release gates.

## Optional online services

- **SteamGridDB:** users provide their own API keys. Provider terms and the rights of individual artwork creators still apply; keys do not grant redistribution rights.
- **Wikidata:** factual metadata is queried subject to service terms and applicable identification requirements.
- No third-party artwork, account API keys or retailer logos are intentionally distributed with the project.

Retro Cover Studio is an independent tool with no affiliation to game publishers, storefronts, or artwork providers.
