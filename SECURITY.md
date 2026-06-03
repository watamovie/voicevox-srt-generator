# Security Policy

## Supported project scope

SRT Generator for VOICEVOX is a static browser app. It should not upload selected
audio, text, or generated subtitle files to an application server.

Security-sensitive areas include:

- Local file handling through file picker, folder picker, and drag and drop.
- Rendering file names and text-derived data in the DOM.
- Web Audio API decoding and duration handling.
- SRT download generation.
- Static hosting configuration.

## Reporting a vulnerability

If you find a vulnerability, please avoid posting exploit details publicly at
first. Open a GitHub issue with a minimal description and mark it as security
sensitive, or contact the maintainer through the GitHub profile:

https://github.com/watamovie

Please include:

- Affected browser and OS.
- Steps to reproduce.
- Impact: for example XSS, unintended network transmission, data exposure, or
  unsafe download behavior.
- Whether the issue requires specific file names, file contents, or user actions.

## Privacy expectation

The project goal is local-only processing. A security fix that introduces server
upload, analytics on file contents, or remote processing is out of scope unless
it is explicitly discussed and documented.
