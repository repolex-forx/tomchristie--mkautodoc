# Repolex Knowledge Graph of tomchristie/mkautodoc

RDF knowledge graph data for [tomchristie/mkautodoc](https://github.com/tomchristie/mkautodoc), parsed by [repolex](https://repolex.ai).

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
lexq download tomchristie/mkautodoc
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ad41abc4a94c4d63347e808ce6ca1dc0fb800bfb
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── ad41abc4a94c4d63347e808ce6ca1dc0fb800bfb.nq.gz
│   └── repolex
│       └── ad41abc4a94c4d63347e808ce6ca1dc0fb800bfb
│           └── chunk-001.nq.gz
├── blob
│   ├── 08f7ba871700a54ce4678ac2b0971ae11da213f3.nq.gz
│   ├── 14d21f630a0aa5d27ab60f930aceceb56ceb1aba.nq.gz
│   ├── 1afacd692fa3e2762178c5ef5f5e71bdf793e5bb.nq.gz
│   ├── 3a5d0edcf7ce5ced15a54b3a20ccdaa92d09c328.nq.gz
│   ├── 46003616fdad4f2917205f27615301015e56fd6c.nq.gz
│   ├── 4f90226113aad2ca1b5f384f85ad84b6a0ee9bc4.nq.gz
│   ├── 52dccac56e79979445dd7d05c4f9c4db276046d5.nq.gz
│   ├── 5dcbe9665f6e6dc654f2fc49ae97589cfb3b66b1.nq.gz
│   ├── 64fe7faa4bb37c5b6649d229b72c74c76aa72016.nq.gz
│   ├── 6999a47641543e199711926a7e6ec96df56b4995.nq.gz
│   ├── 8a7d94cc171598af2275aae2a2f9fe512cdee5c9.nq.gz
│   ├── 9295acb0fd96fc4a9234604ef921ce3c72ec28b3.nq.gz
│   ├── c364fb008d67e2860b70c4cf185f4ca4a0bbf8d5.nq.gz
│   ├── d2e50622bdd92c4709e4ce6f48790b3a4206d92c.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f41bb9b7ac4e918528f49703bf4ea0e509cc9969.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── ad41abc4a94c4d63347e808ce6ca1dc0fb800bfb.nq.gz
├── filetree
│   └── ad41abc4a94c4d63347e808ce6ca1dc0fb800bfb.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 26 files
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

[tomchristie/mkautodoc](https://github.com/tomchristie/mkautodoc)

---
*Parsed on 2026-09-15 by [repolex](https://repolex.ai)*
