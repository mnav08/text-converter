# Project Brief: Text Converter

## Purpose

A personal, browser-based tool that converts between text formats, one file at a time.

## Supported Conversions

- TXT → MD
- TXT → HTML
- MD → HTML
- HTML → MD
- Same-format input (e.g. MD → MD) is not offered

## Input

- Paste into a text box
- Upload via file picker or drag-and-drop (`.txt`, `.md`, `.html`)
- Input format is auto-detected from the file extension, with a manual override for pasted text

## Output

- Read-only output box with the converted result
- **Copy to clipboard** button with brief "Copied" feedback
- **Download** button (`.md` or `.html`)
- No live preview. Conversion runs on a "Convert" button click.

## Design

- Minimal and clean: single centered column, generous whitespace, one accent color
- Dark mode follows the system setting, with a manual toggle that is remembered between visits
- Responsive, so it works on phone and desktop

## Tech Stack

- One `index.html` with vanilla JS and inline CSS
- Turndown + GFM plugin (HTML → MD)
- marked (MD → HTML)
- DOMPurify (sanitizes HTML input and output)
- Custom function for TXT → MD/HTML
- All libraries are inlined into the file (no CDN), so it works fully offline

## Hosting

- GitHub Pages: push `index.html` to a repo and enable Pages
- Everything runs client-side, so files are never uploaded anywhere
- Works offline: save the page (or the `index.html` file) and open it locally with no internet

## Out of Scope (for now)

Batch/ZIP, live preview, conversion options, other formats (`.docx`, PDF)

## Decisions

- Libraries are bundled into the file rather than loaded from a CDN: works offline, at the cost of a larger file (roughly 100-200 KB).
