# Roadmap

This project is intentionally small. The near-term roadmap focuses on making
the browser-only workflow safer, easier to verify, and more useful for Japanese
voice-synthesis video production.

## Near term

- Add tiny synthetic fixtures for timing and SRT formatting checks.
- Add automated checks for timestamp ordering, overlap prevention, and invalid input handling.
- Improve drag-and-drop and folder-picker compatibility notes across major browsers.
- Add English documentation for non-Japanese users who use VOICEVOX or similar tools.
- Add screenshots or a short demo GIF to make the workflow easier to understand.

## Security and privacy

- Keep selected files in the browser; do not add server-side upload.
- Review DOM rendering paths for unsafe file-name or text insertion.
- Document any future network dependency before adding it.

## Out of scope

- Speech recognition.
- Translation.
- `.vvproj` or `.aisp` project-file parsing.
- Hosting or processing user audio on a backend service.
