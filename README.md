# Repolex Knowledge Graph of repolex-ai/git-lex-kit-pan

RDF knowledge graph data for [repolex-ai/git-lex-kit-pan](https://github.com/repolex-ai/git-lex-kit-pan), parsed by [repolex](https://repolex.ai).

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
lexq download repolex-ai/git-lex-kit-pan
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e2458eccc41248a1fffd82686add31fe385c6c98
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── e2458eccc41248a1fffd82686add31fe385c6c98.nq.gz
│   └── repolex
│       └── e2458eccc41248a1fffd82686add31fe385c6c98
│           └── chunk-001.nq.gz
├── blob
│   ├── 69e67287227325f7b6c9f9608fc05195ffe77a04.nq.gz
│   └── 8775eec771c6298e72d653aa1e5bebc5d42c3e6c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e2458eccc41248a1fffd82686add31fe385c6c98.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 9 files
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

[repolex-ai/git-lex-kit-pan](https://github.com/repolex-ai/git-lex-kit-pan)

---
*Parsed on 2026-09-24 by [repolex](https://repolex.ai)*
