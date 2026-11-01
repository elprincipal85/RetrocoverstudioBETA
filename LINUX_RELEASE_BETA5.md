# Retro Cover Studio — Linux x86-64 AppImage (Beta 5)

**Release preparation:** This document describes the Linux AppImage build prepared for attachment to the existing `v0.95.0-beta.5` GitHub pre-release. The AppImage is not a separate Windows/macOS rebuild. Check the [release assets](https://github.com/elprincipal85/RetrocoverstudioBETA/releases/tag/v0.95.0-beta.5) before assuming the Linux file has been uploaded.

## Supported and tested

- Single portable **x86-64 AppImage** for Linux desktop environments; no `.tar.gz` package or installer.
- Built on Ubuntu 22.04 with Python 3.12, Tkinter, Pillow, ReportLab, and PDFium. Compatibility with every Linux distribution is not guaranteed.
- The previous Linux test build was confirmed working on **Bazzite** by the project author, including the preview after the Pillow/Tk fix and the **Auto design** workflow.
- The release candidate has added runtime and third-party license notices, with no intended functional changes from the tested test2 build.

## Run

1. Download `RetroCoverStudio-Linux-x86_64-v0.95.0-beta.5.AppImage` from GitHub Releases.
2. Allow the AppImage to execute and start it:

```bash
chmod +x RetroCoverStudio-Linux-x86_64-v0.95.0-beta.5.AppImage
./RetroCoverStudio-Linux-x86_64-v0.95.0-beta.5.AppImage
```

On systems without usable FUSE support, try:

```bash
./RetroCoverStudio-Linux-x86_64-v0.95.0-beta.5.AppImage --appimage-extract-and-run
```

The application uses a GUI session and is intended for desktop mode, including Bazzite's desktop mode.

## Features and first run

- Cover/insert layouts and disc labels, live PDF preview and print-size export.
- Optional user-initiated SteamGridDB artwork searches with the **user's own API key**.
- **Auto design (cover + logo)** fills available front/back/wrap/inside/disc artwork and game-logo slots from a matching title while leaving existing user-selected images and screenshots alone.
- Online requests are disabled by default. Enable them in the Artwork tab before using search or Auto design.
- Optional Wikidata factual metadata with the contact information required by that provider.
- Printing: select **100% / Actual Size**, not fit-to-page. Verify case dimensions before cutting.

## Local Linux data

Settings and the API key are stored in plain text under `~/.config/RetroCoverStudio/preferences.json` (or `$XDG_CONFIG_HOME/RetroCoverStudio/preferences.json` if configured).

Autosave: `last_cover.json`; artwork: `Images/` in the same application-data directory. Project files (`.rcs`) and PDFs are stored wherever the user chooses.

**Never share personal API keys or private project files in public bug reports.**

## Limits and rights

- Linux and Windows use a Python/Tkinter UI; macOS uses a separate SwiftUI renderer. Layout details can differ.
- The Linux AppImage is unsigned and does not have an installer or auto-updater.
- The AppImage includes the project's MIT license, Python package notices, PDFium component license texts, and runtime notices.
- No personal API key or third-party game images are intentionally bundled.
- Artwork rights and third-party API terms remain the responsibility of the user; a personal API key does not grant redistribution rights.
- SteamGridDB, game companies and OpenAI do not endorse or sponsor this application.

## AI-Assisted Development

Retro Cover Studio was developed with assistance from OpenAI's ChatGPT. The project concept, requirements, feature decisions, testing and release management were directed by the project author. The project is independently maintained.
