# Retro Cover Studio — Beta 0.95.0-beta.5

**Design print-ready physical game covers and disc labels** for your personal retro-game collection. Desktop applications for macOS, Windows, and Linux.

## AI-Assisted Development

Retro Cover Studio was developed with the assistance of OpenAI’s ChatGPT.

The project concept, requirements, feature decisions, testing, and release management were directed by the project author. ChatGPT assisted with software implementation, debugging, and documentation.

The project is independently maintained and is not affiliated with or endorsed by OpenAI.

> **Release status:** [Beta 5 is published](https://github.com/elprincipal85/RetrocoverstudioBETA/releases/tag/v0.95.0-beta.5) for macOS and Windows. A Bazzite-tested Linux x86-64 AppImage has been prepared and will be available from the same release once its asset is uploaded.

## Download formats

| Platform | Distribution |
| --- | --- |
| **macOS 13+** | Universal macOS app for Apple Silicon and Intel, ZIP archive |
| **Windows 10/11** | Portable **folder version** (ZIP archive containing the full `RetroCoverStudio` directory) |
| **Linux x86-64** | Single portable **AppImage** (Bazzite-tested; release attachment pending) |

**Windows: folder package only. No standalone one-file EXE, installer, or single-file download is planned.** Keep the entire extracted Windows folder together. The Windows 10/11 (x64) version requires the **official Microsoft Visual C++ x64 Redistributable**, installed separately by the user if not already present. It does **not** ship standalone Microsoft VC++ or UCRT DLL copies. [Official Microsoft download information](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist/). Both builds are currently unsigned; macOS is not notarized. Do not disable or bypass antivirus/Gatekeeper warnings.

**Linux:** Make the AppImage executable (`chmod +x`) and start it in a Linux desktop session. No separate Python installation is needed. The Linux build includes an **Auto design (cover + logo)** option for filling available cover and logo slots without replacing manually chosen artwork. Linux data are stored under `~/.config/RetroCoverStudio/` (or `$XDG_CONFIG_HOME/RetroCoverStudio/`). See [Linux installation and release notes](LINUX_RELEASE_BETA5.md). Only download the AppImage after it appears in official release assets.

## Features

- Nine layouts for DVD, Blu-ray, and jewel cases, including outside wraps and inside artwork.
- Print-size A4/A3 PDF layouts; use **100% / Actual Size** when printing.
- Choose between proportional **Fill / Crop** and **Fit / Blurred Background** image modes (no stretching).
- Adjustable disc-label logo, disc numbering, and media type positions (Off / Top / Bottom / Left / Right / Center).
- Optional translucent black text strips, strip opacity and disc-label text colors.
- Custom logos, backgrounds, optional game metadata, and saved projects.
- Optional SteamGridDB artwork lookup with a **user-provided** API key and optional Wikidata metadata.

## Privacy, licenses and artwork

No personal API keys or third-party game artwork are included with downloads. Optional online services communicate with their providers when used. Artwork, logos and trademarks remain the property of their rights holders; supplying an API key does not grant redistribution or commercial rights. This tool is independent and is not affiliated with GOG, Steam, SteamGridDB, game publishers, or distributors.

Application source code is maintained separately in a private development repository. The public repository is for beta download releases, documentation, and issue reports. The project's own software is MIT licensed; see [LICENSE](LICENSE) and [third-party notices](THIRD_PARTY_NOTICES.md).

## Feedback

Please open a [GitHub issue](https://github.com/elprincipal85/RetrocoverstudioBETA/issues) with your operating system, cover type, reproduction steps, and non-copyrighted example artwork. **Never post API keys, personal projects, or private information** in public issue reports.

See [Beta 5 release notes](RELEASE_NOTES_BETA5.md) for release contents, including the Linux AppImage preparation status and known limitations.
