# Retro Cover Studio v0.95.0-beta.5 — Pre-release notes

**Release status:** macOS Universal and Windows portable folder ZIPs were published October 31, 2026. A Linux x86-64 **AppImage** passed the author's Bazzite test and private CI; its release candidate is prepared for addition to the existing Beta 5 release. It is **not yet attached** as a public asset. The Windows one-file EXE has been discontinued and will not be released.

## New in Beta 5

- Game logo, disc numbering, and media type can each be set to **Off, Top, Bottom, Left, Right, or Center** on disc labels.
- Optional semi-transparent black strips behind disc text, with adjustable opacity (0–100%).
- Disc text color is configurable; the media type is centered within its strip.

## From earlier betas

- Proportional **Fill / Crop** or **Fit / Blurred Background** rendering for front, back, outside wrap, and inside images. No distortion of the source image's aspect ratio.
- Integrated Windows artwork thumbnail gallery and continuous-cover improvements.

## Distribution files

- `RetroCoverStudio-macOS-v0.95.0-beta.5.zip`
- `RetroCoverStudio-Windows-folder-v0.95.0-beta.5.zip`
- `SHA256SUMS-BETA5-verified-current.txt` (published checksums of the two ZIPs)
- `LICENSE` and `THIRD_PARTY_NOTICES.md`. The Windows portable folder includes its own `LICENSE.txt`, `THIRD_PARTY_NOTICES.md`, and 63 runtime/package license and notice files under `LICENSES/`.

**Prepared for Linux (pending public attachment):**

- `RetroCoverStudio-Linux-x86_64-v0.95.0-beta.5.AppImage` (single-file Linux x86-64 application)
- `SHA256SUMS-BETA5-Linux.txt` (standalone Linux checksum)
- See [Linux-specific release notes](LINUX_RELEASE_BETA5.md) for installation, Bazzite testing, data locations, and Auto design.

## AI-Assisted Development

Retro Cover Studio was developed with the assistance of OpenAI's ChatGPT. The project concept, requirements, feature decisions, testing, and release management were directed by the project author. ChatGPT assisted with software implementation, debugging, and documentation.

The project is independently maintained and is not affiliated with or endorsed by OpenAI.

## Installing

**macOS 13+:** Unzip and move `Retro Cover Studio.app` to Applications. This unsigned and unnotarized beta may prompt macOS security checks. Do not bypass security software.

**Windows 10/11 (x64):** Install the official [Microsoft Visual C++ x64 Redistributable](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist/) if it is not installed already. No separate Microsoft VC++/UCRT DLL copies are included in the uploaded ZIP. Unzip the complete portable folder archive and keep all files inside `RetroCoverStudio` together. Start the included `RetroCoverStudio.exe` from that folder. **There is no standalone EXE download**. Do not bypass any Defender warnings.

**Linux (x86-64):** After the Linux asset has been attached to the release, make the `.AppImage` file executable (`chmod +x RetroCoverStudio-Linux-x86_64-v0.95.0-beta.5.AppImage`) and run it in desktop mode. The previous Linux test build worked on Bazzite. The AppImage includes Python and its required packages, runtime notices, and licenses. If FUSE fails, the `--appimage-extract-and-run` option may help.

## Known limitations

- Applications are unsigned; no auto-update or installer.
- macOS uses a separate native layout engine; Windows and Linux share a Python/Tkinter layout engine. Rendering and interface details may differ between macOS and the other platforms.
- Disc-label elements can overlap if assigned the same position.
- Verify printed dimensions at 100% against your actual case/media.
- Online artwork usage and printing are subject to provider terms and artwork owners' rights.

**Verification:** The author reports working Windows/macOS builds and a clean Defender scan; both published ZIP SHA-256 values were verified. The Linux AppImage test2 worked on Bazzite, and the license-completed release candidate passed private CI, including a frozen Tk/Pillow preview self-test. The remaining Linux publication step is to upload the release-candidate AppImage and its checksum asset to the existing GitHub release. SteamGridDB API usage remains subject to the provider terms and artwork-owner rights.
