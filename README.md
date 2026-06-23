# GCF - Graph Compact Format

Syntax highlighting for [GCF](https://gcformat.com), the AI-native wire format for structured data. 50-92% fewer tokens than JSON. 100% comprehension on every frontier model.

## Features

- Full syntax highlighting for `.gcf` files
- Supports both **generic** and **graph** profiles
- Highlights all GCF constructs:
  - **Headers:** `GCF profile=generic`, `GCF profile=graph tool=...`
  - **Section headers:** `## name [N]{field1,field2}`
  - **Flattened path columns:** `"customer>name"`, `"billing>address>city"` (v3.2)
  - **Summary trailers:** `##! summary counts=N,M`
  - **Comments:** `# comment text`
  - **Symbol IDs:** `@0`, `@1`, `@123`
  - **Edge notation:** `@0<@1 calls`
  - **Key-value pairs:** `key=value`
  - **Scalars:** numbers, booleans (`true`/`false`), null (`-`), absent (`~`)
  - **Quoted strings:** `"hello world"` with escape sequences
  - **Pipe separators:** tabular row delimiters
  - **Attachments:** `^`, `^{fields}`, `.fieldname {}`

## Installation

### From Marketplace

Search for "GCF" in the VS Code Extensions panel, or:

```bash
ext install blackwell-systems.gcf-vscode
```

### From VSIX (local install)

1. Download the `.vsix` file from the [releases page](https://github.com/blackwell-systems/gcf-vscode/releases)
2. In VS Code, open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`)
3. Run **Extensions: Install from VSIX...**
4. Select the downloaded `.vsix` file

## What is GCF?

GCF (Graph Compact Format) is the AI-native wire format for structured data. It encodes any structured data using 50-92% fewer tokens than JSON with 100% comprehension on every frontier model. Validated across 2,400+ LLM evaluations, 11 models, and 43 billion+ lossless round-trips.

- **Generic profile:** Lossless round-trip encoding for any structured data (JSON, YAML, TOML, CSV, MessagePack)
- **Graph profile:** Specialized encoding for code graphs with symbol IDs, edges, and distance groups

Learn more at [gcformat.com](https://gcformat.com) or read the [specification](https://github.com/blackwell-systems/gcf/blob/main/SPEC.md).

## License

MIT. Copyright (c) 2026 Blackwell Systems.
