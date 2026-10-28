# Repolex Knowledge Graph of explosion/ellf-recipes

RDF knowledge graph data for [explosion/ellf-recipes](https://github.com/explosion/ellf-recipes), parsed by [repolex](https://repolex.ai).

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
rlex download explosion/ellf-recipes
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4d7b28a5766a0aaf47980ed33e7e6896ff14b03e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4d7b28a5766a0aaf47980ed33e7e6896ff14b03e
│           └── chunk-001.nq.gz
├── blob
│   ├── 03107b902630881c27005b9e4d912854bb667609.nq.gz
│   ├── 1dfeacce7f53447b7c3be2a6534376227180e8fb.nq.gz
│   ├── 26b96fe62dd278007ad1cbb2c517578c5c6cb39c.nq.gz
│   ├── 2c875477ce59c6cf02e9ce2d056387ac465a30c7.nq.gz
│   ├── 43639ea11bc7c98e0debf82824e787eeaab0bc62.nq.gz
│   ├── 44d0eb2289e090446ccacd28c3e23420249bd5d3.nq.gz
│   ├── 5f0b99d2f3fc6cf9ce4c34e378984709de86efd2.nq.gz
│   ├── 6085f6ff761784d025e190a6e4edb8cf94484c73.nq.gz
│   ├── 60e5fded25c5944f8b941628473be5149273b45b.nq.gz
│   ├── 6112993ffd82d415aefe756d67d243fd3c2b4167.nq.gz
│   ├── 6d0ab7bbda82834e1c708c9a0a7cb70df206a346.nq.gz
│   ├── 80c615e61692baecfc10afccaf7a15b17a70b15c.nq.gz
│   ├── 91ae044adaa43086982b1adef310e6ac8658304c.nq.gz
│   ├── a171560752f8525113c4dc7b1e72a24e3fafa019.nq.gz
│   ├── a4823eb7694d805602207c1cd4a8162596d9078e.nq.gz
│   ├── ab4da1a3c5b977cf440964eaaeadced5be5e1a90.nq.gz
│   ├── c1bc0b150dc0ff693112edd2d1e48824b1b2eef6.nq.gz
│   ├── cfd008f25cdb5bf143f8638206a61bc3a38de48f.nq.gz
│   ├── d3f4ae6a289290be9774ed6f4b460548db0ffc59.nq.gz
│   ├── d888e9c5e300b207463bf0d06fa2cdefce5399e9.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4d7b28a5766a0aaf47980ed33e7e6896ff14b03e.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 27 files
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

[explosion/ellf-recipes](https://github.com/explosion/ellf-recipes)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
