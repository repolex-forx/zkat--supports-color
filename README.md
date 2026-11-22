# Repolex Knowledge Graph of zkat/supports-color

RDF knowledge graph data for [zkat/supports-color](https://github.com/zkat/supports-color), parsed by [repolex](https://repolex.ai).

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
rlex download zkat/supports-color
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 26ad8d206ad01ba7d6b4ad10d52f8f584aa68ec6
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 26ad8d206ad01ba7d6b4ad10d52f8f584aa68ec6.nq.gz
│   └── repolex
│       └── 26ad8d206ad01ba7d6b4ad10d52f8f584aa68ec6
│           └── chunk-001.nq.gz
├── blob
│   ├── 17dc3b8a02b8ebc15a6a61fc61a7290deb1ade63.nq.gz
│   ├── 1b83b43660bc201f6db5af13681a8013a89b63e2.nq.gz
│   ├── 39fd9ad7fae1fe29900d86a357aafefa8c29e2a3.nq.gz
│   ├── 42503d784fe5e6ea49993b9567be1452959e4154.nq.gz
│   ├── 48cbe2966fc00e82204a14c38b7365ab3af1c701.nq.gz
│   ├── 545f464b21a29953bbd564289a029dc157a10477.nq.gz
│   ├── 850f4631d329d487dfac871e08b9d9b6d9fe9594.nq.gz
│   ├── 86d5dfee9df526a319a32d4829664296b10a39d4.nq.gz
│   ├── 96ef6c0b944e24fc22f51f18136cd62ffd5b0b8f.nq.gz
│   ├── 9e9c0406eda47106f627aefe93a5b3e1403f04b8.nq.gz
│   ├── c0753b02f341b1d60cc7e6d76192422868fad1f7.nq.gz
│   └── e52e61f844e85d51e344cdd9a44c274c0d9b3880.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 26ad8d206ad01ba7d6b4ad10d52f8f584aa68ec6.nq.gz
├── filetree
│   └── 26ad8d206ad01ba7d6b4ad10d52f8f584aa68ec6.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 22 files
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

[zkat/supports-color](https://github.com/zkat/supports-color)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
