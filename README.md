# Repolex Knowledge Graph of ibis-project/ibis-dask

RDF knowledge graph data for [ibis-project/ibis-dask](https://github.com/ibis-project/ibis-dask), parsed by [repolex](https://repolex.ai).

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
rlex download ibis-project/ibis-dask
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 30af5be5a2a8531d37f9c7d0f25a89e52b00ad80
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 30af5be5a2a8531d37f9c7d0f25a89e52b00ad80
│           └── chunk-001.nq.gz
├── blob
│   ├── 180486fbce140c4c404423cbd12d4314ff54cfd6.nq.gz
│   ├── 22bdd22d6bc123059abefa12d1e343c122a5be5c.nq.gz
│   ├── 25b27fb84668275975e4bcd011cba4bd1c3e064e.nq.gz
│   ├── 2ee0eff0eace99492afbfefed2a85b6395e5f128.nq.gz
│   ├── 31f66dffc531eadc354e521bbd2161936ed61060.nq.gz
│   ├── 327ebfdca60e050bf1f24c10a765a0175438ac5b.nq.gz
│   ├── 338b8d229f3e38526fa7d97d04295784972ede0f.nq.gz
│   ├── 3f44de48bc4263a5cdbe2f8b524ae5ef627649fb.nq.gz
│   ├── 541c9ec60fb4a116139f0c90d8b247b1efe07350.nq.gz
│   ├── 7a34bf769ded08da48c17c6d116ebb46036d71e8.nq.gz
│   ├── 963a7ee87a657134236c7c3701fda9bddb004f60.nq.gz
│   ├── 9e0afac66d74896a65efc979d154b7b916046df2.nq.gz
│   ├── a81c8ee121952cf06bfaf9ff9988edd8cded763c.nq.gz
│   ├── b27293eab196374561c9ac6e17bb07dabe9783c4.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 30af5be5a2a8531d37f9c7d0f25a89e52b00ad80.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 24 files
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

[ibis-project/ibis-dask](https://github.com/ibis-project/ibis-dask)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
