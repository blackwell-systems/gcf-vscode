# GCF - Graph Compact Format

Syntax highlighting for [GCF](https://betterthanjson.com), the AI-native wire format for structured data. 71% fewer tokens than JSON.

![GCF Syntax Highlighting](assets/screenshot-placeholder.png)

## Features

- Full syntax highlighting for `.gcf` files
- Supports both **generic** and **graph** profiles
- Highlights all GCF constructs:
  - **Headers:** `GCF profile=generic`, `GCF profile=graph tool=...`
  - **Section headers:** `## name`, `## name [N]{field1,field2}`
  - **Summary trailers:** `##! summary counts=N,M`
  - **Comments:** `# comment text`
  - **Symbol IDs:** `@0`, `@1`, `@123`
  - **Edge notation:** `@0<@1 calls`, `@1>@0 references`
  - **Key-value pairs:** `key=value`
  - **Scalars:** numbers, booleans (`true`/`false`), null (`-`), absent (`~`)
  - **Quoted strings:** `"hello world"` with escape sequences
  - **Pipe separators:** tabular row delimiters
  - **Attachments:** `^`, `^{fields}`, `.fieldname {}`

## Installation

### From VSIX (local install)

1. Download the `.vsix` file from the [releases page](https://github.com/blackwell-systems/gcf-vscode/releases)
2. In VS Code, open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`)
3. Run **Extensions: Install from VSIX...**
4. Select the downloaded `.vsix` file

### From Marketplace

Search for "GCF" in the VS Code Extensions panel.

### From source

```bash
git clone https://github.com/blackwell-systems/gcf-vscode.git
cd gcf-vscode
npm install -g @vscode/vsce
vsce package
code --install-extension gcf-vscode-0.1.0.vsix
```

## What is GCF?

GCF (Graph Compact Format) is a token-optimized wire format designed for LLM tool responses. It encodes structured data (objects, arrays, tables, graphs) using 71% fewer tokens than JSON at scale.

- **Generic profile:** Lossless round-trip encoding for any JSON-compatible data
- **Graph profile:** Specialized encoding for code graphs with symbol IDs and edges

Learn more at [betterthanjson.com](https://betterthanjson.com) or read the [specification](https://github.com/blackwell-systems/gcf/blob/main/SPEC.md).

## License

MIT. Copyright (c) 2026 Blackwell Systems.
