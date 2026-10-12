# Repolex Knowledge Graph of datasette/datasette-public

RDF knowledge graph data for [datasette/datasette-public](https://github.com/datasette/datasette-public), parsed by [repolex](https://repolex.ai).

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
rlex download datasette/datasette-public
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 15585d8c79e9757b792b9a8d6d331f0df354a15e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 15585d8c79e9757b792b9a8d6d331f0df354a15e
│           └── chunk-001.nq.gz
├── blob
│   ├── 0821c7b6e240b0f9397d80795e4b16e546097e9a.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 29dafe9560c8491b19e61f9b0a1072ff8c7cdb4d.nq.gz
│   ├── 488704f0a578a62a2102486d6cc8677023793024.nq.gz
│   ├── 7b05bd35451ea04f72c20174c94c3624510f22ae.nq.gz
│   ├── 9500443bb3eb4c2e35a6440087883ccfb5ccbc94.nq.gz
│   ├── ac7d9862d4238dd58300f8b85dea7491e3962353.nq.gz
│   ├── d0d5ce3ee8fa6494d61b4f902ee7d8de943e1b36.nq.gz
│   └── d7591bf9f9c1c229954ce717ae5ec151f99585c5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 15585d8c79e9757b792b9a8d6d331f0df354a15e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
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

[datasette/datasette-public](https://github.com/datasette/datasette-public)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
