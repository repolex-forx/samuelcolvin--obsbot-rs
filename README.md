# Repolex Knowledge Graph of samuelcolvin/obsbot-rs

RDF knowledge graph data for [samuelcolvin/obsbot-rs](https://github.com/samuelcolvin/obsbot-rs), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/obsbot-rs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e8a17fb8f1499e2d964d25e8c5657e7da3372b20
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e8a17fb8f1499e2d964d25e8c5657e7da3372b20
│           └── chunk-001.nq.gz
├── blob
│   ├── 03590e95bbd185d17e80cd52b884b96df35bb0eb.nq.gz
│   ├── 041b45f6072d2f67327ee6c71835df6c564f07ec.nq.gz
│   ├── 079a2cf966b953207b1764038e547d570125e4d8.nq.gz
│   ├── 0c489d64708ed42a73b59d499a1a5aa6a73696f9.nq.gz
│   ├── 0f2eb267efbbe0a6708b215e03a5d3c0cf744ade.nq.gz
│   ├── 16d92db253d6685d291ecb9b38c2824edc3e4723.nq.gz
│   ├── 1e703e7c937986db0e67f007accc4b2ee8eb721e.nq.gz
│   ├── 1fb0a12d016ddc1f99f708e48dac3d69b651899e.nq.gz
│   ├── 2cfbc81dc0d1205963dc56eaac51092878a47985.nq.gz
│   ├── 335a5cf2a331ee22eabbb758984c9ee4aea8fd28.nq.gz
│   ├── 33949dda28eeac7d64d7264c1157141a9f60e7a9.nq.gz
│   ├── 3b618792e4070513060635d2ed0980b6445d0fcf.nq.gz
│   ├── 3d4b7d5efe1974a6503cc7bce30fdcd2404158f6.nq.gz
│   ├── 44669a4b2b3413e576c5aeb27ef8547888b28b81.nq.gz
│   ├── 590cbd1bc6eeea92b58d86d9de7a1b7d6133b339.nq.gz
│   ├── 59bb8fac894f3abedb6957637121c86dfb2becf2.nq.gz
│   ├── 5c6083ed62009bd74c635bab2bbd82da700760cc.nq.gz
│   ├── 61db75a17d4cb88098a096a3514f9324c06ac8dc.nq.gz
│   ├── 65c41beb149881f052d4afc46c7834ac53c0ce4a.nq.gz
│   ├── 74e9ec8ff942b5dbc8a68c990253c700f19ae240.nq.gz
│   ├── 8e47c6524120f56254d4cf99aa8f4ed432d43a2e.nq.gz
│   ├── 97893819576f5e84ae40225d654ab3506c04a376.nq.gz
│   ├── af3033ee381cffea909794be3193bc486a19a026.nq.gz
│   ├── b80b47fc8445e50015385fb146489ad94afbb77c.nq.gz
│   ├── beefed12fbdb23ba91611f4ebacd516b3b82f336.nq.gz
│   ├── ce356a28882af1be3b47afb17e59f632f3cd26d1.nq.gz
│   ├── de9730c5e9747be215921cae70ef7d5c7b0cc147.nq.gz
│   ├── e2c3d3d4c478e3aaa3d985a5f22774d9d44d3f12.nq.gz
│   ├── e7007f582aa139b16217fcb92fa1947f9c1f6603.nq.gz
│   └── eadcb64fb5c0968746bb15ab781c526cf020d5e1.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e8a17fb8f1499e2d964d25e8c5657e7da3372b20.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 36 files
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

[samuelcolvin/obsbot-rs](https://github.com/samuelcolvin/obsbot-rs)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
