# Repolex Knowledge Graph of sdispater/flask-orator

RDF knowledge graph data for [sdispater/flask-orator](https://github.com/sdispater/flask-orator), parsed by [repolex](https://repolex.ai).

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
rlex download sdispater/flask-orator
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f1d6e2a7a855928a458c69efc36c7a77451c80b4
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── f1d6e2a7a855928a458c69efc36c7a77451c80b4
│           └── chunk-001.nq.gz
├── blob
│   ├── 049681c6f27bdc1d93a8578903f63923b4e235fd.nq.gz
│   ├── 23fb0c354fe969a2f27497b59603d8838e8bc4d6.nq.gz
│   ├── 2e37694e8bd1ae0a4a98a6f57495b300e83c8dd8.nq.gz
│   ├── 3c6660ebe3bdd5ae967e9454c3f09f4eab503d79.nq.gz
│   ├── 625bed64a9cbb7f3ccbe8d216ee07aebeef19c8e.nq.gz
│   ├── 633f866158ac742cf754a2c43edcb07e3a094f3c.nq.gz
│   ├── 676166b918055b92f23f53012bedd14ab51db758.nq.gz
│   ├── 677bf5dddcc6d0f7117dff995923cca9111e3158.nq.gz
│   ├── 701df228d97e9bf3f2b10c5634107daff2f7bd3d.nq.gz
│   ├── 9753d8f7d82b6fb5ff7a5c98ea5d3cd6ae2ccf51.nq.gz
│   ├── 9cb239600796bb3782ac945292642726e5276b2a.nq.gz
│   ├── add0901f6d2028b98d8823619bd777cacd0805b1.nq.gz
│   ├── bc5f5a7dada178f16e44bf9ef18c62865146a369.nq.gz
│   ├── bcaf588abad09636032fb4fbb494fed3a6a4d8f1.nq.gz
│   ├── bea6fdf26f1014f3c64d72c75597de63dee86e5a.nq.gz
│   ├── c16d885dde13f323ad4adacdabcdc815d5c99840.nq.gz
│   ├── d737b7514b168139e83c18afd0f86342c23d304c.nq.gz
│   ├── db93d1d225e1403fe4e1160d839691c4d544b9ab.nq.gz
│   ├── e0141e9a5495441eb3131dd551c9f860f8a16be6.nq.gz
│   ├── f0567a39131c67db43cb175985166262c18719e9.nq.gz
│   ├── f3efa2d34841cbf8e44b8696484a1c35fa407c4b.nq.gz
│   └── fa302706be828501c6dc76ec2da17506c010fa01.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── f1d6e2a7a855928a458c69efc36c7a77451c80b4.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 30 files
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

[sdispater/flask-orator](https://github.com/sdispater/flask-orator)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
