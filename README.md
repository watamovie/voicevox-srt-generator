# SRT Generator for VOICEVOX

[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Static app](https://img.shields.io/badge/app-static%20HTML%2FCSS%2FJS-blue.svg)](#development)
[![Privacy](https://img.shields.io/badge/files-browser--local-only.svg)](#privacy-and-security)

Browser-only SRT subtitle generator for matching `.wav` and `.txt` exports from
VOICEVOX-style voice-synthesis workflows.

Public app: https://srt-wavtxt-tool.pages.dev/

This is an unofficial tool. It is not affiliated with the VOICEVOX project and
does not include VOICEVOX, its engine, core, voice libraries, or character assets.

## Why this exists

VOICEVOX and similar Japanese voice-synthesis tools are often used for video
production. A common workflow is:

1. Write lines in the voice-synthesis tool.
2. Export numbered `.wav` files and matching `.txt` scripts.
3. Import audio and subtitles into a video editor.

This project removes part of the repetitive subtitle work by measuring the audio
duration in the browser and producing an `.srt` file from the existing text. It
does not perform speech recognition or translation; it uses the script text that
already exists.

The project is still early-stage and intentionally small. Its open-source value
is in providing a focused, privacy-preserving utility for a concrete Japanese
creator workflow.

## Features

- Pair same-base-name `.wav` and `.txt` files.
- Measure audio duration with the Web Audio API.
- Generate valid SRT timestamps with millisecond formatting.
- Manual timing adjustment mode.
- Target-duration automatic adjustment mode.
- Frame-rate-aware timestamp rounding.
- Download `output.srt` directly from the browser.
- No backend and no upload of selected files.

## Quick start

Use the hosted app:

https://srt-wavtxt-tool.pages.dev/

Or run locally:

```bash
open index.html
```

For behavior closer to production static hosting:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## Input format

Prepare matching files with the same base name:

```text
001.wav
001.txt
002.wav
002.txt
003.wav
003.txt
```

Each `.txt` file is used as the subtitle text for the matching `.wav` file.
File names are sorted by browser-provided file name/path.

## VOICEVOX workflow

1. In VOICEVOX, enable text file export from the options menu.
2. Export audio from the file menu. VOICEVOX can write `.wav` files and matching
   `.txt` files into the same folder.
3. Open this app and select the folder or files.
4. Choose frame-rate and timing settings.
5. Generate and download the SRT file.
6. Import the `.wav` files and generated `.srt` into your video editor.

When using VOICEVOX outputs, follow the
[VOICEVOX terms](https://voicevox.hiroshiba.jp/term/) and the terms for each
voice library. VOICEVOX usage generally requires credit notation.

## Privacy and security

Selected files are processed in the browser. The app does not upload audio,
scripts, or generated SRT files to an application server.

Security-sensitive areas are documented in [SECURITY.md](SECURITY.md):

- local file handling,
- DOM rendering of file names and text-derived data,
- Web Audio API decoding,
- SRT download generation,
- static hosting configuration.

## Maintenance

This repository is maintained as a small open-source utility.

- License: [MIT](LICENSE)
- Support guide: [SUPPORT.md](SUPPORT.md)
- Contributing guide: [CONTRIBUTING.md](CONTRIBUTING.md)
- Security policy: [SECURITY.md](SECURITY.md)
- Roadmap: [ROADMAP.md](ROADMAP.md)
- Changelog: [CHANGELOG.md](CHANGELOG.md)

Good contributions include browser compatibility fixes, accessibility
improvements, SRT timing edge-case fixes, and documentation for video-editor
workflows.

## Limitations

This tool does not support:

- speech recognition,
- transcription,
- translation,
- `.vvproj` / `.aisp` project-file parsing,
- guaranteed subtitle timing for every editor/export workflow,
- backend processing of user audio.

Generated subtitles should be checked in your video editor before publishing.

## 日本語概要

VOICEVOX などで書き出した連番の音声ファイル（`.wav`）とテキストファイル
（`.txt`）のペアから、ブラウザ上で SRT 字幕を生成する小さな静的ツールです。

選択したファイルはブラウザ内で処理され、アプリケーションのサーバーへ
アップロードされません。

### 主な機能

- 同名の `.wav` と `.txt` をペアにして解析
- Web Audio API を用いた音声長の自動計測
- 手動調整と自動調整の 2 モード
- フレームレートに合わせたタイムコード調整
- 生成した `.srt` ファイルのダウンロード

### 注意事項

- VOICEVOX 公式ツールではありません。
- VOICEVOX 本体、エンジン、コア、音声ライブラリ、キャラクター素材は含みません。
- 音声認識、文字起こし、翻訳、プロジェクトファイル解析は行いません。
- 生成された字幕は、動画編集ソフト上で最終確認してください。

## License

MIT License
