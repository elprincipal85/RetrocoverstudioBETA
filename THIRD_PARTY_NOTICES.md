# Third-party software, service and artwork notices — Beta 5

The project's own software is licensed under MIT (see [LICENSE](LICENSE)). This does **not** grant rights to game artwork, logos, trademarks, or third-party code.

## macOS

The native macOS app uses system-provided Apple platform frameworks including SwiftUI, AppKit, Foundation, PDFKit and CoreGraphics. The inspected macOS ZIP contains no third-party runtime binary; Apple's developer terms and the rights to the app's bundled icon/resources still apply.

## Windows portable folder

The actual Windows portable ZIP includes the CPython 3.12 interpreter, Tcl/Tk, OpenSSL 3, libffi, zlib, Microsoft Visual C++ Runtime and UCRT DLLs, plus Python packages such as Pillow, ReportLab, pypdfium2/PDFium and Requests. PyInstaller is the build tool. Each redistributed component has its own terms.

**NOT CLEARED FOR PUBLIC DISTRIBUTION.** Package/PDFium license texts were collected in the private build, but the runtime notice bundle is **incomplete**: CPython, Tcl/Tk, OpenSSL, libffi and zlib notices need to be completed; Microsoft's Visual C++ Runtime/UCRT redistribution authorization for the exact shipped DLLs must be verified. See [the component-by-component license audit](LICENSE_AUDIT_BETA5.md). The final license set must accompany the exact released binaries.

## Optional online services

- **SteamGridDB:** users provide their own API keys. Provider terms and the rights of individual artwork creators still apply; keys do not grant redistribution rights.
- **Wikidata:** factual metadata is queried subject to service terms and applicable identification requirements.
- No third-party artwork, account API keys or retailer logos are intentionally distributed with the project.

Retro Cover Studio is an independent tool with no affiliation to game publishers, storefronts, or artwork providers.
