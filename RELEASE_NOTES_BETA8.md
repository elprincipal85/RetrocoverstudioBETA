# Retro Cover Studio v0.95.0-beta.8 — Pre-release notes

Create printable retro-game DVD/Blu-ray case covers, CD jewel-case inserts, wraparound artwork and CD/DVD/Blu-ray disc labels on **macOS, Windows and Linux**. This update combines the improvements introduced in Betas 6–8 since public Beta 5.

## What's new in Beta 8

**Customizable top media band**
- Set any background color and opacity (0–100%) for the spine-to-front header band.
- Optionally replace the spine's “PC” marking with a custom image or transparent logo.
- Independently replace the entire front “PC CD-ROM”, “PC DVD-ROM” or “PC BLU-RAY” marking with another image.
- Choose local images or SteamGridDB artworks. Images retain their original aspect ratio.
- Existing printed header letters remain available and the default black/86% band style is preserved.
- On jewel cases, the top media strip applies to the separate front card rather than wrapping around the tray spines.

**From Beta 7 — Disc printing and artwork editing**
- Export transparent **600 dpi disc-label PNGs** (2835 × 2835 px for a 120 mm disc), in addition to the existing PDF format.
- Set printable inner-hole and outer diameters (defaults: **22 mm inside / 118 mm outside**). Multi-disc projects export one numbered PNG per disc.
- PNGs can be imported into Canon Easy-PhotoPrint Editor or compatible direct-to-disc printing software. The app does not directly operate printer trays.
- Artwork can be replaced at any time, without having to unlock images.

**From Beta 6 — Layout and preview**
- Use an outside wraparound image as a base, then optionally place independent front/back images above it.
- Customize the spine background and opacity.
- Preview text edits using **Update Preview**; other controls keep their responsive preview updates.

All existing Beta 5 disc-label placement controls, optional translucent text strips, colors, image fitting modes and case layouts remain supported.

## Downloads

| Platform | File |
| --- | --- |
| **macOS 13+**, Universal (Intel / Apple Silicon) | `RetroCoverStudio-macOS-v0.95.0-beta.8.zip` |
| **Windows 10/11**, x64 | `RetroCoverStudio-Windows-folder-v0.95.0-beta.8.zip` |
| **Linux**, x86-64 | `RetroCoverStudio-Linux-x86_64-v0.95.0-beta.8.AppImage` |

Also provided: **SHA256SUMS-BETA8.txt**, the MIT **LICENSE** and **THIRD_PARTY_NOTICES.md**. Check the SHA-256 of each downloaded program against the manifest.

### Installation

**macOS:** Unzip the package and open `Retro Cover Studio.app`. The app is unsigned and not notarized; macOS may display its normal security warning. Do not disable system security to run it.

**Windows:** Unzip the full portable folder, keep all of its contents, and run `RetroCoverStudio.exe` from inside. No standalone single-file EXE or installer is distributed. If needed, obtain the official [Microsoft Visual C++ x64 Redistributable](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist/) directly from Microsoft. The binary is unsigned; never bypass Defender detections.

**Linux:** Mark the AppImage executable with `chmod +x RetroCoverStudio-Linux-x86_64-v0.95.0-beta.8.AppImage` and launch it from a graphical desktop session. Compatibility can vary across distributions.

**Printing:** Set PDF printing to **100% / Actual Size**. For direct-to-disc labels, load the 600 dpi PNG in your disc-printer editor, match the printable inner/outer diameters and test alignment on a blank.

## Important notes

- This is **beta software**, without an auto-updater, installer or code signing.
- The application includes **no personal API key and no third-party game artwork**. Each user provides their own SteamGridDB API key if desired.
- Artwork and trademarks remain subject to their respective owners' rights and service terms. API access is not permission to redistribute images.
- macOS uses a separate native renderer and autosave format; Windows/Linux share a Python engine and `.rcs` projects. Cross-platform project-file conversion is not currently supported.
- Very small layout or printed-color differences across systems/printers are possible. Test physical case and disc alignment.

## Development and feedback

Retro Cover Studio was developed with assistance from OpenAI's ChatGPT. The project concept, requirements, decisions, tests and release management are directed by the project author. The tool is independently maintained and is not affiliated with or endorsed by OpenAI.

Issues and feedback: https://github.com/elprincipal85/RetrocoverstudioBETA/issues

Project source is maintained separately in a private development repository. This public repository distributes tested beta releases and documentation.
