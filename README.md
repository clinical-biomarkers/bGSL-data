# bGSL-data: biomarker Glycan Structure Lexicon Resource

This repository is a public data deposit for the biomarker Glycan Structure Lexicon (bGSL), a structured and standardized lexicon of glycan names and biomarker-relevant glycan concepts. The dataset captures canonical terms, common abbreviations, synonym variants, classification labels, and cross-references to established glycan identifiers and ontology resources.

The bGSL is intended to support glycan annotation, literature mining, biomarker curation, and downstream integration into knowledgebases and data pipelines that require consistent terminology and cross-resource mapping.

> [!IMPORTANT]
> The first release version (`2026-07-06`) uses a different set of Universally Unique Identifiers (UUIDs) for the bGSL terms. All versions after the second release version (`2026-10-08`) do not re-assign new UUIDs for the same glycan terms.

## Repository contents

```text
releases/
	YYYY-MM-DD/
		bGSL_YYYY-MM-DD.tsv
		RELEASE.md
```

## Data format

## Columns

| Field              | Description                                                            |
| ------------------ | ---------------------------------------------------------------------- |
| `bgsl_id`          | Stable internal identifier for the glycan entry in the bGSL registry.  |
| `term`             | Preferred or canonical glycan term.                                    |
| `abbreviations`    | Common short forms or abbreviated names.                               |
| `exact_synonyms`   | Synonyms considered equivalent to the canonical term.                  |
| `broad_synonyms`   | Broader or less specific naming variants.                              |
| `narrow_synonyms`  | More specific naming variants.                                         |
| `related_synonyms` | Related but not necessarily equivalent names.                          |
| `classification`   | Structural or lexical classification label.                            |
| `gtc_id`           | GlyTouCan accession(s) associated with the glycan.                     |
| `gsd_id`           | Glycan structure database accession(s), when available.                |
| `glycomotif_id`    | GlycoMotif accession(s), when available.                               |
| `sources`          | Provenance of the term or mapping evidence.                            |
| `eog_sentence`     | Example sentence or evidence text associated with the naming or usage. |
| `review_notes`     | Internal notes from curation or review.                                |
