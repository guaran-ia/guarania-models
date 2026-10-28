# Gemma4 2B (Full CPT)

| benchmark | base (-95% CI, +95% CI) | C7 (-95% CI, +95% CI) | Gain C7 |
| --- | --- | --- | --- |
| **Guarani** |  |  |  |
| Global MMLU Lite GN (acc) | 36.25 (31.53, 40.97) | **41.00 (36.17, 45.83)** | +4.75 |
| MGSM GN (exact_match) | **2.11 (-0.26, 4.48)** | 1.41 (-0.54, 3.36) | -0.70 |
| WNLI GN (acc) | 38.78 (25.00, 52.56) | **51.02 (36.88, 65.16)** | +12.24 |
| Belebele GN (acc) | 34.56 (31.45, 37.67) | **37.22 (34.06, 40.38)** | +2.66 |
| MultiWikiQA GN (F1) | 23.36 (22.38, 24.34) | **30.77 (29.70, 31.84)** | +7.41 |
| FLORES+ EN->GN (chrF++) | 8.38 | **26.34** | +17.96 |
| FLORES+ GN->EN (chrF++) | 28.18 | **35.04** | +6.86 |
| FLORES+ ES->GN (chrF++) | 9.01 | **26.72** | +17.71 |
| FLORES+ GN->ES (chrF++) | 26.61 | **31.85** | +5.24 |
| Average | 23.03 | **31.26** | +8.23 |
| **Spanish** |  |  |  |
| benchmark | base (-95% CI, +95% CI) | C7 (-95% CI, +95% CI) | Gain C7 |
| --- | --- | --- | --- |
| Global MMLU Lite ES (acc) | **59.00 (54.17, 63.83)** | 56.00 (51.13, 60.87) | -3.00 |
| Belebele ES (acc) | **70.11 (67.12, 73.10)** | 67.11 (64.04, 70.18) | -3.00 |
| MultiWikiQA ES (F1) | **73.27 (72.23, 74.31)** | 68.53 (67.44, 69.62) | -4.74 |
| ARC Easy ES (acc_norm) | **74.04 (70.44, 77.64)** | **74.04 (70.44, 77.64)** | +0.00 |
| ARC Challenge ES (acc_norm) | 67.89 (62.59, 73.19) | **68.23 (62.94, 73.52)** | +0.34 |
| PIQA ES (acc_norm) | **79.00 (70.98, 87.02)** | 76.00 (67.59, 84.41) | -3.00 |
| HellaSwag ES (acc_norm) | 65.93 (64.97, 66.89) | **66.42 (65.46, 67.38)** | +0.49 |
| COPA ES (acc) | 73.00 (64.25, 81.75) | **77.00 (68.71, 85.29)** | +4.00 |
| XStoryCloze ES (acc) | **71.74 (69.47, 74.01)** | 70.95 (68.66, 73.24) | -0.79 |
| TruthfulQA-MC1 ES (acc) | **31.31 (28.07, 34.55)** | 29.40 (26.22, 32.58) | -1.91 |
| WNLI ES (acc) | 50.70 (38.99, 62.41) | **52.11 (40.41, 63.81)** | +1.41 |
| MGSM ES (exact_match) | **8.40 (4.95, 11.85)** | 7.60 (4.31, 10.89) | -0.80 |
| GPQA Main ES (acc) | **29.46 (25.23, 33.69)** | 27.01 (22.89, 31.13) | -2.45 |
| Average | **57.99 (56.45, 59.53)** | 56.95 (55.42, 58.48) | -1.04 |
| **English** |  |  |  |
| benchmark | base (-95% CI, +95% CI) | C7 (-95% CI, +95% CI) | Gain C7 |
| --- | --- | --- | --- |
| Global MMLU Lite EN (acc) | **59.50 (54.68, 64.32)** | 58.75 (53.92, 63.58) | -0.75 |
| Belebele EN (acc) | **76.67 (73.91, 79.43)** | 74.11 (71.25, 76.97) | -2.56 |
| MultiWikiQA EN (F1) | **75.45 (74.44, 76.46)** | 72.58 (71.53, 73.63) | -2.87 |
| ARC Easy EN (acc_norm) | **76.14 (72.64, 79.64)** | 75.09 (71.54, 78.64) | -1.05 |
| ARC Challenge EN (acc_norm) | **57.86 (52.25, 63.47)** | 57.19 (51.57, 62.81) | -0.67 |
| PIQA EN (acc_norm) | **72.00 (63.16, 80.84)** | **72.00 (63.16, 80.84)** | +0.00 |
| HellaSwag EN (acc_norm) | 75.27 (74.43, 76.11) | **76.46 (75.63, 77.29)** | +1.19 |
| WNLI EN (acc) | 45.07 (33.41, 56.73) | **46.48 (34.80, 58.16)** | +1.41 |
| COPA EN (acc) | 82.00 (74.43, 89.57) | **83.00 (75.60, 90.40)** | +1.00 |
| XStoryCloze EN (acc) | 78.76 (76.70, 80.82) | **80.21 (78.20, 82.22)** | +1.45 |
| MGSM EN (exact_match) | **7.20 (3.99, 10.41)** | **7.20 (3.99, 10.41)** | +0.00 |
| GPQA Main EN (acc) | **33.04 (28.68, 37.40)** | 31.70 (27.39, 36.01) | -1.34 |
| TruthfulQA-MC1 EN (acc) | **23.87 (20.95, 26.79)** | 23.38 (20.48, 26.28) | -0.49 |
| Average | **58.68 (57.16, 60.20)** | 58.32 (56.80, 59.84) | -0.36 |

>[!Note]
> 95% confidence intervals are approximate normal intervals computed as the score or average ± 1.96 times its standard error. Average standard errors assume independent benchmark estimates. An interval is omitted when the evaluation output lacks a finite standard error. Gain columns show signed score-point differences from the corresponding base model; average gains use displayed rounded scores. FLORES+ BLEU is excluded; FLORES+ chrF++ is reported by translation direction.

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
