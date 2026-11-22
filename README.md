# Repolex Knowledge Graph of Ezibenroc/PyRoaringBitMap

RDF knowledge graph data for [Ezibenroc/PyRoaringBitMap](https://github.com/Ezibenroc/PyRoaringBitMap), parsed by [repolex](https://repolex.ai).

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
rlex download Ezibenroc/PyRoaringBitMap
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 703a842a211dd551509c9e7846c256960e7fa27f
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 703a842a211dd551509c9e7846c256960e7fa27f.nq.gz
│   └── repolex
│       └── 703a842a211dd551509c9e7846c256960e7fa27f
│           └── chunk-001.nq.gz
├── blob
│   ├── 07a5f2bde2eedb22be0ed7b6dc0f5032853021b3.nq.gz
│   ├── 0cee11fca17f6ce59f05a19fbca6d4863f7e6b1f.nq.gz
│   ├── 0e32cf3f79a4faec817a329128fd37f26d8c3739.nq.gz
│   ├── 176d47826b7a7a86f8d6a777c9a65d857d12fa56.nq.gz
│   ├── 2083c1936d84e93ad25eb0a3876997b570059abd.nq.gz
│   ├── 270a9cf9e75c782e60f9a8a5b3e030251e0061f4.nq.gz
│   ├── 27dc6085ae72459ea6078aa351956eaf71f1b598.nq.gz
│   ├── 2e346c21497db428076a284d67fd6b37f148e06f.nq.gz
│   ├── 33dfad161e49f055d040ce189643d2b85d78a5c6.nq.gz
│   ├── 39cf84fc254a97f3905301a11c90a7cc764f6186.nq.gz
│   ├── 3a2e087133eba86b0bfee967f7d1c2aa83c72980.nq.gz
│   ├── 3a5b61a0dff83ba5d83a576cecf26a8a86036c36.nq.gz
│   ├── 3fc8ac525b14a1a2028093421ecb13290525bc8a.nq.gz
│   ├── 51173ad9daaab4133e740220c51780f926cc1ae8.nq.gz
│   ├── 6bf02958afab0cb93f329de0a586cbbbe88e9e23.nq.gz
│   ├── 6e6666d5f198702111f9d560eedf5288b601db58.nq.gz
│   ├── 6fe992bb0f38963f54dfaefd491611a279a1da92.nq.gz
│   ├── 72f56a981c3865a20200a49f490b1f0dccfcf2c2.nq.gz
│   ├── 7a3bd5acfeab775810aa03c586035479c205aac5.nq.gz
│   ├── 7caeb1e4ae711c626132f402ba32d6bf7e434ef2.nq.gz
│   ├── 92192eed4fc88eaee9fdbafbc8e2139c43ba00e2.nq.gz
│   ├── 9b94de51ad7db643912250b3b110a1d672674272.nq.gz
│   ├── b1b7c0b48af82119d9965166786feb30e43c8d6c.nq.gz
│   ├── be017b579a174a62c1291927cefb36f563ac766e.nq.gz
│   ├── be51da7ac088120cee8563fa1441649c91c2c131.nq.gz
│   ├── c038cc231fb072930be41e5e4cb9b387d45142bd.nq.gz
│   ├── c5ab0e8997e8b72957e74144240958c5e1da582c.nq.gz
│   ├── d083eb894c27c72d50df2684d6424b18646faa38.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f4def4062b42243a6ef9d6e0d7aaee8f18dfab55.nq.gz
│   ├── f7079c0a3f9b92a11538cb6ff4a889cf2c501092.nq.gz
│   └── f8c425d896a78dd8825dad4d999bd6cfc0a15c20.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 703a842a211dd551509c9e7846c256960e7fa27f.nq.gz
├── filetree
│   └── 703a842a211dd551509c9e7846c256960e7fa27f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 42 files
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

[Ezibenroc/PyRoaringBitMap](https://github.com/Ezibenroc/PyRoaringBitMap)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
