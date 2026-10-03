# Notepad Viewer Plus 0.4.0

Notepad Viewer Plus is an offline, docked multi-format preview for Windows Notepad++. It can preview Markdown, math, Mermaid, PlantUML, HTML, SVG, JSON, YAML, XML, CSV/TSV, OpenAPI, images, and PDF files.

This is a prerelease evaluation package prepared for review of a proposed Notepad++ Plugin Admin entry. It is not yet included in Plugin Admin.

## Downloads

Download the evaluation packages:

- [64-bit package](https://github.com/Duclevn/notepad-viewer-plus-releases/releases/download/v0.4.0/NotepadViewerPlus-0.4.0-x64.zip) — SHA-256: `0b671904ba1bc997b5cd8c7b62ea598b73fad8e97754b99d81d172eded2be747`
- [32-bit package](https://github.com/Duclevn/notepad-viewer-plus-releases/releases/download/v0.4.0/NotepadViewerPlus-0.4.0-x86.zip) — SHA-256: `a9ec08fe7daef0000f3a4f36c1a3833d0401913944b0b4deef879238ef2f57e2`

Use the package matching the architecture shown by **Help → About Notepad++**. ARM64 is unsupported.

## Requirements

- Windows with a matching 64-bit or 32-bit Notepad++ installation.
- Microsoft Edge WebView2 Evergreen Runtime.
- Microsoft Visual C++ v14 Redistributable matching the plugin architecture.

The x64 package was observed in an isolated Notepad++ 8.9.8.1 host. The x86 package was built and structurally validated, but has not had live editor testing. No broader supported-version range is claimed by this prerelease.

## Manual installation

1. Close every Notepad++ window.
2. Extract the entire ZIP into `<Notepad++>\plugins\NotepadViewerPlus\`.
3. Confirm that `NotepadViewerPlus.dll` is directly in that directory and that the `assets\` directory is beside it.
4. Keep `THIRD-PARTY-LICENSES.txt` and the included notices with the package.
5. Restart Notepad++. Use **Plugins → Notepad Viewer Plus → Toggle Preview**, **Ctrl+Alt+P**, or the toolbar button.

Do not copy only the DLL with **Import plugin(s)**; the renderer assets are required. Close Notepad++ before upgrading or removing the plugin.

## Evaluation terms and source

The author makes these binaries available for free download, installation, and use for evaluation. The original C++ and TypeScript source repository remains private. This review statement is not an effective project license and grants no broader source or redistribution rights.

The broader proposed terms for free personal/business use and redistribution of complete unchanged packages remain conditional on the licensing clarification in [official template issue #28](https://github.com/npp-plugins/plugintemplate/issues/28). The package does not claim a GPL exception or complete licensing clearance. Third-party components retain their own licenses; their notices are included in each ZIP.

## Known limitation

Some math expressions can remain clipped after widening a very narrow preview pane. **Refresh Preview** or hide and show the preview to render the expression again.

The preview is offline by default. Remote navigation and remote definitions are blocked; an explicit remote-image setting can allow HTTPS images. PlantUML does not require a server or Java installation.

For evaluation reports, use the [release repository issue tracker](https://github.com/Duclevn/notepad-viewer-plus-releases/issues) and include the plugin version, Notepad++ version and architecture, WebView2 version, and a small non-sensitive example.
