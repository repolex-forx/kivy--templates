# Repolex Knowledge Graph of kivy/templates

RDF knowledge graph data for [kivy/templates](https://github.com/kivy/templates), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download kivy/templates
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 935165910a6ebf6186d30c9103e3e407a85ab8ab
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 935165910a6ebf6186d30c9103e3e407a85ab8ab
│           └── chunk-001.nq.gz
├── blob
│   ├── 0a91d8e9c00ccf4fe254a36536ea6227fa16a30e.nq.gz
│   ├── 1a4425fc6c3946e7c5bc5bad200d2d789e34f0dc.nq.gz
│   ├── 1a6e25a2c4b4a2cbe62ddcb847dd249c411b509b.nq.gz
│   ├── 1c75e1aef3eaaf29751e45ff99327aa3f0a89c69.nq.gz
│   ├── 22300778551fcf1315f27d2236411c99198fdcd7.nq.gz
│   ├── 315b59396726712ea515e284576436c29571b5e2.nq.gz
│   ├── 3714ddaa5c5f4094f3dd6da0298a193bbe7ecf82.nq.gz
│   ├── 4acb650ce4046cb73667e92923e5d74370d8d3ab.nq.gz
│   ├── 5113ca557e8d6745d62f8340a23531ad9ee9fd45.nq.gz
│   ├── 5995793db1dcb753c1c03df72e6ad8b2d094a397.nq.gz
│   ├── 5cc31689ad6fd6c4a2eb6d63a462eb6d2eae8e7d.nq.gz
│   ├── 6d7e8ed7ed64d47d3a5e31700628708414ebc8e2.nq.gz
│   ├── 72ee301740d3221113dfaf825fd2b482a1975c2c.nq.gz
│   ├── 8153ff41a00f943701fad813b64317a272242e17.nq.gz
│   ├── 8522e54660187ebaaae90d50af81f063df491724.nq.gz
│   ├── 8d74e9a6dc11c0b6b23046fc55b396025fa0fe32.nq.gz
│   ├── ab81dd1e866536a9ef817a9299fcdb80aa09e83d.nq.gz
│   ├── b87b8cee915b3702aaf281a73603d29fa8adb4f7.nq.gz
│   ├── c5ee90189eda4715e13e6b25835385c290dcf8a3.nq.gz
│   ├── cd102f83d12c174afb433002ce72f22e2569454a.nq.gz
│   ├── e582497cc08e5f7f6b3adac26aec152ec78f6273.nq.gz
│   ├── e6235465aba83c9480727b1cc970586b70baf973.nq.gz
│   ├── ecb9d8faee78ca776c5d44fa2cb053975dc7451b.nq.gz
│   ├── ee9c5c03848568558c87c64d01226f01897abd0b.nq.gz
│   ├── eec2427118afe29e689f553c56254c65e004d88f.nq.gz
│   └── f0818540647efd6c31a57b5e9cc12fc5d946273a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 935165910a6ebf6186d30c9103e3e407a85ab8ab.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[kivy/templates](https://github.com/kivy/templates)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
