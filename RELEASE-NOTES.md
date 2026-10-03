# Notepad Viewer Plus 0.4.0

Prerelease notes for maintainer and user evaluation — 2026-10-03.

## What is included

- Docked offline preview inside Notepad++.
- Markdown with syntax highlighting, math, and table of contents support.
- Mermaid and PlantUML diagrams rendered locally.
- Sanitized HTML and SVG, JSON/YAML/XML trees, CSV/TSV tables, OpenAPI documentation, images, and PDF viewing.
- Light/dark/system theme handling and a toolbar toggle.
- Exact-file delivery for images and PDF without passing their bytes through the renderer message bridge.

## Release assets

| Package | SHA-256 | Notes |
| --- | --- | --- |
| [NotepadViewerPlus-0.4.0-x64.zip](https://github.com/Duclevn/notepad-viewer-plus-releases/releases/download/v0.4.0/NotepadViewerPlus-0.4.0-x64.zip) | `0b671904ba1bc997b5cd8c7b62ea598b73fad8e97754b99d81d172eded2be747` | 64-bit Notepad++ |
| [NotepadViewerPlus-0.4.0-x86.zip](https://github.com/Duclevn/notepad-viewer-plus-releases/releases/download/v0.4.0/NotepadViewerPlus-0.4.0-x86.zip) | `a9ec08fe7daef0000f3a4f36c1a3833d0401913944b0b4deef879238ef2f57e2` | 32-bit Notepad++ |

Each ZIP contains the plugin DLL at the archive root, the renderer assets, and the generated third-party license inventory. ARM64 is unsupported.

## Validation completed

The candidate passed the renderer version check, TypeScript check, 71 renderer tests, production build, strict size gate, native Release builds and CTest for x64 and x86, CPack, and structural package validation for both architectures. The x64 package was observed in an isolated portable Notepad++ 8.9.8.1 host: startup stayed hidden, the preview docked, the initial floating window had a usable content area, saved floating geometry was restored, and the math regression fixture rendered at normal width.

The x86 package was also exercised in an isolated portable Notepad++ 8.9.8.1 host. In the official Plugin Admin debug workflow, installation, removal, and updating from the 0.3.0 x86 package to 0.4.0 completed with automatic restarts. The installed 0.4.0 payload matched all 61 files in the published x86 ZIP. Broader host/runtime coverage and settings-retention checks remain open.

## Known limitation and remaining review work

Widening a very narrow preview pane can leave some math clipped until the preview is refreshed. The current candidate also needs broader host/runtime, theme, PDF, OpenAPI network, image/SVG, toolbar/DPI, and clean installation coverage.

The original C++ and TypeScript source remains private. The package includes third-party notices, but the Notepad++ SDK/template header and host/plugin licensing question remains open in [issue #28](https://github.com/npp-plugins/plugintemplate/issues/28). These notes do not assert a GPL exception, an effective project license, or complete licensing clearance.
