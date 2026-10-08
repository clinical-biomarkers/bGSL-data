---
version: "2026-10-08"
dataset: "biomarker Glycan Structure Lexicon export"
data_file: "bGSL_2026-10-08.tsv"
pipeline:
  name: "biomarker Glycan Structure Lexicon enrichment LLM pipeline"
  version: null
  version_source: null
  model: "gpt5.6-luna"
---

## Release notes

LLM pipeline ran on 2026-09-04; manually-curated on 2026-09-09.

- `bGSL_2026-10-08.json`: 973 nodes + 1,397 edges in one payload
- `bGSL_2026_10_08.tsv`: flat reviewer sheet for easy data integration, one row per node

### Statistics

nodes: 973
edges: 1397

- `has_related_synonym`: 84
- `has_broad_synonym` / `has_narrow_synonym`: 538
- `is_a`: 237

Class distribution: 1A 321, 1B 111, 1C 56, 2A 112, 2B 38, 2C 47, 2D 98, 2E 1, 3A 37, 3B 134, 3C 18

### Changelog

Structural verification against GlyTouCan

- 552 accessions were fetched and their WURCS linkage strings decoded independently of the IUPAC conversion.
- Accessions whose structure contradicted their node's label were removed.

ABH blood groups consolidation - manually re-organized

- Layer 1 (`blood group A`/`B`/`H`) is pinned to the
  determinant (3/3/2 residues)
- layer 2 (`blood group ? type ?`) to the tetra/tetra/tri form
- layer 3 to the extended chains, linked by `has_narrow_synonym`

Glycosphingolipid consolidation

- The systematic short form is canonical (`iGb4`, `Gb3`, `Gb4`, `Gb5`, `Gg3`, `Gg4`, `Lc4`, `nLc4`), with the `-osylceramide` long form as an exact synonym.

Added `hidden` flag (new)

- 64 nodes are marked `hidden`, withholding them from the text-mining vector store while keeping them in the enrichment store and in this release. Absent means visible, so all other and future terms default in. Exposed as a `hidden` column in the reviewer TSV.
