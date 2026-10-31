# Retro Cover Studio 0.95.0-beta.5 — actual binary license audit

**Verified candidate build:** private GitHub Actions [run 41230818790](https://github.com/elprincipal85/RetroCoverStudio/actions/runs/41230818790), 2026-10-31.

**Microsoft runtime redistribution issue: RESOLVED BY NOT DISTRIBUTING SEPARATE MICROSOFT RUNTIME DLLs.** The application still depends on the Microsoft Visual C++ x64 Redistributable being installed on Windows by the end user. The embedded Microsoft-linked code in CPython binaries remains subject to the CPython-provided Microsoft pass-through restrictions. Final public publication also depends on a clean-system Defender/user test and separate SteamGridDB/provider/content terms.

## Confirmed released-binary candidates

| Package | SHA-256 of the inner application ZIP |
| --- | --- |
| Windows 10/11 x64 portable folder | `f961d1b0d5ce209026879dff3f20a8098d4cea8bce0396d07ae89fee6596c776` |
| macOS universal app | `e7afd37b969056807c0d87a8ecfd3511c5e548d6e760e61c31804d1a2c6631fe` |

See [the complete checksum manifest](SHA256SUMS-BETA5.txt). ZIP integrity was checked independently; these hashes are not malware certificates.

## Windows: Microsoft libraries and authorization

The prior candidate ZIP bundled **45 individual Microsoft DLLs**, consisting of `VCRUNTIME140.dll`, `VCRUNTIME140_1.dll`, `ucrtbase.dll` and numerous `api-ms-win-*.dll` API-set forwarders.

The new candidate ZIP was rebuilt with `--onedir` and a controlled removal step. An independent inspection of all ZIP entries confirms **zero separately bundled Microsoft VC++/UCRT/API-set runtime DLLs**. CI also enforces the absence of these libraries and checks the frozen EXE after pruning.

**Windows 10/11 UCRT:** Microsoft documents UCRT as a built-in operating-system component; it is provided by Windows, not this package.

**Microsoft VC++ x64 Runtime:** `python312.dll`, `_tkinter.pyd`, and OpenSSL depend on VC++ runtime APIs. Users install the **official Microsoft Visual C++ x64 Redistributable** when needed, directly from Microsoft, subject to Microsoft's installer terms. We distribute neither the redistributable installer nor standalone `vcruntime140*.dll` copies.

**CPython Microsoft Distributable Code conditions:** Compiled Python code may still include embedded Microsoft-linked code. The official CPython `PC/crtlicense.txt` is included verbatim at `LICENSES/windows_runtime/PYTHON-3.12-MICROSOFT-CRT-CONDITIONS.txt`; `README_FIRST_WINDOWS.txt` gives user-facing terms and refers to this file. Required conditions include preserving notices, no false Microsoft endorsement, use on Microsoft-supported platforms, and no illegal or malicious use. Do not represent the MIT source license as replacing these conditions.

**Conclusion:** The issue concerning the publisher's authorization to ship *separate Microsoft runtime DLLs* is removed by excluding all those files from the distributed ZIP. This does not represent a binding legal opinion or override the CPython linked-code conditions.

Official documentation:
- [Visual C++ redistribution](https://learn.microsoft.com/en-us/cpp/windows/redistributing-visual-cpp-files)
- [Official Visual C++ Redistributable download information](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist/)
- [Universal CRT and Windows 10/11](https://learn.microsoft.com/en-us/cpp/windows/universal-crt-deployment?view=msvc-170)
- [CPython CRT pass-through conditions](https://github.com/python/cpython/blob/3.12/PC/crtlicense.txt)

## Windows: other licenses

The exact portable ZIP contains the application's MIT license and **63 runtime/package license and notice files** under `RetroCoverStudio/LICENSES/`:

- Python 3.12 PSF license and notices for incorporated software
- Tcl/Tk license
- OpenSSL 3 Apache 2.0 license
- libffi and zlib licenses
- Installed wheel/package notices for Pillow, ReportLab, Requests, pypdfium2, and dependencies, including PDFium BUILD_LICENSES for its embedded components
- CPython Microsoft-linked-code additional conditions

The private CI validates presence of expected files and PDFium notices before packaging. The app has **no user SteamGridDB API keys or downloaded game covers** bundled with it.

## macOS

The inspected universal `.app` uses Apple system SwiftUI, AppKit, Foundation, PDFKit, and CoreGraphics frameworks; these frameworks are not redistributed as separate runtime binaries inside the ZIP. No additional third-party runtime DLLs/framework packages were identified. Original application icons, software MIT license, and Apple platform rules remain relevant.

## Technical verification and remaining release gates

- **PASSED:** New macOS and Windows build jobs.
- **PASSED:** Windows core unit tests.
- **PASSED:** The frozen Windows EXE's own headless Tcl/PDF generation/PDFium runtime self-test on the GitHub Windows runner after pruning.
- **PASSED:** Independent new ZIP integrity checks, SHA-256 verification, zero extra Microsoft VC++/UCRT DLLs, and presence of license notices.
- **PENDING:** Real clean Windows 10/11 x64 machine test after installation of official VC++ x64 Redistributable, with up-to-date Microsoft Defender. Do not disable security products or bypass warnings.
- **PENDING:** Clean macOS first-run / unsigned-app warning UX.
- **SEPARATE LEGAL QUESTION:** Provider API and third-party game artwork rights under SteamGridDB's terms and users' respective jurisdictions.

**Public-binary status:** Draft/release candidate, not published. Owner approves public distribution only after the remaining release gates are satisfied.
