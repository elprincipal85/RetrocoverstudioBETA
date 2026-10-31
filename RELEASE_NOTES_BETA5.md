# Retro Cover Studio v0.95.0-beta.5 — Pre-release notes (draft)

**Status: release preparation; binaries not yet published.** Two distribution formats only: macOS universal ZIP and Windows portable **folder ZIP**. The standalone Windows one-file EXE has been discontinued and will not be released.

## New in Beta 5

- Game logo, disc numbering, and media type can each be set to **Off, Top, Bottom, Left, Right, or Center** on disc labels.
- Optional semi-transparent black strips behind disc text, with adjustable opacity (0–100%).
- Disc text color is configurable; the media type is centered within its strip.

## From earlier betas

- Proportional **Fill / Crop** or **Fit / Blurred Background** rendering for front, back, outside wrap, and inside images. No distortion of the source image's aspect ratio.
- Integrated Windows artwork thumbnail gallery and continuous-cover improvements.

## Planned release files (NOT YET UPLOADED)

- `RetroCoverStudio-macOS-v0.95.0-beta.5.zip`
- `RetroCoverStudio-Windows-folder-v0.95.0-beta.5.zip`
- `SHA256SUMS-BETA5.txt` (the exact SHA-256 hashes of the final published ZIPs)
- `LICENSE` and `THIRD_PARTY_NOTICES.md`. The Windows portable folder includes its own `LICENSE.txt`, `THIRD_PARTY_NOTICES.md`, and 60 runtime/package license texts under `LICENSES/`.

## Installing

**macOS 13+:** Unzip and move `Retro Cover Studio.app` to Applications. This unsigned and unnotarized beta may prompt macOS security checks. Do not bypass security software.

**Windows 10/11 (x64):** Install the official [Microsoft Visual C++ x64 Redistributable](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist/) if it is not installed already. No Microsoft VC++/UCRT DLL copies are included in the planned updated ZIP. Unzip the complete portable folder archive and keep all files inside `RetroCoverStudio` together. Start the included `RetroCoverStudio.exe` from that folder. **There is no standalone EXE download**. Do not bypass any Defender warnings.

## Known limitations

- Applications are unsigned; no auto-update or installer.
- macOS and Windows use separate layout engines and may render details slightly differently.
- Disc-label elements can overlap if assigned the same position.
- Verify printed dimensions at 100% against your actual case/media.
- Online artwork usage and printing are subject to provider terms and artwork owners' rights.

**Publishing gates:** exact third-party/runtime notices are bundled and final ZIP SHA-256 hashes verified. Remaining: clean Windows Defender test, confirmation of Microsoft runtime redistribution conditions and SteamGridDB provider terms, and macOS first-run behavior.
