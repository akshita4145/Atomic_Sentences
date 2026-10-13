# Rule-Based Atomic Sentence Extraction

Decomposes complex sentences into simple "atomic" sentences that each express a single idea, using spaCy dependency parsing and clause-type rules. Unlike LLM-based approaches, the rules are interpretable, so we can see exactly which sentence structures cause extraction to fail.

📄 Paper: [Rule-Based Approaches to Atomic Sentence Extraction](https://arxiv.org/abs/2601.00506), presented at NCUR 2026

## Results
On 100 manually annotated WikiSplit sentences:
- ROUGE-1 F1: 0.671 · ROUGE-2 F1: 0.478 · ROUGE-L F1: 0.650
- BERTScore F1: 0.590

Hardest structures: relative clauses, appositions, coordinated predicates, adverbial clauses, and passive constructions.

## Pipeline
Notebooks are in `notebooks/`; data files are in `data/`.
1. `create_subset.ipynb`: samples 200 sentences from WikiSplit → `train_subset.csv`
2. `preprocessing.ipynb`: cleans the subset → `train_subset_cleaned.csv`
3. `splitter.ipynb`: tokenizes and parses with spaCy → `tokenized_data.csv`
4. `100_best.ipynb`: selects 100 sentences for evaluation, [selection criterion]
5. `sentence_extractor_v2.ipynb`: applies the extraction rules (see `Current_Rules.md`) → `split_sentences_v2.csv`
6. `evaluation.ipynb`: scores output against hand-annotated `gold_standard.csv` with ROUGE and BERTScore

`sentence_extractor_v1` and `v3` are earlier and experimental versions.

## Requirements
Python 3, pandas, numpy, spaCy (`python -m spacy download en_core_web_sm`), rouge-score, bert-score, Jupyter

## Requirements
Python 3, spaCy, pandas, Jupyter

## Authors
Lineesha Kamana, Akshita Ananda Subramanian, Mehuli Ghosh, Suman Saha (Penn State)
