# Evaluation Information Sheet

## Model variants

| Model | Variant | Training Method | Training Data | LoRA Rank |
| --- | --- | --- | --- | --- |
| Gemma3 4B | base | Base |  |  |
| Gemma3 4B | C7 | Full CPT | Kuatia + 10% Spanish FineWeb-Edu + 10% FineWeb-Edu |  |

## Benchmarks

| Benchmark | Language | Metric | Instances | Shots | Score Split |
| --- | --- | --- | --- | --- | --- |
| ARC Challenge | Spanish (ES) | acc_norm | 299 | 25 | validation |
| ARC Challenge | English (EN) | acc_norm | 299 | 25 | validation |
| ARC Easy | Spanish (ES) | acc_norm | 570 | 0 | validation |
| ARC Easy | English (EN) | acc_norm | 570 | 0 | validation |
| Belebele | Guarani (GN) | acc | 900 | 1 | test |
| Belebele | Spanish (ES) | acc | 900 | 1 | test |
| Belebele | English (EN) | acc | 900 | 1 | test |
| COPA | Spanish (ES) | acc | 100 | 0 | validation |
| COPA | English (EN) | acc | 100 | 0 | validation |
| CoreGuapa Perplexity | Guarani (GN) | word_perplexity, byte_perplexity, bits_per_byte | 66 | 0 | test |
| FLORES+ translation (English → Guarani) | English → Guarani | bleu, chrF++ | 997 | 1 | dev |
| FLORES+ translation (Guarani → English) | Guarani → English | bleu, chrF++ | 997 | 1 | dev |
| FLORES+ translation (Guarani → Spanish) | Guarani → Spanish | bleu, chrF++ | 997 | 1 | dev |
| FLORES+ translation (Spanish → Guarani) | Spanish → Guarani | bleu, chrF++ | 997 | 1 | dev |
| Global MMLU Lite | Guarani (GN) | acc | 400 | 5 | test |
| Global MMLU Lite | Spanish (ES) | acc | 400 | 5 | test |
| Global MMLU Lite | English (EN) | acc | 400 | 5 | test |
| Global PIQA | Spanish (ES) | acc_norm | 100 | 0 | test |
| Global PIQA | English (EN) | acc_norm | 100 | 0 | test |
| GPQA Main | Spanish (ES) | acc | 448 | 5 | train |
| GPQA Main | English (EN) | acc | 448 | 5 | train |
| HellaSwag | Spanish (ES) | acc_norm | 9,374 | 10 | val |
| HellaSwag | English (EN) | acc_norm | 10,042 | 10 | validation |
| MGSM | Guarani (GN) | exact_match | 142 | 5 | test |
| MGSM | Spanish (ES) | exact_match | 250 | 0 | test |
| MGSM | English (EN) | exact_match | 250 | 0 | test |
| MultiWikiQA | Guarani (GN) | exact_match, f1 | 5,003 | 2 | train |
| MultiWikiQA | Spanish (ES) | exact_match, f1 | 5,001 | 2 | train |
| MultiWikiQA | English (EN) | exact_match, f1 | 4,999 | 2 | train |
| TruthfulQA MC1 | Spanish (ES) | acc | 789 | 6 | val |
| TruthfulQA MC1 | English (EN) | acc | 817 | 6 | validation |
| WNLI | Guarani (GN) | acc | 49 | 5 | dev |
| WNLI | Spanish (ES) | acc | 71 | 5 | validation |
| WNLI | English (EN) | acc | 71 | 5 | validation |
| XStoryCloze | Spanish (ES) | acc | 1,511 | 5 | eval |
| XStoryCloze | English (EN) | acc | 1,511 | 5 | eval |

>[!Note]
> Instances are the effective examples evaluated by LM-Eval; shots are the configured few-shot examples. Score split is the dataset split used to calculate the benchmark metrics.
