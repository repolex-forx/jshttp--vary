# Repolex Knowledge Graph of jshttp/vary

RDF knowledge graph data for [jshttp/vary](https://github.com/jshttp/vary), parsed by [repolex](https://repolex.ai).

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
lexq download jshttp/vary
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ca7edac6b919a45bf9e2c5cb6ba31c1790e9f046
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── ca7edac6b919a45bf9e2c5cb6ba31c1790e9f046.nq.gz
│   └── repolex
│       └── ca7edac6b919a45bf9e2c5cb6ba31c1790e9f046
│           └── chunk-001.nq.gz
├── blob
│   ├── 23d13de2a08832990667c5e3869743058dd837be.nq.gz
│   ├── 449c1e29c87cbcddbd903210b3903a4d5903df6c.nq.gz
│   ├── 62562b74a3b5a79e82ca417b02e0f597d85f5e2f.nq.gz
│   ├── 7eeefc33b66c055f211388c46d17b50c45db7c25.nq.gz
│   ├── 84441fbb5709262c2bfc9b5ff0166ad4f024a1b8.nq.gz
│   ├── 98718cd72b7b915c3e0f67f0411163b5022b9540.nq.gz
│   ├── ac37a83381cb2feb07af1c2c1be68650067cb2a1.nq.gz
│   ├── b509c88b36471944dbd4a1e03e6482ece473fa9e.nq.gz
│   ├── cc000b34684a1d0b03d4c4cb4fac3e1094a81eec.nq.gz
│   ├── e3578aadfd3a97c6ef9d74f46e07314d775c9c61.nq.gz
│   └── e689a8a94999df1630f3cfc573bb0c777b23f904.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── ca7edac6b919a45bf9e2c5cb6ba31c1790e9f046.nq.gz
├── filetree
│   └── ca7edac6b919a45bf9e2c5cb6ba31c1790e9f046.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 21 files
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

[jshttp/vary](https://github.com/jshttp/vary)

---
*Parsed on 2026-04-10 by [repolex](https://repolex.ai)*
