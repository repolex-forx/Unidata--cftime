# Repolex Knowledge Graph of Unidata/cftime

RDF knowledge graph data for [Unidata/cftime](https://github.com/Unidata/cftime), parsed by [repolex](https://repolex.ai).

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
rlex download Unidata/cftime
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 211e91f18fdb59f6030a10b8af10b84bdff81a2a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 211e91f18fdb59f6030a10b8af10b84bdff81a2a
│           └── chunk-001.nq.gz
├── blob
│   ├── 0bea7d531cfd4a5c20fe15fce31c874f060f21cd.nq.gz
│   ├── 18513cff02ea20eede7048217b18a6b378828bb2.nq.gz
│   ├── 18d67320069085c2c8f043951bd850b998ddb34e.nq.gz
│   ├── 24975db9f71af81d83a39b65a733d6a59496212c.nq.gz
│   ├── 2841aabea86a8918e07df0f69dc466a8e2efcb3d.nq.gz
│   ├── 2a65c5e553080d0b3c200163d5d0ae9d83e2de2d.nq.gz
│   ├── 2b23c8ae0d60ec886fe82f441785f6dc8253c048.nq.gz
│   ├── 2bb2504d2fbdc910ab4001dd206a9f090d973c65.nq.gz
│   ├── 4589d16ef1c3f7e5eb8a8faee3ae723163c42f7d.nq.gz
│   ├── 4c175fa4a7adf2931f655c270d8a9677ddde1f37.nq.gz
│   ├── 60ed60dac300a073aaee2565db10c0a3ae9b49dc.nq.gz
│   ├── 7415136740989447afab92b7efc0948a1a819dc2.nq.gz
│   ├── 7c93d26dc4f6ac8a360f175554b6b2d69d488f10.nq.gz
│   ├── 8607e82f30406774bbdd408464074c221c6baa77.nq.gz
│   ├── 8ee8748bbd84f6b089ae59d923b65b0f273455cd.nq.gz
│   ├── 9142c861c34a35f3b6b6a495e77698b241f3a239.nq.gz
│   ├── 9eea98ed8b25848deb140859c4d059a6040b336e.nq.gz
│   ├── a3512ee21734379c8a3f6d716b03ab8aca8924ad.nq.gz
│   ├── ae45934387f82aa34f6299ae3a8e6807ef7204b8.nq.gz
│   ├── af637544ad2d95f8135b80f3a19237f8dc0cc7f5.nq.gz
│   ├── b1347bb1d2374f9897f83264d4ebb6d228fcce48.nq.gz
│   ├── c3278e4916cd73004aa4c5f134e0f979573b5557.nq.gz
│   ├── c954d5a9845a07f3d1a34b9389efdbd42af09ea3.nq.gz
│   ├── cca96131a297ace00560d1de3ac9ef1697fcf195.nq.gz
│   ├── dc43bf5fe2725535ccc06c1741f2ec8a864bfc35.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 211e91f18fdb59f6030a10b8af10b84bdff81a2a.nq.gz
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

[Unidata/cftime](https://github.com/Unidata/cftime)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
