# GCF: The AI-Native Wire Format

**50-92% fewer tokens than JSON. 100% comprehension on every frontier model. Zero training required.**

GCF (Graph Compact Format) replaces JSON as the data encoding between your tools and your LLM. Same data, dramatically fewer tokens, better model accuracy. This extension adds syntax highlighting for `.gcf` files in VS Code.

## Why GCF?

Every time an MCP server, agent, or tool sends structured data to an LLM, JSON wastes 52% of tokens on repeated field names and 29% on structural characters. At 500 rows, 81% of JSON tokens carry zero information.

GCF declares field names once in a header. Rows are positional pipe-separated values. Nested objects flatten into path columns (`"customer>name"`). The result:

```
GCF profile=generic
## orders [3]{id,"customer>name","customer>email",total,status}
ORD-1|Alice|alice@co.com|99.99|shipped
ORD-2|Bob|bob@co.com|49.99|pending
ORD-3|Carol|carol@co.com|29.99|processing
```

vs the equivalent JSON (3x more tokens):

```json
[{"id":"ORD-1","customer":{"name":"Alice","email":"alice@co.com"},"total":99.99,"status":"shipped"},
 {"id":"ORD-2","customer":{"name":"Bob","email":"bob@co.com"},"total":49.99,"status":"pending"},
 {"id":"ORD-3","customer":{"name":"Carol","email":"carol@co.com"},"total":29.99,"status":"processing"}]
```

## The numbers

- **50-92%** fewer tokens than JSON (varies by data complexity and session reuse)
- **100% comprehension** on every frontier model (Claude, GPT-5.5, Gemini, Grok)
- **15/16 wins** vs TOON across 16 real-world datasets
- **43 billion+** lossless round-trips verified across 17 serialization formats
- **2,400+** LLM evaluations across 11 models, 3 providers
- **Zero training.** Models read GCF natively. No fine-tuning, no few-shot examples.

## Syntax highlighting

This extension highlights all GCF constructs:

- **Headers:** `GCF profile=generic`, `GCF profile=graph tool=...`
- **Section headers:** `## name [N]{field1,field2}`
- **Flattened paths:** `"customer>name"`, `"billing>address>city"`
- **Tabular rows:** pipe-separated values with positional columns
- **Attachments:** `^`, `^{fields}`, `.fieldname {}`
- **Graph symbols:** `@0 fn pkg.Auth 0.78 lsp`
- **Edges:** `@0<@1 calls`
- **Scalars:** numbers, booleans, null (`-`), absent (`~`), quoted strings
- **Comments:** `# comment text`

## Get started

```bash
pip install gcf-python                    # Python
npm install @blackwell-systems/gcf        # TypeScript
go get github.com/blackwell-systems/gcf-go  # Go
cargo add gcf                             # Rust
```

Or wrap any existing MCP server with zero code changes:

```bash
pip install gcf-proxy
```

**Documentation:** [gcformat.com](https://gcformat.com)
**Playground:** [gcformat.com/playground](https://gcformat.com/playground.html)
**Specification:** [Spec v3.2 Stable](https://github.com/blackwell-systems/gcf/blob/main/SPEC.md)
**Benchmarks:** [gcformat.com/guide/benchmarks](https://gcformat.com/guide/benchmarks.html)

## Adopted by

[Speakeasy](https://speakeasy.com) (customers: Google, Verizon, Mistral AI, DocuSign, Vercel) · [OmniRoute](https://omniroute.online) (6.1K stars) · [NeuroNest](https://neuronest.cc) · [Open Data Products SDK](https://opendataproducts.org/sdk/) (Linux Foundation) · [and more](https://gcformat.com/ecosystem/adopters.html)

## License

MIT. Copyright (c) 2026 Blackwell Systems.
