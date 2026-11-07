# Repolex Knowledge Graph of litestar-org/advanced-alchemy-docs-preview

RDF knowledge graph data for [litestar-org/advanced-alchemy-docs-preview](https://github.com/litestar-org/advanced-alchemy-docs-preview), parsed by [repolex](https://repolex.ai).

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
rlex download litestar-org/advanced-alchemy-docs-preview
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5f5be5187345e11f4591a4c32103fa7ee3637fa1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5f5be5187345e11f4591a4c32103fa7ee3637fa1
│           └── chunk-001.nq.gz
├── blob
│   ├── 02813e67a101ef920c9d907512e285f0c19f8ddd.nq.gz
│   ├── 68bc17f9ff2104a9d7b6777058bb4c343ca72609.nq.gz
│   ├── a7052bbc525b89b30dd43a7ab7d75d50ad97fc70.nq.gz
│   ├── aff5b386a12f758f00f1946676c798be15904b8b.nq.gz
│   └── b1bdf40960e1246b63b8aa02c6aa5e8e5551783e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5f5be5187345e11f4591a4c32103fa7ee3637fa1.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 12 files
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

[litestar-org/advanced-alchemy-docs-preview](https://github.com/litestar-org/advanced-alchemy-docs-preview)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
