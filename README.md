# Repolex Knowledge Graph of simonw/llm-openai-decisions

RDF knowledge graph data for [simonw/llm-openai-decisions](https://github.com/simonw/llm-openai-decisions), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/llm-openai-decisions
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4827324f5b55a5a4e8626b81518d48706d790a08
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4827324f5b55a5a4e8626b81518d48706d790a08
│           └── chunk-001.nq.gz
├── blob
│   ├── 037fa5fcdb7adb35e8392c6e716635ec841a347d.nq.gz
│   ├── 03be2f1fe6d36833afeeb8824a3123faa7474262.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 29017e96c90b341a9c108deaa015e773e2fa81f0.nq.gz
│   ├── 8433b121acb46137ab14ed4ad03d09dc3bbcbe5d.nq.gz
│   ├── 8c853af6d83c999b7e95de091fa67ab965ee0493.nq.gz
│   ├── a5ab08854148420219be161ca6ab715356825d40.nq.gz
│   ├── bd71d92b21eb162456e495c0b314df5f6c5e4978.nq.gz
│   └── d0d5ce3ee8fa6494d61b4f902ee7d8de943e1b36.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4827324f5b55a5a4e8626b81518d48706d790a08.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 15 files
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

[simonw/llm-openai-decisions](https://github.com/simonw/llm-openai-decisions)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
