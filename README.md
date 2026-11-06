# Repolex Knowledge Graph of sphinx-contrib/doxylink

RDF knowledge graph data for [sphinx-contrib/doxylink](https://github.com/sphinx-contrib/doxylink), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/doxylink
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8e8046908004d7953d05acb26558376b376ee267
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8e8046908004d7953d05acb26558376b376ee267
│           └── chunk-001.nq.gz
├── blob
│   ├── 0343107724f705cf1961e434e6d183435714de1a.nq.gz
│   ├── 09e3f5b69ca1c6c52f75e72014b3fa119d6ea85a.nq.gz
│   ├── 0a7fc97b59bbf4767a6018ab83c4a88978413e42.nq.gz
│   ├── 11cde083cb208f472853fb3cea2150ba67c83a93.nq.gz
│   ├── 1af5737cc5853e8b1961888dad20a77385bb38aa.nq.gz
│   ├── 1c2f37e51b128ee0e1778db1384c5c67ac0bb7f7.nq.gz
│   ├── 1e5f6933ab38e5b7a0579725bdb6b22db7ff5dec.nq.gz
│   ├── 2540a86f4eb3a274e3895b9a8801839e9b36cf6d.nq.gz
│   ├── 265e04fa3753964fbe5de5afe85ee903677233a3.nq.gz
│   ├── 31d6c2713e0387ac58a35ddddebc3fbeef2f51e4.nq.gz
│   ├── 39c150db9eb6f461f775187786bb7680da7f4c87.nq.gz
│   ├── 3a0bb85aa6a68bc67cc5b51b100673b0dfbecb4d.nq.gz
│   ├── 447e2a325a4b48f07990b73caad95f0f92471c79.nq.gz
│   ├── 497b4288e2009295e8acc3b33659e76058231e0e.nq.gz
│   ├── 4acbd54f97fd0d49f1db4f1470324c27c0452320.nq.gz
│   ├── 55483332ed1dc3a42766ff0dfb6f3f2fd320adc2.nq.gz
│   ├── 55b1de865c0578f07b24a4702f8dbb676702c885.nq.gz
│   ├── 57ffe75eb32ae1f5a8c3cd682c2dcab15393951f.nq.gz
│   ├── 5eb817cefc2409ee6632bc368e24fec457189389.nq.gz
│   ├── 6c44bd60fd7113c5228edf7b2798ca1ef9dc15be.nq.gz
│   ├── 803806f02f2168856a9929e762c9f5a7d48fcae7.nq.gz
│   ├── 9ef69ac7b02d5cd29722633ef9e12ceca86cfa85.nq.gz
│   ├── b48d106c4f5308693e3a969c8dc61a64bdb1344c.nq.gz
│   ├── b72f8907d8ffc606e86815117bbc4ab02067a099.nq.gz
│   ├── beb73592958cca81d632b8936127b00b2d59ea88.nq.gz
│   ├── cafa79e01c359f96fb0a740192f2255c95ed30a8.nq.gz
│   ├── d9bf9326bcb38f1816d74e3b10dd618b97d7b078.nq.gz
│   ├── e0ae659b19cc47d6b96015aa04ac30537cf36ac2.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── fff1d8b05d1fc8eae851528676357ead3f9f6f7d.nq.gz
│   └── fffeb087be24c568c7ee09640ca70fb7c4a34e09.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8e8046908004d7953d05acb26558376b376ee267.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 39 files
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

[sphinx-contrib/doxylink](https://github.com/sphinx-contrib/doxylink)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
