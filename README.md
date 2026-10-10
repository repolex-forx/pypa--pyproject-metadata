# Repolex Knowledge Graph of pypa/pyproject-metadata

RDF knowledge graph data for [pypa/pyproject-metadata](https://github.com/pypa/pyproject-metadata), parsed by [repolex](https://repolex.ai).

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
rlex download pypa/pyproject-metadata
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c78be647e3d747b007996cdaa8899b2b4f533b84
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c78be647e3d747b007996cdaa8899b2b4f533b84
│           └── chunk-001.nq.gz
├── blob
│   ├── 04915b18b26864d038dc7fae1815a4703d3439fe.nq.gz
│   ├── 149244211bb3f4667581e22dd32d2f0772b61038.nq.gz
│   ├── 16d8f858540d7acdcd9f7cd11a06ff821f246e60.nq.gz
│   ├── 274c0971985e9c507840d2e8e799fb5a6777984b.nq.gz
│   ├── 29845976b57616f7745a36075af51bfc42b3d166.nq.gz
│   ├── 29c6e9490f9a4875052c58a8e964236fa83e6a6d.nq.gz
│   ├── 2e7f2464b0bfc563f6678d28fccc6d6aeee0b7c9.nq.gz
│   ├── 40b34ebe54054d20e2d002d680ae5703c2c3fba3.nq.gz
│   ├── 440d767d2c36b1522ceda982026dc37f672e9e52.nq.gz
│   ├── 457cef814a8aa4e510cc8c09813ebfe60e685c7d.nq.gz
│   ├── 5701a4c28311c1209bcec600b58863068b584a57.nq.gz
│   ├── 5f89818f9e63c2f6829c7706c57f223cdb5bbd38.nq.gz
│   ├── 637e659c1960d1051feff084c2959995b2c400d4.nq.gz
│   ├── 674a8813719adfbbb0c97d8d7d4def04f7546725.nq.gz
│   ├── 676fc4eef2c736d3eec1332896fbf46233746389.nq.gz
│   ├── 6e5fb375cbb68de93b95f30c3452c58f49e5ba64.nq.gz
│   ├── 6fd76d3bfcdf73f4df858637d6e86ae159a05298.nq.gz
│   ├── 71d354358275f2ace052ffbf8389ee5cf2fc6c35.nq.gz
│   ├── 826701fbca67f92a2901e3cc44e8d1b6582ebd9f.nq.gz
│   ├── 8e4a10de960261e2001ebff90c565683ee249299.nq.gz
│   ├── 8ef6be04a87a44b9d5e434f2ea6df11a4d79bb76.nq.gz
│   ├── 96b02af7c8044af9d814891024ed9a053ef22a8e.nq.gz
│   ├── a870237e2bf5ce245f40d8d1c8185f408955a45b.nq.gz
│   ├── aa22981d06d4233c5110dd4eaf7d1a2be1dd5c78.nq.gz
│   ├── ae4b07e5c3eae0418fdc9463db802406788e39c7.nq.gz
│   ├── c3713cdcc9b5df70576fb1d5d010c7a17e02e038.nq.gz
│   ├── c50c28bf528e7eeb03fe2915742c02ce75c62b91.nq.gz
│   ├── cd8468e5343d28caa09fc271c0a8235bd42bd291.nq.gz
│   ├── d58d5a46064bd0b6e03c0aa95c1e8934a63c24ec.nq.gz
│   ├── d85090936a17e0f4e774ed97b5768dee274c6dc0.nq.gz
│   ├── dd866a5dc135d21ff3ad5eec3683f5b092031ad9.nq.gz
│   ├── e1ac4140cf9b6836e86c01a692f895c9ecd21712.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ee89da194912efdeae15b8d559df67097318fe29.nq.gz
│   ├── f10f121114f3104cfb7f6c230567c74fbb39495b.nq.gz
│   ├── f48162e0faf7a3ea45acf5198c51fea31ebf93cb.nq.gz
│   ├── fac802edde33761c490b94143fc55981ddda31d5.nq.gz
│   └── fbf6b98bdea7e1c1111b47bdc99000f22e599388.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c78be647e3d747b007996cdaa8899b2b4f533b84.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 46 files
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

[pypa/pyproject-metadata](https://github.com/pypa/pyproject-metadata)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
