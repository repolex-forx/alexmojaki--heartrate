# Repolex Knowledge Graph of alexmojaki/heartrate

RDF knowledge graph data for [alexmojaki/heartrate](https://github.com/alexmojaki/heartrate), parsed by [repolex](https://repolex.ai).

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
rlex download alexmojaki/heartrate
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e6cab2c5123bde194d5de2654b2f39938fd2be13
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e6cab2c5123bde194d5de2654b2f39938fd2be13
│           └── chunk-001.nq.gz
├── blob
│   ├── 091fc72a6154940dfb87e4af71b54513f3b4c898.nq.gz
│   ├── 1413fc609ab6f21774de0cb7e01360095584f65b.nq.gz
│   ├── 1645dbcbe07fc2493044ca488bf2cf8a237be5ab.nq.gz
│   ├── 296e2c5d59490631dd4520dbaf9a21d6c81bdcd9.nq.gz
│   ├── 4006379731a772d007e3e50390dba72677af1ab2.nq.gz
│   ├── 473e36e246edd5800325e9fa1eaa7697c95be1ef.nq.gz
│   ├── 5647b9a391beb7e55626ff9467236dfeb8ad2637.nq.gz
│   ├── 5dc3bcb55e71c871a8832d4ca02cc51c57058b83.nq.gz
│   ├── 64539b54c3751a6d9adb44c8e3a45ba5a73b77f0.nq.gz
│   ├── 7a41c4f15f025584f7970e139f27ce83eb23efeb.nq.gz
│   ├── 94fb5490a2ed10b2c69a4a567a4fd2e4f706d841.nq.gz
│   ├── 9e612858f802245ddcbf59788a0db942224bab35.nq.gz
│   ├── b93a4953fff68df523aa7656497ee339d6026d64.nq.gz
│   ├── bf5fe1e9059815f39921bd0e8ecdbe01d6fcbbc1.nq.gz
│   ├── c2e75d398c09f6a73a3c4307fec33c08a118a8d3.nq.gz
│   ├── d2d8ca4790e52b0537f3cbb7dcd766099b789583.nq.gz
│   ├── d8777a8569e444c1ad2dbe7d1ad0401c6785edb7.nq.gz
│   ├── e7f3cef2f54398d779ae753eceef1c2b57b93376.nq.gz
│   └── f1ce5037d4b094ef0cb319e2fe631c5137fc77ec.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e6cab2c5123bde194d5de2654b2f39938fd2be13.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

[alexmojaki/heartrate](https://github.com/alexmojaki/heartrate)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
