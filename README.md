# Repolex Knowledge Graph of boydgreenfield/query

RDF knowledge graph data for [boydgreenfield/query](https://github.com/boydgreenfield/query), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download boydgreenfield/query
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1a04a7c008541a730e3ea57e511195d3d4567b44
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 1a04a7c008541a730e3ea57e511195d3d4567b44.nq.gz
│   └── repolex
│       └── 1a04a7c008541a730e3ea57e511195d3d4567b44
│           └── chunk-001.nq.gz
├── blob
│   ├── 00a750d94dd063bf2bcadae045db660542a4fafa.nq.gz
│   ├── 03325b4af6654a42f26a4e27c9db39341b8da439.nq.gz
│   ├── 19e4b616bddb713b5b6ef8da1f67f5d8ea7aaecc.nq.gz
│   ├── 484a489a123d0df9c139d68fe67da86c161995ad.nq.gz
│   ├── 71937853991238ab655dc909291a1d137a7d27a6.nq.gz
│   ├── a4447934340f8b17c96dab81988860d231178d9b.nq.gz
│   ├── aadb704edf75f123fb2915d8991cc14d0d5c8486.nq.gz
│   ├── be0cca2d5c945b60c66a893765faf92f8cf5ff17.nq.gz
│   ├── c81e085aa390fddaca479a4a403895b64caf5197.nq.gz
│   ├── ca5561a49b28582e2373145c90945f8b55429314.nq.gz
│   ├── d5e6eff088dd80a4a8a7c60e2fe07ccc3cb03d02.nq.gz
│   ├── dde3895fc112ad34a839b2fed9210ac2288a959b.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ea4edec87142cbd1b4d7f7c8d6a67ee6fbab82b3.nq.gz
│   └── f6283a9cfb3205e7893f28b74111f875b5e9188c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 1a04a7c008541a730e3ea57e511195d3d4567b44.nq.gz
├── filetree
│   └── 1a04a7c008541a730e3ea57e511195d3d4567b44.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 25 files
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

## Source repository

[boydgreenfield/query](https://github.com/boydgreenfield/query)

---
*Parsed on 2026-04-13 by [repolex](https://repolex.ai)*
