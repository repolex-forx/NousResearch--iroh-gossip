# Repolex Knowledge Graph of NousResearch/iroh-gossip

RDF knowledge graph data for [NousResearch/iroh-gossip](https://github.com/NousResearch/iroh-gossip), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/iroh-gossip
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 8e68fe0716fff25e962c5475a9840e14532aed7a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 8e68fe0716fff25e962c5475a9840e14532aed7a
│           └── chunk-001.nq.gz
├── blob
│   ├── 02bbb6de364e98711c06c60017c89ec4a16b6ccb.nq.gz
│   ├── 0de9680eb239af098fb399f205f2728ad1542958.nq.gz
│   ├── 0e6b809d0498b2b167b9a9c1c2440441be71bc64.nq.gz
│   ├── 130d3215d6bac1ad2f39385b1f0455148898279d.nq.gz
│   ├── 1b5c6d238c4bd29a3f5988f56dbe8c84fa1df525.nq.gz
│   ├── 204a310df12a15c151a2960793486e956d800bbb.nq.gz
│   ├── 22405d254746ba54025d19dbc96485b858d02317.nq.gz
│   ├── 28ccecdf049a6990c8a578500c6a26f37d158cf0.nq.gz
│   ├── 2d5f18dd41d651dc325cf4d6349130670109cc50.nq.gz
│   ├── 2f4457550a06bd368fe7da9eacd5ff31e20df34b.nq.gz
│   ├── 348c1b2e84113f0fd5069ea07656048251b4ee09.nq.gz
│   ├── 3881704396b8f3faa4ab2810f4fc2be5d87eebcd.nq.gz
│   ├── 409b571b89f93d00917d34ce5b46a8b540934976.nq.gz
│   ├── 4f0a061fb0432b6fc5e2db3cee1ba9bb9f7f3c3b.nq.gz
│   ├── 55837bd21e950975614cbfb27c742a7c24539ff5.nq.gz
│   ├── 56bc5da8e8a5b08551f68b10fe30f9edf09440fe.nq.gz
│   ├── 5af9c42e2fa50cca7d3fa4d65c6c10696341736a.nq.gz
│   ├── 5da1bb4275afe9f98d7a0eb90ebd28061f1d3077.nq.gz
│   ├── 5e641a14e4a058797396564a0b1a3db8213513cd.nq.gz
│   ├── 6cc5a1f3eef36f61df5fb9b10cc56638bd0bf679.nq.gz
│   ├── 6fe186034d467fcede352f0603d5eb0691aaa19c.nq.gz
│   ├── 7af71361aca7cbe6b4e89b8b02fde92bd398dcc0.nq.gz
│   ├── 8bc2cba3511ddb591b625cc106216d121c03f041.nq.gz
│   ├── a03c269416e625477189b7568cfb317b3da8775d.nq.gz
│   ├── a0d4901a781d80ef97272e70f70bace72a9cc998.nq.gz
│   ├── a1c6e1c0c73de6d63e7f78bfac405f7de407b54a.nq.gz
│   ├── afee382a3c2d0639056b380a693f1a5357876a88.nq.gz
│   ├── b4dc18381cd254a8e0b26fc5de7e515b2e078ea2.nq.gz
│   ├── be006de9a1ae3b9628e796c74277cd6d61e0a34a.nq.gz
│   ├── c16fa50115991186e5ca3e86f3e8dd786248c627.nq.gz
│   ├── c8d5e37f1f4b73d44c3cf8f26743b6272e8513a5.nq.gz
│   ├── cde63023fec1cdfab12aa647c83f18d82c077768.nq.gz
│   ├── e2db9284926852ff674979ca3aba5634c8a627d3.nq.gz
│   ├── e8b9757b8175cee3287ea01e6b09bd8e50ed676b.nq.gz
│   ├── e9e8bc20fbf53cfaccf90483088c8a86b72deeac.nq.gz
│   ├── ea8c4bf7f35f6f77f75d92ad8ce8349f6e81ddba.nq.gz
│   ├── f09adc5ee4f9ffe255bea93c0e4bc6e1d4458212.nq.gz
│   ├── f3c57ed7de1fa1a9978f4f3ff0e8e154fcd277f3.nq.gz
│   ├── f7302360457609c8fdde2fdc28a129f179bf003d.nq.gz
│   └── f78c38cc0906a631593cd503f38e2769e08e861d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 8e68fe0716fff25e962c5475a9840e14532aed7a.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 46 files
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

[NousResearch/iroh-gossip](https://github.com/NousResearch/iroh-gossip)

---
*Parsed on 2026-10-09 by [repolex](https://repolex.ai)*
