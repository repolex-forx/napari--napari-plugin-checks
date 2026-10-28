# Repolex Knowledge Graph of napari/napari-plugin-checks

RDF knowledge graph data for [napari/napari-plugin-checks](https://github.com/napari/napari-plugin-checks), parsed by [repolex](https://repolex.ai).

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
rlex download napari/napari-plugin-checks
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 7775fdda3048b9355c311b867e90ad4b9dce197d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 7775fdda3048b9355c311b867e90ad4b9dce197d
│           └── chunk-001.nq.gz
├── blob
│   ├── 1d43943f65d2c6631d2916e5e1bf383dd43f8bf1.nq.gz
│   ├── 3f712512458cde2f1337abfde5d33d34c4da7599.nq.gz
│   ├── 5548dedaba969127acf5a7bf4c0c9211590ca179.nq.gz
│   ├── 606849326a4002007fd42060b51e69a19c18675c.nq.gz
│   ├── 69321c78472ca8e2e10aae3a3a04f795f07a1365.nq.gz
│   ├── 6a3cd18446a1aa3818b1f4b587c7f4e953e94786.nq.gz
│   ├── 76c3b0cbc4aeddd567ebbc0a9f8f6c027b22608a.nq.gz
│   ├── 79c325b917e51d05ef5939ff2a78308d95d9d9de.nq.gz
│   ├── 87d1c0b0b4aa01d141da6397ac8e5935706d3b90.nq.gz
│   ├── a9088e73aabd58fb48a0be2e871a5be3ea2b20ee.nq.gz
│   ├── b6a6ceeb5b87927ad53b00e52613ed2915dc8707.nq.gz
│   ├── c793f63368e8ca49b76af352c37d772cb6de92ce.nq.gz
│   ├── ca44497dfc342e94e559eee2c2eeb5922a7328c5.nq.gz
│   ├── cf908f5e5f3245988412c4dde24ba5e3f8e4c80e.nq.gz
│   ├── e0ce81d0d7b1ca67b6966e4a2c45c32eca02eb83.nq.gz
│   ├── e5d82dba609375d23e171146b71ec1596b632c87.nq.gz
│   └── ee4da56f9e371f43871a0de233fd7c4283d929ae.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 7775fdda3048b9355c311b867e90ad4b9dce197d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
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

[napari/napari-plugin-checks](https://github.com/napari/napari-plugin-checks)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
