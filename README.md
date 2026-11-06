# Repolex Knowledge Graph of sphinx-contrib/sqlalchemyviz

RDF knowledge graph data for [sphinx-contrib/sqlalchemyviz](https://github.com/sphinx-contrib/sqlalchemyviz), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/sqlalchemyviz
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0abac04599bb8477a9059def1ff333701a2a1891
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0abac04599bb8477a9059def1ff333701a2a1891
│           └── chunk-001.nq.gz
├── blob
│   ├── 09269fd7e96ca3d4778ca888a8293aedbf9ed551.nq.gz
│   ├── 1a72e21791ba330bf27f5f95ad98414e9a8769e6.nq.gz
│   ├── 86c3c123b4538671cac58c130a58b4827be307f5.nq.gz
│   ├── 8e7e2bc0d26ebc39199523caf9850ff62f3d650a.nq.gz
│   ├── 991514b3eebbb09394a9e6b94d8db2af500b0c01.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── bef2b783d3a171545d641d272e06b32d6dbbe3a3.nq.gz
│   ├── bfb9f4b5e992f8af7ca8153e93dab5c67e47976f.nq.gz
│   └── bfdbe9ac05d69ac822cc31a082bef4a3b183e2e3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0abac04599bb8477a9059def1ff333701a2a1891.nq.gz
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

[sphinx-contrib/sqlalchemyviz](https://github.com/sphinx-contrib/sqlalchemyviz)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
