# Repolex Knowledge Graph of beeware/std-nslog

RDF knowledge graph data for [beeware/std-nslog](https://github.com/beeware/std-nslog), parsed by [repolex](https://repolex.ai).

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
rlex download beeware/std-nslog
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 39328076ecd236d574a775dd7e688b879ba1de88
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 39328076ecd236d574a775dd7e688b879ba1de88
│           └── chunk-001.nq.gz
├── blob
│   ├── 11dc21ead21ad4f6c5a951299cf4f3e1891558c9.nq.gz
│   ├── 16b51012646d57dec8be728765f0aee1967740d0.nq.gz
│   ├── 28c0cccec91b9b8834d885ec5023b05eba96cb70.nq.gz
│   ├── 48b5fa365b10a674d9e51e7e79cbce96ef159ee2.nq.gz
│   ├── 4a09c81e23ca735b7d235c71f9ed7feca8081af3.nq.gz
│   ├── 60d9b0725a56b1e899fa1923943473b80b478fc3.nq.gz
│   ├── 70060c49157573ee8d7d59412871cf92921a3037.nq.gz
│   ├── 800ed44ab0afea3b4a9b05cc8f159755251423d3.nq.gz
│   ├── 896dd58a2870e9aa62a27042babc8fb2380cd32a.nq.gz
│   ├── 94b29494782264c8eb70cbf26b289f6733301865.nq.gz
│   ├── 96fba87aab44a2e15831fe0900e9a3bd21923ebd.nq.gz
│   ├── a26be4878f97fec22c87960fa5a3009f74278227.nq.gz
│   ├── b834affdddcf5014398ca9c16aafe3ea7f2d0422.nq.gz
│   ├── b8a131969461284853f0a4db38b6e8d534da5b40.nq.gz
│   ├── b9bcff9ce67bcb72d9851a1e080f12c3c1d9a710.nq.gz
│   ├── bd26d83508060c0a53a0ce1221058c001aecb3f4.nq.gz
│   ├── c087635610de7793e2af1d83a514c6af795e685c.nq.gz
│   ├── c4d88e8173e484996f9c1fe716bd0fb7e4c8a73b.nq.gz
│   ├── cb416c84ad429238662b0c5639cdc07c73dcd354.nq.gz
│   ├── e06576e3999d5708bf9b2219ed51abbbc2af7080.nq.gz
│   └── f122860d468dba7fd67e4928964e27f2c2646917.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 39328076ecd236d574a775dd7e688b879ba1de88.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 29 files
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

[beeware/std-nslog](https://github.com/beeware/std-nslog)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
