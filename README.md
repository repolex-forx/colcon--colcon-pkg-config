# Repolex Knowledge Graph of colcon/colcon-pkg-config

RDF knowledge graph data for [colcon/colcon-pkg-config](https://github.com/colcon/colcon-pkg-config), parsed by [repolex](https://repolex.ai).

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
rlex download colcon/colcon-pkg-config
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 81d7fdf25794bb7d9e0e2235060696e1e03a31ba
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 81d7fdf25794bb7d9e0e2235060696e1e03a31ba
│           └── chunk-001.nq.gz
├── blob
│   ├── 0f17157ed42b486a0c57cbffddd97987a4844e6b.nq.gz
│   ├── 32f3ad179c26390ee9a2113236601e0e2b9ca3ff.nq.gz
│   ├── 495ec25264ed08f266f2567ae69a6d622dd4eca9.nq.gz
│   ├── 522c15599e2e2dc33e3741185c90802b792317c3.nq.gz
│   ├── aaedc097b2ab27302cb540cc06647304d32550b2.nq.gz
│   ├── bd7c8693b373f16474a10254e75b502ef8389f27.nq.gz
│   ├── be05d80c71a755cb02b8d6f955baa3058fe766bb.nq.gz
│   ├── c0c6f67ce2b5498e63b497aac08b25714f2596f7.nq.gz
│   ├── cc7b15e61260635e53080c7ad9ba7f2cb9ded87f.nq.gz
│   ├── ce0771b81a13bb16112a19383a8152c4092cd6e9.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── dffe460f162da9929178a7ce342532e7ba896425.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f2d0bdd3299ddfb81c077fc81f525c1573b4de09.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 81d7fdf25794bb7d9e0e2235060696e1e03a31ba.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 22 files
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

[colcon/colcon-pkg-config](https://github.com/colcon/colcon-pkg-config)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
