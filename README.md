# Repolex Knowledge Graph of glue-viz/glue-standalone-apps

RDF knowledge graph data for [glue-viz/glue-standalone-apps](https://github.com/glue-viz/glue-standalone-apps), parsed by [repolex](https://repolex.ai).

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
rlex download glue-viz/glue-standalone-apps
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4e35d18fe6d1ff86ddb5feb02572f6cd60a3568b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4e35d18fe6d1ff86ddb5feb02572f6cd60a3568b
│           └── chunk-001.nq.gz
├── blob
│   ├── 1417696695452cb82e908ad5f98c478b432541d2.nq.gz
│   ├── 1f754be653a4fc9141b689a2e8f24ed538f25c72.nq.gz
│   ├── 2354e18ca789fb19d04321a41c41e6e947e220c2.nq.gz
│   ├── 29fec86c5702d3bdcfcc0cbebea46a6ca76d2ec0.nq.gz
│   ├── 2ad1e56d91df2f606faa70e1f8e1e49af739cc21.nq.gz
│   ├── 2dd359789e8218093e96aabb9cfff38113dd7620.nq.gz
│   ├── 348e313c21bbc692300096a6f980cfe914a695d0.nq.gz
│   ├── 3549062c96718005782e2a2c9d2712945f597f5b.nq.gz
│   ├── 38d785fd3a99d96eb6b0f0c0a3a6f866df905e3e.nq.gz
│   ├── 45e6dca51b06fac1d34eba5785973a85f6967933.nq.gz
│   ├── 47dcdf70c8d98f84990a627500213165c46ad59d.nq.gz
│   ├── 48f7bf5cece0e3d9b0c0d36bcfd1c00ac6fae3e2.nq.gz
│   ├── 4ca32bb60f0f0cc6882733c8cfa53b2b1206234d.nq.gz
│   ├── 64db6e5bda83ffa20d4e157f5fa96a72f19452ad.nq.gz
│   ├── 65999a62975429a0dd4e5c2b0c97285e1246023c.nq.gz
│   ├── 673584e1f54fe6fdd1063f970e0d7bf8e2e70091.nq.gz
│   ├── 833187db76bcf1b391499f8e38ef27127e3bfee9.nq.gz
│   ├── 9667dfec9784391fa7788dc6a4dce2b5b50fd682.nq.gz
│   ├── aaf4d5d492e9f8f5459faa39fceed2b636591a66.nq.gz
│   ├── aea3c2ddb6db987c6dee9decb2d8d3e379b0f500.nq.gz
│   ├── aef8cab18a6193c0254e490135dc6e5a99d73db7.nq.gz
│   ├── b038fb77c0cda6a271b89c03ce97800bc3b83468.nq.gz
│   ├── e6b7120da36ac8eee7727be4d3b3055cbfaf8bf0.nq.gz
│   ├── e7ec2bc50b177dd0b453bde0bca27c94263ace26.nq.gz
│   ├── f90ec456bd1f5350dc0480fa8bde27fc39ad4913.nq.gz
│   └── fbcac2a4a9ad3a3aa0e6415158f91540392be9c9.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4e35d18fe6d1ff86ddb5feb02572f6cd60a3568b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
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

[glue-viz/glue-standalone-apps](https://github.com/glue-viz/glue-standalone-apps)

---
*Parsed on 2026-10-16 by [repolex](https://repolex.ai)*
