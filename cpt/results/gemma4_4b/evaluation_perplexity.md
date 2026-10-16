# Gemma4 4B (Full CPT)

| Perplexity metric | base | C1 | C2 | C3 | C4 | C5 | C6 | C7 | C8 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| word perplexity | 3058.27 | 469.16 | 533.09 | 476.78 | 542.04 | 485.26 | 553.65 | **463.10** | 521.08 |
| byte perplexity | 2.64 | 2.11 | 2.14 | 2.11 | 2.14 | 2.11 | 2.15 | **2.10** | 2.13 |
| bits per byte | 1.40 | 1.07 | 1.10 | 1.08 | 1.10 | 1.08 | 1.10 | **1.07** | 1.09 |

## Variant reference
* C1: Kuatia (43,677,319 tokens)
* C2: Kuatia without synthetic (27,994,685 tokens)
* C3: Kuatia + 20% Spanish FineWeb-Edu (52,415,631 tokens)
* C4: Kuatia without synthetic + 20% Spanish FineWeb-Edu (36,732,997 tokens)
* C5: Kuatia + 20% FineWeb-Edu (52,412,827 tokens)
* C6: Kuatia without synthetic + 20% FineWeb-Edu (36,730,193 tokens)
* C7: Kuatia + 10% Spanish FineWeb-Edu + 10% FineWeb-Edu (52,415,521 tokens)
* C8: Kuatia without synthetic + 10% Spanish FineWeb-Edu + 10% FineWeb-Edu (36,732,887 tokens)

>[!Note]
> Token totals are the number of tokens in each configuration’s training split, as recorded in its data manifest.
