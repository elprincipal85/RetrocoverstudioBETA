# Retro Cover Studio — Beta 8 · Public pre-release

**Design print-ready retro-game covers and disc labels** for your personal collection on macOS, Windows and Linux.

> **Latest published pre-release:** [Retro Cover Studio v0.95.0-beta.8](https://github.com/elprincipal85/RetrocoverstudioBETA/releases/tag/v0.95.0-beta.8) (November 2, 2026), available for macOS, Windows and Linux. [Beta 5](https://github.com/elprincipal85/RetrocoverstudioBETA/releases/tag/v0.95.0-beta.5) remains available as an earlier version.

## AI-assisted development

Retro Cover Studio was developed with assistance from OpenAI's ChatGPT. The concept, requirements, feature decisions, tests and release decisions are directed by the project author. ChatGPT assisted with implementation, debugging and documentation. The project is independently maintained and is not endorsed by or affiliated with OpenAI.

## Downloads and platforms

| Platform | Beta 8 distribution |
| --- | --- |
| **macOS 13+** (Apple Silicon / Intel) | `RetroCoverStudio-macOS-v0.95.0-beta.8.zip` (Universal application) |
| **Windows 10/11**, x64 | `RetroCoverStudio-Windows-folder-v0.95.0-beta.8.zip` (portable complete application folder) |
| **Linux**, x86-64 | `RetroCoverStudio-Linux-x86_64-v0.95.0-beta.8.AppImage` |

**Download Beta 8 from the [official GitHub release page](https://github.com/elprincipal85/RetrocoverstudioBETA/releases/tag/v0.95.0-beta.8).** Choose the file for your operating system under **Assets**. A [SHA-256 checksum manifest](https://github.com/elprincipal85/RetrocoverstudioBETA/releases/download/v0.95.0-beta.8/SHA256SUMS-BETA8.txt) is provided to verify the files. Since Beta 8 is a **pre-release**, GitHub's generic `/releases/latest` shortcut may not point to it.

Windows distributes **only the portable folder version** (not a standalone single-file EXE). Unzip the entire folder; keep its supporting files together. The Windows 10/11 build may need the [official Microsoft Visual C++ x64 Redistributable](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist/) installed separately. Microsoft VC++ and UCRT system libraries are not redistributed as separate files in this folder.

The macOS application is unsigned and not notarized. Windows binaries are unsigned too; security prompts may occur. Do not disable antivirus or platform security to run the app.

For Linux: make the AppImage executable (`chmod +x`) and launch in a graphical desktop session. Compatibility with every distribution is not guaranteed; earlier Linux builds have been tried on Bazzite.

## Features

- Nine case formats spanning standard/slim/multidisc DVD, Blu-ray and CD jewel case.
- Print-size A4/A3 PDF export, inside and outside cover layouts, and multi-disc labels.
- Continuous wraparound art with independent front/back overlay images and an optionally recolored/translucent spine panel.
- Customizable top media strip **background color and opacity**, with independent replacement images for the spine `PC` mark and the front `PC CD-ROM / PC DVD-ROM / PC BLU-RAY` wordmark.
- **600 dpi transparent PNG export** for directly printable discs, with individually adjustable inner and outer print diameters; can be imported into Canon Easy-PhotoPrint Editor or comparable disc-printing software.
- Artwork can be replaced freely without manual unlocking; local images and optional SteamGridDB searches.
- Proportional **Fill / Crop** and **Fit / Blurred Background** artwork modes without stretching.
- Individual disc game-logo, number and media-type positions; optional translucent text strip and selectable text color.
- Editable metadata, optional online factual metadata lookups, saved projects and efficient **Update Preview** for text changes.
- Optional user-triggered **Auto design** to fill standard artwork slots. Screenshots and custom logos are not overwritten automatically.

Print PDF artwork at **Actual Size / 100%**, not Fit to Page. Import PNG disc labels into a compatible printer editor using the correct hole and outer-print dimensions. Verify alignment with a test blank before printing your collection.

## Privacy, rights, licenses

No API keys or copyrighted game artwork are bundled. Each user supplies their own SteamGridDB API key. Provider access does not grant license rights to reproduce or distribute individual artworks or trademarks. Retro Cover Studio is independent and is not affiliated with GOG, Steam, SteamGridDB or game publishers.

Application source is developed in a separate **private** repository. This public repository hosts downloads, documentation and issue reports. Our application code is licensed under [MIT](LICENSE); [third-party notices](THIRD_PARTY_NOTICES.md) describe external dependencies. Linux and Windows share the Python/Tkinter app and file format; macOS has a separate native application and project autosave format. Projects are not currently interchangeable between these systems.

## Release notes and feedback

See [Beta 8 release notes](RELEASE_NOTES_BETA8.md) for detailed changes, installation and known limitations. [Previous Beta 5 notes](RELEASE_NOTES_BETA5.md) remain available.

Found a bug? [Open an issue](https://github.com/elprincipal85/RetrocoverstudioBETA/issues) with your OS, template and steps to reproduce. **Never paste API keys, personal project files or private details into issues.**
