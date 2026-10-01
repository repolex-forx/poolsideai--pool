# Repolex Knowledge Graph of poolsideai/pool

RDF knowledge graph data for [poolsideai/pool](https://github.com/poolsideai/pool), parsed by [repolex](https://repolex.ai).

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
rlex download poolsideai/pool
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fcabc59ff67810ecec5429ec9d45fa1dda6c1136
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── fcabc59ff67810ecec5429ec9d45fa1dda6c1136.nq.gz
│   └── repolex
│       └── fcabc59ff67810ecec5429ec9d45fa1dda6c1136
│           └── chunk-001.nq.gz
├── blob
│   ├── 552d378ccb678ee977ab3466b1c118f3e18ea6cd.nq.gz
│   ├── 7bee63541f1035275265a554e85ade5e66965e1b.nq.gz
│   └── e4887bd7a0176b13c9cf663375dedfbe1ae3a748.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── fcabc59ff67810ecec5429ec9d45fa1dda6c1136.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 12 files
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

[poolsideai/pool](https://github.com/poolsideai/pool)

---
*Parsed on 2026-10-01 by [repolex](https://repolex.ai)*
