# Gemma-3 4B vs Gemma-4 E4B (Full CPT) vs BYOL-GUG

| Guarani Benchmark | Gemma 3 (4B) Base | GuaranIA-G34B (C7) | Gain | Gemma 4 (E4B) Base | GuaranIA-G4E4B (C7) | Gain | BYOL-GUG (4B) | Gain |
| --- | --- | --- | --- | --- | --- | --- | -- | -- |
| Global MMLU Lite GN (acc) | 36.00 | 44.25 | +8.25 | 46.00 | 45.50 | -0.50 | 45.00 | +9.00 |
| MGSM GN (exact_match) | 4.93 | 5.63 | +0.70 | 9.86 | 9.15 | -0.71 | 25.20 | +20.27 |
| WNLI GN (acc) | 40.82 | 42.86 | +2.04 | 44.90 | 48.98 | +4.08 | -- | -- |
| Belebele GN (acc) | 34.11 | 43.33 | +9.22 | 52.22 | 55.56 | +3.34 | 45.40 | +11.29 |
| MultiWikiQA GN (F1) | 16.93 | 33.74 | +16.81 | 42.83 | 36.32 | -6.51 | -- | -- |
| FLORES+ EN->GN (chrF++) | 7.93 | 27.21 | +19.28 | 8.48 | 30.05 | +21.57 | 32.20 | +24.27 |
| FLORES+ GN->EN (chrF++) | 27.05 | 39.62 | +12.57 | 37.94 | 44.47 | +6.53 | 39.40 | +12.35 |
| FLORES+ ES->GN (chrF++) | 8.14 | 27.54 | +19.40 | 9.30 | 29.60 | +20.30 | -- | -- |
| FLORES+ GN->ES (chrF++) | 25.45 | 34.45 | +9.00 | 33.40 | 37.11 | +3.71 | -- | -- |
| Average | 22.37 | 33.18 | +10.81 | 31.66 | 37.42 | +5.76 | -- | -- |

## Reference
* `GuaranIA-G34B` is based on `Gemma-3 4B`
* `GuaranIA-G4E4B` is based on `Gemma-4 E4B`
* `C7` is a dataset configuration that includes the guarani corpus `Kuatia` + 10% `Spanish FineWeb-Edu` + 10% `FineWeb-Edu` (52,415,521 tokens)
* `BYOL-GUG` is based on `Gemma-3 4B`
