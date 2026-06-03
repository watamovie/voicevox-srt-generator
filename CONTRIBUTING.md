# Contributing

Thank you for considering a contribution to SRT Generator for VOICEVOX.

This is a small static web tool for generating SRT subtitle files from matching
`.wav` and `.txt` exports. The project intentionally stays browser-only: user
files must be processed locally and must not be uploaded to an application
server.

## Good first contributions

- Browser compatibility fixes for file selection, drag and drop, and Web Audio API handling.
- Accessibility improvements for keyboard operation, focus order, labels, and contrast.
- More robust SRT timing behavior around frame-rate rounding and edge cases.
- Documentation improvements for VOICEVOX workflows and video-editor import steps.
- Regression test cases using tiny synthetic `.wav` fixtures and matching `.txt` files.

## Development

No build step is required.

```bash
open index.html
```

For browser behavior closer to production, use a local static server:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`.

## Pull request checklist

- Keep the app static: do not add a backend or file-upload path.
- Do not commit user-generated `.wav`, `.txt`, or `.srt` files unless they are tiny,
  synthetic test fixtures with a clear license.
- Test with at least one matching `.wav`/`.txt` pair and one mismatched file set.
- Confirm generated subtitles still use valid SRT timestamp formatting.
- Update `README.md` when changing user-visible behavior.

## Reporting issues

Please include:

- Browser and OS.
- Whether files were selected by file picker, folder picker, or drag and drop.
- A minimal description of file names and counts.
- Expected behavior and actual behavior.

Do not attach private audio or script files to public issues.
