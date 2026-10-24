# Gemma3 4B (Full CPT)

| benchmark | base (-95% CI, +95% CI) | C7 (-95% CI, +95% CI) | Gain C7 |
| --- | --- | --- | --- |
| **Guarani** |  |  |  |
| Global MMLU Lite GN (acc) | 36.00 (31.29, 40.71) | **44.25 (39.38, 49.12)** | +8.25 |
| MGSM GN (exact_match) | 4.93 (1.36, 8.50) | **5.63 (1.82, 9.44)** | +0.70 |
| WNLI GN (acc) | 40.82 (26.92, 54.72) | **42.86 (28.86, 56.86)** | +2.04 |
| Belebele GN (acc) | 34.11 (31.01, 37.21) | **43.33 (40.09, 46.57)** | +9.22 |
| MultiWikiQA GN (F1) | 16.93 (16.04, 17.82) | **33.74 (32.66, 34.82)** | +16.81 |
| FLORES+ EN->GN (chrF++) | 7.93 | **27.21** | +19.28 |
| FLORES+ GN->EN (chrF++) | 27.05 | **39.62** | +12.57 |
| FLORES+ ES->GN (chrF++) | 8.14 | **27.54** | +19.40 |
| FLORES+ GN->ES (chrF++) | 25.45 | **34.45** | +9.00 |
| Average | 22.37 | **33.18** | +10.81 |
| **Spanish** |  |  |  |
| benchmark | base (-95% CI, +95% CI) | C7 (-95% CI, +95% CI) | Gain C7 |
| --- | --- | --- | --- |
| Global MMLU Lite ES (acc) | **62.75 (58.01, 67.49)** | 59.75 (54.94, 64.56) | -3.00 |
| Belebele ES (acc) | **70.44 (67.46, 73.42)** | 67.33 (64.26, 70.40) | -3.11 |
| MultiWikiQA ES (F1) | **76.13 (75.14, 77.12)** | 72.07 (71.03, 73.11) | -4.06 |
| ARC Easy ES (acc_norm) | 81.93 (78.77, 85.09) | **82.11 (78.96, 85.26)** | +0.18 |
| ARC Challenge ES (acc_norm) | **71.91 (66.81, 77.01)** | 69.57 (64.35, 74.79) | -2.34 |
| PIQA ES (acc_norm) | 79.00 (70.98, 87.02) | **81.00 (73.27, 88.73)** | +2.00 |
| HellaSwag ES (acc_norm) | 67.19 (66.24, 68.14) | **69.48 (68.55, 70.41)** | +2.29 |
| COPA ES (acc) | **77.00 (68.71, 85.29)** | 76.00 (67.59, 84.41) | -1.00 |
| XStoryCloze ES (acc) | 72.53 (70.28, 74.78) | **73.33 (71.10, 75.56)** | +0.80 |
| TruthfulQA-MC1 ES (acc) | **32.07 (28.81, 35.33)** | 29.66 (26.47, 32.85) | -2.41 |
| WNLI ES (acc) | **49.30 (37.59, 61.01)** | 42.25 (30.68, 53.82) | -7.05 |
| MGSM ES (exact_match) | 10.80 (6.94, 14.66) | **12.00 (7.96, 16.04)** | +1.20 |
| GPQA Main ES (acc) | **29.24 (25.02, 33.46)** | 27.01 (22.89, 31.13) | -2.23 |
| Average | **60.02 (58.50, 61.54)** | 58.58 (57.07, 60.09) | -1.44 |
| **English** |  |  |  |
| benchmark | base (-95% CI, +95% CI) | C7 (-95% CI, +95% CI) | Gain C7 |
| --- | --- | --- | --- |
| Global MMLU Lite EN (acc) | **68.00 (63.42, 72.58)** | 65.75 (61.09, 70.41) | -2.25 |
| Belebele EN (acc) | **76.78 (74.02, 79.54)** | 73.56 (70.68, 76.44) | -3.22 |
| MultiWikiQA EN (F1) | **78.42 (77.47, 79.37)** | 71.88 (70.84, 72.92) | -6.54 |
| ARC Easy EN (acc_norm) | 80.18 (76.90, 83.46) | **80.53 (77.28, 83.78)** | +0.35 |
| ARC Challenge EN (acc_norm) | **56.19 (50.56, 61.82)** | 55.18 (49.53, 60.83) | -1.01 |
| PIQA EN (acc_norm) | **78.00 (69.84, 86.16)** | **78.00 (69.84, 86.16)** | +0.00 |
| HellaSwag EN (acc_norm) | 77.78 (76.97, 78.59) | **80.25 (79.47, 81.03)** | +2.47 |
| WNLI EN (acc) | **47.89 (36.19, 59.59)** | 40.85 (29.33, 52.37) | -7.04 |
| COPA EN (acc) | 88.00 (81.60, 94.40) | **90.00 (84.09, 95.91)** | +2.00 |
| XStoryCloze EN (acc) | 80.28 (78.27, 82.29) | **81.14 (79.17, 83.11)** | +0.86 |
| MGSM EN (exact_match) | **14.40 (10.04, 18.76)** | 13.20 (9.00, 17.40) | -1.20 |
| GPQA Main EN (acc) | 33.48 (29.10, 37.85) | **33.71 (29.33, 38.09)** | +0.23 |
| TruthfulQA-MC1 EN (acc) | **24.36 (21.41, 27.31)** | 22.03 (19.19, 24.87) | -2.33 |
| Average | **61.83 (60.35, 63.31)** | 60.47 (59.02, 61.92) | -1.36 |

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
