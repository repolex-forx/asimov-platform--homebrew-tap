# Repolex Knowledge Graph of asimov-platform/homebrew-tap

RDF knowledge graph data for [asimov-platform/homebrew-tap](https://github.com/asimov-platform/homebrew-tap), parsed by [repolex](https://repolex.ai).

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
lexq download asimov-platform/homebrew-tap
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   ├── 2fd52103af3873b94830d0f7a1589a811748cfcc
│   │   │   └── chunk-001.nq.gz
│   │   └── 2fd52103af3873b94830d0f7a1589a811748cfcc.nq.gz
│   ├── lsp
│   │   └── 2fd52103af3873b94830d0f7a1589a811748cfcc.nq.gz
│   └── repolex
│       ├── 2fd52103af3873b94830d0f7a1589a811748cfcc
│       │   └── chunk-001.nq.gz
│       └── 2fd52103af3873b94830d0f7a1589a811748cfcc.nq.gz
├── blob
│   ├── 14fb7a7bcedaf6797cf18a584fafb8b6f4762929.nq.gz
│   ├── 1c13c35aff44bf07e46c086a86daf066d5fb9abf.nq.gz
│   ├── 34da9c321a3ff2c713f9e9f062d272747cc7ecc4.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ee66e82c9b5d67f612c9a31fe561120a2eb2f71c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 2fd52103af3873b94830d0f7a1589a811748cfcc.nq.gz
├── filetree
│   └── 2fd52103af3873b94830d0f7a1589a811748cfcc.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 16 files
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

[asimov-platform/homebrew-tap](https://github.com/asimov-platform/homebrew-tap)

---
*Parsed on 2026-04-15 by [repolex](https://repolex.ai)*
