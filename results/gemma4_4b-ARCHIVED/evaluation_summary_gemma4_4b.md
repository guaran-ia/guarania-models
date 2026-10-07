# Model: gemma4_4b

Gain rows show relative percentage change from the matching base model; positive values indicate improvement.

## FLORES-200 translations

| metric | base | full_C1_kuatia | full_C2_kuatia_no_synthetic | full_C3_kuatia_es20 | full_C4_kuatia_no_synthetic_es20 | full_C5_kuatia_en20 | full_C6_kuatia_no_synthetic_en20 | full_C7_kuatia_es10_en10 | full_C8_kuatia_no_synthetic_es10_en10 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| flores200_en_to_gn_bleu | 0.672 | 0.886 | 0.023 | 1.676 | 1.174 | 1.253 | **4.129** | 2.194 | 2.501 |
| flores200_en_to_gn_bleu_gain_base | -- | +31.74% | -96.60% | +149.25% | +74.68% | +86.32% | +514.18% | +226.39% | +272.07% |
| flores200_en_to_gn_chrf++ | 4.306 | 11.415 | 5.493 | 14.286 | 12.497 | 12.943 | **22.567** | 15.917 | 16.623 |
| flores200_en_to_gn_chrf++_gain_base | -- | +165.09% | +27.57% | +231.79% | +190.24% | +200.58% | +424.10% | +269.65% | +286.05% |
| flores200_es_to_gn_bleu | 0.022 | **0.700** | 0.002 | 0.235 | 0.000 | 0.301 | 0.074 | 0.278 | 0.205 |
| flores200_es_to_gn_bleu_gain_base | -- | +3071.53% | -91.66% | +964.47% | -100.00% | +1263.86% | +235.79% | +1158.85% | +828.42% |
| flores200_es_to_gn_chrf++ | 0.643 | 7.322 | 0.129 | 1.452 | 1.687 | **8.482** | 6.042 | 8.356 | 6.604 |
| flores200_es_to_gn_chrf++_gain_base | -- | +1039.15% | -79.93% | +125.81% | +162.52% | +1219.57% | +839.92% | +1199.87% | +927.37% |
| flores200_gn_to_es_bleu | 1.286 | 8.207 | 7.182 | 4.527 | 7.354 | **10.582** | 8.891 | 9.495 | 0.405 |
| flores200_gn_to_es_bleu_gain_base | -- | +538.22% | +458.56% | +252.05% | +471.92% | +722.97% | +591.46% | +638.41% | -68.54% |
| flores200_gn_to_es_chrf++ | 12.290 | 27.068 | 25.281 | 20.257 | 24.992 | **31.808** | 28.735 | 28.960 | 10.026 |
| flores200_gn_to_es_chrf++_gain_base | -- | +120.24% | +105.70% | +64.82% | +103.35% | +158.81% | +133.80% | +135.63% | -18.42% |
| flores200_gn_to_en_bleu | 9.726 | 17.068 | 17.307 | 17.314 | 17.119 | 18.262 | 17.702 | **19.239** | 8.364 |
| flores200_gn_to_en_bleu_gain_base | -- | +75.49% | +77.94% | +78.02% | +76.01% | +87.76% | +82.01% | +97.81% | -14.01% |
| flores200_gn_to_en_chrf++ | 27.314 | 38.512 | 41.250 | 39.048 | 40.619 | 40.594 | 40.311 | **41.936** | 25.224 |
| flores200_gn_to_en_chrf++_gain_base | -- | +41.00% | +51.02% | +42.96% | +48.71% | +48.62% | +47.59% | +53.53% | -7.65% |

## Perplexity

| metric | base | full_C1_kuatia | full_C2_kuatia_no_synthetic | full_C3_kuatia_es20 | full_C4_kuatia_no_synthetic_es20 | full_C5_kuatia_en20 | full_C6_kuatia_no_synthetic_en20 | full_C7_kuatia_es10_en10 | full_C8_kuatia_no_synthetic_es10_en10 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| gn_bits_per_byte | 2.534 | 1.147 | 1.172 | 1.150 | 1.175 | 1.152 | 1.180 | 1.145 | 1.170 |
| gn_bits_per_byte_gain_base | -- | +54.74% | +53.77% | +54.64% | +53.63% | +54.55% | +53.42% | +54.82% | +53.83% |
| gn_byte_perplexity | 5.794 | 2.215 | 2.253 | 2.219 | 2.258 | 2.222 | 2.267 | 2.212 | 2.250 |
| gn_byte_perplexity_gain_base | -- | +61.77% | +61.12% | +61.71% | +61.02% | +61.65% | +60.88% | +61.83% | +61.16% |
| gn_word_perplexity | 1998537.220 | 711.090 | 817.978 | 721.317 | 835.255 | 730.535 | 860.464 | 702.489 | 810.546 |
| gn_word_perplexity_gain_base | -- | +99.96% | +99.96% | +99.96% | +99.96% | +99.96% | +99.96% | +99.96% | +99.96% |

## Guarani benchmarks

| metric | base | full_C1_kuatia | full_C2_kuatia_no_synthetic | full_C3_kuatia_es20 | full_C4_kuatia_no_synthetic_es20 | full_C5_kuatia_en20 | full_C6_kuatia_no_synthetic_en20 | full_C7_kuatia_es10_en10 | full_C8_kuatia_no_synthetic_es10_en10 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| gn_belebele_acc | 0.430 | **0.467** | 0.408 | 0.436 | 0.424 | 0.432 | 0.434 | 0.466 | 0.432 |
| gn_belebele_acc_gain_base | -- | +8.53% | -5.17% | +1.29% | -1.29% | +0.52% | +1.03% | +8.27% | +0.52% |
| gn_belebele_acc_norm | 0.430 | **0.467** | 0.408 | 0.436 | 0.424 | 0.432 | 0.434 | 0.466 | 0.432 |
| gn_belebele_acc_norm_gain_base | -- | +8.53% | -5.17% | +1.29% | -1.29% | +0.52% | +1.03% | +8.27% | +0.52% |
| gn_global_mmlu_lite_acc | 0.388 | 0.325 | 0.400 | 0.355 | 0.355 | 0.395 | 0.390 | **0.412** | 0.385 |
| gn_global_mmlu_lite_acc_gain_base | -- | -16.13% | +3.23% | -8.39% | -8.39% | +1.94% | +0.65% | +6.45% | -0.65% |
| gn_global_mmlu_lite_acc_norm | 0.388 | 0.325 | 0.400 | 0.355 | 0.355 | 0.395 | 0.390 | **0.412** | 0.385 |
| gn_global_mmlu_lite_acc_norm_gain_base | -- | -16.13% | +3.23% | -8.39% | -8.39% | +1.94% | +0.65% | +6.45% | -0.65% |
| gn_multiwikiqa_exact_match | 0.051 | 0.113 | 0.100 | 0.126 | 0.099 | 0.116 | 0.123 | 0.124 | **0.133** |
| gn_multiwikiqa_exact_match_gain_base | -- | +121.96% | +95.69% | +147.84% | +94.51% | +127.84% | +140.78% | +143.14% | +161.57% |
| gn_multiwikiqa_f1 | 0.202 | 0.287 | 0.273 | 0.301 | 0.276 | 0.293 | 0.293 | 0.303 | **0.311** |
| gn_multiwikiqa_f1_gain_base | -- | +42.22% | +35.08% | +49.00% | +36.51% | +45.03% | +44.77% | +50.10% | +53.97% |
| Average of variant across benchmarks | 0.315 | 0.331 | 0.331 | 0.335 | 0.322 | 0.344 | 0.344 | **0.364** | 0.346 |
| Average of variant gain in relation to base across benchmarks | -- | +24.83% | +21.15% | +30.44% | +18.61% | +29.63% | +31.49% | +37.11% | +35.88% |

## Spanish benchmarks

| metric | base | full_C1_kuatia | full_C2_kuatia_no_synthetic | full_C3_kuatia_es20 | full_C4_kuatia_no_synthetic_es20 | full_C5_kuatia_en20 | full_C6_kuatia_no_synthetic_en20 | full_C7_kuatia_es10_en10 | full_C8_kuatia_no_synthetic_es10_en10 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| es_arc_challenge_acc | **0.806** | 0.749 | 0.719 | 0.729 | 0.729 | 0.726 | 0.749 | 0.739 | 0.709 |
| es_arc_challenge_acc_gain_base | -- | -7.05% | -10.79% | -9.54% | -9.54% | -9.96% | -7.05% | -8.30% | -12.03% |
| es_arc_challenge_acc_norm | **0.806** | 0.749 | 0.719 | 0.729 | 0.729 | 0.726 | 0.749 | 0.739 | 0.709 |
| es_arc_challenge_acc_norm_gain_base | -- | -7.05% | -10.79% | -9.54% | -9.54% | -9.96% | -7.05% | -8.30% | -12.03% |
| es_arc_easy_acc | **0.898** | 0.868 | 0.867 | 0.884 | 0.874 | 0.825 | 0.881 | 0.874 | 0.874 |
| es_arc_easy_acc_gain_base | -- | -3.32% | -3.52% | -1.56% | -2.73% | -8.20% | -1.95% | -2.73% | -2.73% |
| es_arc_easy_acc_norm | **0.898** | 0.868 | 0.867 | 0.884 | 0.874 | 0.825 | 0.881 | 0.874 | 0.874 |
| es_arc_easy_acc_norm_gain_base | -- | -3.32% | -3.52% | -1.56% | -2.73% | -8.20% | -1.95% | -2.73% | -2.73% |
| es_belebele_acc | **0.784** | 0.716 | 0.676 | 0.728 | 0.734 | 0.701 | 0.738 | 0.752 | 0.721 |
| es_belebele_acc_gain_base | -- | -8.78% | -13.88% | -7.22% | -6.37% | -10.62% | -5.95% | -4.11% | -8.07% |
| es_belebele_acc_norm | **0.784** | 0.716 | 0.676 | 0.728 | 0.734 | 0.701 | 0.738 | 0.752 | 0.721 |
| es_belebele_acc_norm_gain_base | -- | -8.78% | -13.88% | -7.22% | -6.37% | -10.62% | -5.95% | -4.11% | -8.07% |
| es_copa_acc | **0.828** | 0.810 | 0.802 | 0.810 | **0.828** | 0.812 | 0.812 | 0.816 | 0.802 |
| es_copa_acc_gain_base | -- | -2.17% | -3.14% | -2.17% | +0.00% | -1.93% | -1.93% | -1.45% | -3.14% |
| es_global_mmlu_lite_acc | **0.632** | 0.562 | 0.547 | 0.593 | 0.575 | 0.575 | 0.620 | 0.598 | 0.590 |
| es_global_mmlu_lite_acc_gain_base | -- | -11.07% | -13.44% | -6.32% | -9.09% | -9.09% | -1.98% | -5.53% | -6.72% |
| es_global_mmlu_lite_acc_norm | **0.632** | 0.562 | 0.547 | 0.593 | 0.575 | 0.575 | 0.620 | 0.598 | 0.590 |
| es_global_mmlu_lite_acc_norm_gain_base | -- | -11.07% | -13.44% | -6.32% | -9.09% | -9.09% | -1.98% | -5.53% | -6.72% |
| es_gpqa_diamond_acc | **0.323** | 0.268 | 0.293 | 0.273 | 0.268 | 0.303 | 0.278 | 0.293 | 0.268 |
| es_gpqa_diamond_acc_gain_base | -- | -17.19% | -9.38% | -15.63% | -17.19% | -6.25% | -14.06% | -9.38% | -17.19% |
| es_gpqa_diamond_acc_norm | **0.323** | 0.268 | 0.293 | 0.273 | 0.268 | 0.303 | 0.278 | 0.293 | 0.268 |
| es_gpqa_diamond_acc_norm_gain_base | -- | -17.19% | -9.38% | -15.63% | -17.19% | -6.25% | -14.06% | -9.38% | -17.19% |
| es_hellaswag_acc | 0.533 | 0.525 | 0.528 | 0.534 | 0.534 | 0.533 | 0.530 | **0.535** | 0.525 |
| es_hellaswag_acc_gain_base | -- | -1.42% | -0.94% | +0.24% | +0.24% | +0.14% | -0.44% | +0.48% | -1.40% |
| es_hellaswag_acc_norm | **0.716** | 0.695 | 0.702 | 0.706 | 0.708 | 0.710 | 0.708 | 0.701 | 0.701 |
| es_hellaswag_acc_norm_gain_base | -- | -2.85% | -1.92% | -1.36% | -1.13% | -0.75% | -1.06% | -2.03% | -2.12% |
| es_mgsm_direct | **0.280** | 0.228 | 0.224 | 0.180 | 0.172 | 0.192 | 0.184 | 0.200 | 0.128 |
| es_mgsm_direct_gain_base | -- | -18.57% | -20.00% | -35.71% | -38.57% | -31.43% | -34.29% | -28.57% | -54.29% |
| es_mgsm_direct_exact_match_stderr | **0.028** | 0.027 | 0.026 | 0.024 | 0.024 | 0.025 | 0.025 | 0.025 | 0.021 |
| es_mgsm_direct_exact_match_stderr_gain_base | -- | -6.56% | -7.14% | -14.43% | -15.95% | -12.28% | -13.70% | -10.91% | -25.59% |
| es_multiwikiqa_exact_match | 0.146 | 0.239 | 0.233 | 0.360 | 0.351 | 0.371 | **0.387** | 0.364 | 0.366 |
| es_multiwikiqa_exact_match_gain_base | -- | +63.42% | +59.86% | +146.58% | +140.27% | +153.84% | +164.93% | +149.32% | +150.68% |
| es_multiwikiqa_f1 | 0.222 | 0.484 | 0.468 | 0.566 | 0.562 | 0.556 | **0.597** | 0.572 | 0.567 |
| es_multiwikiqa_f1_gain_base | -- | +118.17% | +111.38% | +155.47% | +153.50% | +150.89% | +169.34% | +158.23% | +155.99% |
| es_piqa_acc | **0.830** | 0.800 | 0.800 | 0.780 | 0.770 | 0.790 | 0.780 | 0.800 | 0.790 |
| es_piqa_acc_gain_base | -- | -3.61% | -3.61% | -6.02% | -7.23% | -4.82% | -6.02% | -3.61% | -4.82% |
| es_piqa_acc_bytes | **0.830** | 0.800 | 0.780 | 0.740 | 0.780 | 0.790 | 0.760 | 0.800 | 0.790 |
| es_piqa_acc_bytes_gain_base | -- | -3.61% | -6.02% | -10.84% | -6.02% | -4.82% | -8.43% | -3.61% | -4.82% |
| es_piqa_acc_norm | **0.830** | 0.800 | 0.780 | 0.750 | 0.790 | 0.790 | 0.760 | 0.810 | 0.790 |
| es_piqa_acc_norm_gain_base | -- | -3.61% | -6.02% | -9.64% | -4.82% | -4.82% | -8.43% | -2.41% | -4.82% |
| es_truthfulqa_mc1_acc | 0.259 | 0.256 | 0.261 | 0.251 | **0.270** | 0.245 | 0.240 | 0.242 | 0.240 |
| es_truthfulqa_mc1_acc_gain_base | -- | -0.98% | +0.98% | -2.94% | +4.41% | -5.39% | -7.35% | -6.37% | -7.35% |
| es_xnli_acc | 0.476 | 0.471 | 0.470 | 0.470 | **0.500** | 0.467 | 0.475 | 0.477 | 0.490 |
| es_xnli_acc_gain_base | -- | -1.10% | -1.27% | -1.27% | +5.06% | -1.77% | -0.17% | +0.25% | +2.95% |
| es_xstorycloze_acc | 0.717 | 0.716 | 0.720 | 0.719 | 0.722 | **0.732** | 0.725 | 0.719 | 0.717 |
| es_xstorycloze_acc_gain_base | -- | -0.18% | +0.37% | +0.28% | +0.65% | +2.03% | +1.11% | +0.28% | +0.00% |
| Average of variant across benchmarks | **0.591** | 0.573 | 0.565 | 0.578 | 0.581 | 0.577 | 0.588 | 0.590 | 0.576 |
| Average of variant gain in relation to base across benchmarks | -- | +1.83% | +0.89% | +5.98% | +6.11% | +6.55% | +8.33% | +8.24% | +4.69% |

## English benchmarks

| metric | base | full_C1_kuatia | full_C2_kuatia_no_synthetic | full_C3_kuatia_es20 | full_C4_kuatia_no_synthetic_es20 | full_C5_kuatia_en20 | full_C6_kuatia_no_synthetic_en20 | full_C7_kuatia_es10_en10 | full_C8_kuatia_no_synthetic_es10_en10 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| en_arc_challenge_acc | **0.566** | 0.539 | 0.520 | 0.538 | 0.538 | 0.544 | 0.547 | 0.532 | 0.544 |
| en_arc_challenge_acc_gain_base | -- | -4.68% | -8.14% | -4.98% | -4.98% | -3.92% | -3.32% | -5.88% | -3.92% |
| en_arc_challenge_acc_norm | **0.596** | 0.567 | 0.551 | 0.564 | 0.558 | 0.562 | 0.582 | 0.569 | 0.564 |
| en_arc_challenge_acc_norm_gain_base | -- | -5.01% | -7.58% | -5.44% | -6.44% | -5.72% | -2.43% | -4.58% | -5.44% |
| en_arc_easy_acc | **0.848** | 0.814 | 0.821 | 0.810 | 0.816 | 0.820 | 0.837 | 0.819 | 0.816 |
| en_arc_easy_acc_gain_base | -- | -4.02% | -3.13% | -4.47% | -3.77% | -3.23% | -1.24% | -3.43% | -3.67% |
| en_arc_easy_acc_norm | **0.852** | 0.797 | 0.811 | 0.803 | 0.814 | 0.813 | 0.829 | 0.808 | 0.806 |
| en_arc_easy_acc_norm_gain_base | -- | -6.42% | -4.84% | -5.73% | -4.45% | -4.59% | -2.67% | -5.14% | -5.34% |
| en_bbh | **0.027** | 0.005 | 0.007 | 0.009 | 0.016 | 0.015 | 0.008 | 0.011 | 0.009 |
| en_bbh_gain_base | -- | -83.15% | -75.28% | -68.54% | -42.13% | -44.38% | -71.91% | -60.11% | -67.42% |
| en_bbh__stderr | **0.002** | 0.001 | 0.001 | 0.001 | 0.001 | 0.001 | 0.001 | 0.001 | 0.001 |
| en_bbh__stderr_gain_base | -- | -56.06% | -46.98% | -40.12% | -21.09% | -22.68% | -42.83% | -32.50% | -38.86% |
| en_bbh_boolean_expressions | 0.032 | 0.008 | 0.016 | 0.036 | **0.172** | 0.020 | 0.016 | 0.012 | 0.000 |
| en_bbh_boolean_expressions_gain_base | -- | -75.00% | -50.00% | +12.50% | +437.50% | -37.50% | -50.00% | -62.50% | -100.00% |
| en_bbh_boolean_expressions__stderr | 0.011 | 0.006 | 0.008 | 0.012 | **0.024** | 0.009 | 0.008 | 0.007 | 0.000 |
| en_bbh_boolean_expressions__stderr_gain_base | -- | -49.38% | -28.71% | +5.85% | +114.42% | -20.45% | -28.71% | -38.13% | -100.00% |
| en_bbh_causal_judgement | **0.016** | 0.000 | 0.000 | 0.000 | 0.005 | **0.016** | 0.005 | 0.000 | 0.005 |
| en_bbh_causal_judgement_gain_base | -- | -100.00% | -100.00% | -100.00% | -66.67% | +0.00% | -66.67% | -100.00% | -66.67% |
| en_bbh_causal_judgement__stderr | 0.009 | 0.000 | 0.000 | 0.000 | 0.005 | **0.009** | 0.005 | 0.000 | 0.005 |
| en_bbh_causal_judgement__stderr_gain_base | -- | -100.00% | -100.00% | -100.00% | -41.95% | +0.00% | -41.95% | -100.00% | -41.95% |
| en_bbh_date_understanding | **0.136** | 0.008 | 0.004 | 0.028 | 0.052 | 0.024 | 0.004 | 0.016 | 0.000 |
| en_bbh_date_understanding_gain_base | -- | -94.12% | -97.06% | -79.41% | -61.76% | -82.35% | -97.06% | -88.24% | -100.00% |
| en_bbh_date_understanding__stderr | **0.022** | 0.006 | 0.004 | 0.010 | 0.014 | 0.010 | 0.004 | 0.008 | 0.000 |
| en_bbh_date_understanding__stderr_gain_base | -- | -74.01% | -81.59% | -51.87% | -35.23% | -55.35% | -81.59% | -63.40% | -100.00% |
| en_bbh_disambiguation_qa | 0.000 | 0.000 | 0.004 | 0.000 | 0.000 | **0.040** | 0.008 | 0.008 | 0.000 |
| en_bbh_disambiguation_qa_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_disambiguation_qa__stderr | 0.000 | 0.000 | 0.004 | 0.000 | 0.000 | **0.012** | 0.006 | 0.006 | 0.000 |
| en_bbh_disambiguation_qa__stderr_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_dyck_languages | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** |
| en_bbh_dyck_languages_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_dyck_languages__stderr | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** |
| en_bbh_dyck_languages__stderr_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_formal_fallacies | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | **0.008** |
| en_bbh_formal_fallacies_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_formal_fallacies__stderr | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | **0.006** |
| en_bbh_formal_fallacies__stderr_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_geometric_shapes | **0.004** | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 |
| en_bbh_geometric_shapes_gain_base | -- | -100.00% | -100.00% | -100.00% | -100.00% | -100.00% | -100.00% | -100.00% | -100.00% |
| en_bbh_geometric_shapes__stderr | **0.004** | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 |
| en_bbh_geometric_shapes__stderr_gain_base | -- | -100.00% | -100.00% | -100.00% | -100.00% | -100.00% | -100.00% | -100.00% | -100.00% |
| en_bbh_hyperbaton | 0.000 | 0.000 | **0.004** | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 |
| en_bbh_hyperbaton_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_hyperbaton__stderr | 0.000 | 0.000 | **0.004** | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 |
| en_bbh_hyperbaton__stderr_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_logical_deduction_five_objects | 0.000 | 0.004 | **0.024** | 0.004 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 |
| en_bbh_logical_deduction_five_objects_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_logical_deduction_five_objects__stderr | 0.000 | 0.004 | **0.010** | 0.004 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 |
| en_bbh_logical_deduction_five_objects__stderr_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_logical_deduction_seven_objects | **0.016** | 0.004 | 0.012 | 0.012 | 0.004 | 0.000 | **0.016** | 0.000 | 0.004 |
| en_bbh_logical_deduction_seven_objects_gain_base | -- | -75.00% | -25.00% | -25.00% | -75.00% | -100.00% | +0.00% | -100.00% | -75.00% |
| en_bbh_logical_deduction_seven_objects__stderr | **0.008** | 0.004 | 0.007 | 0.007 | 0.004 | 0.000 | 0.008 | 0.000 | 0.004 |
| en_bbh_logical_deduction_seven_objects__stderr_gain_base | -- | -49.70% | -13.22% | -13.22% | -49.70% | -100.00% | -0.00% | -100.00% | -49.70% |
| en_bbh_logical_deduction_three_objects | **0.024** | 0.000 | 0.000 | 0.016 | 0.000 | 0.004 | 0.000 | 0.000 | 0.008 |
| en_bbh_logical_deduction_three_objects_gain_base | -- | -100.00% | -100.00% | -33.33% | -100.00% | -83.33% | -100.00% | -100.00% | -66.67% |
| en_bbh_logical_deduction_three_objects__stderr | **0.010** | 0.000 | 0.000 | 0.008 | 0.000 | 0.004 | 0.000 | 0.000 | 0.006 |
| en_bbh_logical_deduction_three_objects__stderr_gain_base | -- | -100.00% | -100.00% | -18.02% | -100.00% | -58.76% | -100.00% | -100.00% | -41.79% |
| en_bbh_movie_recommendation | 0.000 | 0.000 | 0.000 | 0.004 | 0.016 | 0.004 | **0.028** | 0.000 | 0.020 |
| en_bbh_movie_recommendation_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_movie_recommendation__stderr | 0.000 | 0.000 | 0.000 | 0.004 | 0.008 | 0.004 | **0.010** | 0.000 | 0.009 |
| en_bbh_movie_recommendation__stderr_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_multistep_arithmetic_two | 0.060 | 0.064 | **0.080** | 0.004 | 0.000 | 0.004 | 0.000 | 0.068 | 0.036 |
| en_bbh_multistep_arithmetic_two_gain_base | -- | +6.67% | +33.33% | -93.33% | -100.00% | -93.33% | -100.00% | +13.33% | -40.00% |
| en_bbh_multistep_arithmetic_two__stderr | 0.015 | 0.016 | **0.017** | 0.004 | 0.000 | 0.004 | 0.000 | 0.016 | 0.012 |
| en_bbh_multistep_arithmetic_two__stderr_gain_base | -- | +3.06% | +14.24% | -73.42% | -100.00% | -73.42% | -100.00% | +6.00% | -21.56% |
| en_bbh_navigate | **0.292** | 0.000 | 0.000 | 0.080 | 0.056 | 0.076 | 0.024 | 0.024 | 0.064 |
| en_bbh_navigate_gain_base | -- | -100.00% | -100.00% | -72.60% | -80.82% | -73.97% | -91.78% | -91.78% | -78.08% |
| en_bbh_navigate__stderr | **0.029** | 0.000 | 0.000 | 0.017 | 0.015 | 0.017 | 0.010 | 0.010 | 0.016 |
| en_bbh_navigate__stderr_gain_base | -- | -100.00% | -100.00% | -40.33% | -49.43% | -41.72% | -66.34% | -66.34% | -46.17% |
| en_bbh_object_counting | 0.000 | 0.004 | 0.000 | 0.000 | 0.000 | 0.000 | **0.016** | 0.000 | 0.000 |
| en_bbh_object_counting_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_object_counting__stderr | 0.000 | 0.004 | 0.000 | 0.000 | 0.000 | 0.000 | **0.008** | 0.000 | 0.000 |
| en_bbh_object_counting__stderr_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_penguins_in_a_table | 0.000 | 0.000 | 0.000 | 0.000 | 0.034 | **0.048** | **0.048** | 0.021 | 0.007 |
| en_bbh_penguins_in_a_table_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_penguins_in_a_table__stderr | 0.000 | 0.000 | 0.000 | 0.000 | 0.015 | **0.018** | **0.018** | 0.012 | 0.007 |
| en_bbh_penguins_in_a_table__stderr_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_reasoning_about_colored_objects | 0.008 | 0.000 | 0.000 | 0.004 | **0.048** | 0.008 | 0.008 | 0.012 | 0.000 |
| en_bbh_reasoning_about_colored_objects_gain_base | -- | -100.00% | -100.00% | -50.00% | +500.00% | +0.00% | +0.00% | +50.00% | -100.00% |
| en_bbh_reasoning_about_colored_objects__stderr | 0.006 | 0.000 | 0.000 | 0.004 | **0.014** | 0.006 | 0.006 | 0.007 | 0.000 |
| en_bbh_reasoning_about_colored_objects__stderr_gain_base | -- | -100.00% | -100.00% | -29.15% | +139.96% | -0.00% | +0.00% | +22.23% | -100.00% |
| en_bbh_ruin_names | 0.000 | 0.004 | 0.004 | 0.000 | 0.000 | 0.000 | 0.004 | 0.000 | **0.008** |
| en_bbh_ruin_names_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_ruin_names__stderr | 0.000 | 0.004 | 0.004 | 0.000 | 0.000 | 0.000 | 0.004 | 0.000 | **0.006** |
| en_bbh_ruin_names__stderr_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_salient_translation_error_detection | 0.000 | 0.004 | 0.000 | 0.004 | 0.004 | 0.000 | 0.000 | **0.008** | 0.000 |
| en_bbh_salient_translation_error_detection_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_salient_translation_error_detection__stderr | 0.000 | 0.004 | 0.000 | 0.004 | 0.004 | 0.000 | 0.000 | **0.006** | 0.000 |
| en_bbh_salient_translation_error_detection__stderr_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_snarks | 0.006 | **0.011** | **0.011** | 0.000 | 0.000 | 0.000 | **0.011** | 0.000 | **0.011** |
| en_bbh_snarks_gain_base | -- | +100.00% | +100.00% | -100.00% | -100.00% | -100.00% | +100.00% | -100.00% | +100.00% |
| en_bbh_snarks__stderr | 0.006 | 0.008 | **0.008** | 0.000 | 0.000 | 0.000 | 0.008 | 0.000 | 0.008 |
| en_bbh_snarks__stderr_gain_base | -- | +41.02% | +41.02% | -100.00% | -100.00% | -100.00% | +41.02% | -100.00% | +41.02% |
| en_bbh_sports_understanding | **0.016** | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 |
| en_bbh_sports_understanding_gain_base | -- | -100.00% | -100.00% | -100.00% | -100.00% | -100.00% | -100.00% | -100.00% | -100.00% |
| en_bbh_sports_understanding__stderr | **0.008** | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 | 0.000 |
| en_bbh_sports_understanding__stderr_gain_base | -- | -100.00% | -100.00% | -100.00% | -100.00% | -100.00% | -100.00% | -100.00% | -100.00% |
| en_bbh_temporal_sequences | 0.028 | 0.008 | 0.012 | 0.020 | 0.020 | **0.168** | 0.024 | 0.028 | 0.044 |
| en_bbh_temporal_sequences_gain_base | -- | -71.43% | -57.14% | -28.57% | -28.57% | +500.00% | -14.29% | +0.00% | +57.14% |
| en_bbh_temporal_sequences__stderr | 0.010 | 0.006 | 0.007 | 0.009 | 0.009 | **0.024** | 0.010 | 0.010 | 0.013 |
| en_bbh_temporal_sequences__stderr_gain_base | -- | -46.00% | -34.00% | -15.14% | -15.14% | +126.62% | -7.23% | +0.00% | +24.32% |
| en_bbh_tracking_shuffled_objects_five_objects | **0.044** | 0.004 | 0.000 | 0.004 | 0.000 | 0.000 | 0.008 | 0.028 | 0.008 |
| en_bbh_tracking_shuffled_objects_five_objects_gain_base | -- | -90.91% | -100.00% | -90.91% | -100.00% | -100.00% | -81.82% | -36.36% | -81.82% |
| en_bbh_tracking_shuffled_objects_five_objects__stderr | **0.013** | 0.004 | 0.000 | 0.004 | 0.000 | 0.000 | 0.006 | 0.010 | 0.006 |
| en_bbh_tracking_shuffled_objects_five_objects__stderr_gain_base | -- | -69.22% | -100.00% | -69.22% | -100.00% | -100.00% | -56.56% | -19.56% | -56.56% |
| en_bbh_tracking_shuffled_objects_seven_objects | **0.032** | 0.000 | 0.008 | 0.008 | 0.016 | 0.004 | 0.000 | 0.008 | 0.012 |
| en_bbh_tracking_shuffled_objects_seven_objects_gain_base | -- | -100.00% | -75.00% | -75.00% | -50.00% | -87.50% | -100.00% | -75.00% | -62.50% |
| en_bbh_tracking_shuffled_objects_seven_objects__stderr | **0.011** | 0.000 | 0.006 | 0.006 | 0.008 | 0.004 | 0.000 | 0.006 | 0.007 |
| en_bbh_tracking_shuffled_objects_seven_objects__stderr_gain_base | -- | -100.00% | -49.38% | -49.38% | -28.71% | -64.14% | -100.00% | -49.38% | -38.13% |
| en_bbh_tracking_shuffled_objects_three_objects | 0.004 | 0.000 | 0.000 | 0.000 | 0.000 | 0.004 | 0.004 | **0.060** | 0.004 |
| en_bbh_tracking_shuffled_objects_three_objects_gain_base | -- | -100.00% | -100.00% | -100.00% | -100.00% | +0.00% | +0.00% | +1400.00% | +0.00% |
| en_bbh_tracking_shuffled_objects_three_objects__stderr | 0.004 | 0.000 | 0.000 | 0.000 | 0.000 | 0.004 | 0.004 | **0.015** | 0.004 |
| en_bbh_tracking_shuffled_objects_three_objects__stderr_gain_base | -- | -100.00% | -100.00% | -100.00% | -100.00% | -0.00% | -0.00% | +276.25% | +0.00% |
| en_bbh_web_of_lies | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** |
| en_bbh_web_of_lies_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_web_of_lies__stderr | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** |
| en_bbh_web_of_lies__stderr_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_word_sorting | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** |
| en_bbh_word_sorting_gain_base | -- |  |  |  |  |  |  |  |  |
| en_bbh_word_sorting__stderr | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** | **0.000** |
| en_bbh_word_sorting__stderr_gain_base | -- |  |  |  |  |  |  |  |  |
| en_belebele_acc | **0.840** | 0.782 | 0.773 | 0.759 | 0.794 | 0.787 | 0.811 | 0.819 | 0.772 |
| en_belebele_acc_gain_base | -- | -6.88% | -7.94% | -9.66% | -5.42% | -6.35% | -3.44% | -2.51% | -8.07% |
| en_belebele_acc_norm | **0.840** | 0.782 | 0.773 | 0.759 | 0.794 | 0.787 | 0.811 | 0.819 | 0.772 |
| en_belebele_acc_norm_gain_base | -- | -6.88% | -7.94% | -9.66% | -5.42% | -6.35% | -3.44% | -2.51% | -8.07% |
| en_global_mmlu_lite_acc | **0.700** | 0.665 | 0.650 | 0.627 | 0.647 | 0.647 | 0.667 | 0.655 | 0.637 |
| en_global_mmlu_lite_acc_gain_base | -- | -5.00% | -7.14% | -10.36% | -7.50% | -7.50% | -4.64% | -6.43% | -8.93% |
| en_global_mmlu_lite_acc_norm | **0.700** | 0.665 | 0.650 | 0.627 | 0.647 | 0.647 | 0.667 | 0.655 | 0.637 |
| en_global_mmlu_lite_acc_norm_gain_base | -- | -5.00% | -7.14% | -10.36% | -7.50% | -7.50% | -4.64% | -6.43% | -8.93% |
| en_gpqa_diamond_zeroshot_acc | 0.258 | **0.288** | 0.268 | 0.263 | 0.283 | 0.268 | 0.283 | 0.253 | 0.253 |
| en_gpqa_diamond_zeroshot_acc_gain_base | -- | +11.76% | +3.92% | +1.96% | +9.80% | +3.92% | +9.80% | -1.96% | -1.96% |
| en_gpqa_diamond_zeroshot_acc_norm | 0.258 | **0.288** | 0.268 | 0.263 | 0.283 | 0.268 | 0.283 | 0.253 | 0.253 |
| en_gpqa_diamond_zeroshot_acc_norm_gain_base | -- | +11.76% | +3.92% | +1.96% | +9.80% | +3.92% | +9.80% | -1.96% | -1.96% |
| en_hellaswag_acc | 0.593 | 0.593 | 0.592 | 0.598 | 0.588 | 0.599 | **0.601** | 0.600 | 0.594 |
| en_hellaswag_acc_gain_base | -- | +0.15% | -0.12% | +0.89% | -0.79% | +1.16% | +1.48% | +1.31% | +0.22% |
| en_hellaswag_acc_norm | 0.785 | 0.786 | 0.786 | **0.792** | 0.787 | 0.790 | 0.791 | 0.790 | 0.784 |
| en_hellaswag_acc_norm_gain_base | -- | +0.06% | +0.01% | +0.85% | +0.15% | +0.65% | +0.66% | +0.60% | -0.18% |
| en_mgsm_direct | **0.320** | 0.204 | 0.168 | 0.168 | 0.112 | 0.280 | 0.232 | 0.232 | 0.212 |
| en_mgsm_direct_gain_base | -- | -36.25% | -47.50% | -47.50% | -65.00% | -12.50% | -27.50% | -27.50% | -33.75% |
| en_mgsm_direct_exact_match_stderr | **0.030** | 0.026 | 0.024 | 0.024 | 0.020 | 0.028 | 0.027 | 0.027 | 0.026 |
| en_mgsm_direct_exact_match_stderr_gain_base | -- | -13.61% | -19.85% | -19.85% | -32.39% | -3.75% | -9.51% | -9.51% | -12.38% |
| en_multiwikiqa_exact_match | 0.405 | 0.270 | 0.348 | 0.427 | 0.399 | 0.431 | **0.463** | 0.432 | 0.433 |
| en_multiwikiqa_exact_match_gain_base | -- | -33.35% | -14.16% | +5.28% | -1.53% | +6.27% | +14.16% | +6.66% | +6.76% |
| en_multiwikiqa_f1 | 0.563 | 0.521 | 0.572 | 0.586 | 0.611 | 0.614 | **0.652** | 0.627 | 0.615 |
| en_multiwikiqa_f1_gain_base | -- | -7.52% | +1.46% | +4.00% | +8.37% | +8.95% | +15.70% | +11.32% | +9.17% |
| en_piqa_acc | **0.796** | 0.782 | 0.787 | 0.792 | 0.794 | 0.786 | 0.794 | 0.795 | 0.788 |
| en_piqa_acc_gain_base | -- | -1.78% | -1.09% | -0.55% | -0.21% | -1.30% | -0.21% | -0.07% | -0.96% |
| en_piqa_acc_norm | 0.808 | 0.807 | 0.811 | 0.805 | 0.807 | 0.805 | **0.814** | 0.812 | 0.801 |
| en_piqa_acc_norm_gain_base | -- | -0.20% | +0.34% | -0.47% | -0.13% | -0.47% | +0.67% | +0.47% | -0.94% |
| en_truthfulqa_mc1_acc | **0.299** | 0.264 | 0.274 | 0.256 | 0.264 | 0.271 | 0.259 | 0.257 | 0.262 |
| en_truthfulqa_mc1_acc_gain_base | -- | -11.48% | -8.20% | -14.34% | -11.48% | -9.43% | -13.11% | -13.93% | -12.30% |
| en_winogrande_acc | 0.702 | 0.695 | 0.687 | 0.688 | **0.709** | 0.703 | 0.702 | 0.702 | 0.698 |
| en_winogrande_acc_gain_base | -- | -1.12% | -2.25% | -2.02% | +0.90% | +0.11% | +0.00% | +0.00% | -0.67% |
| en_xnli_acc | 0.546 | 0.525 | 0.524 | 0.507 | 0.533 | 0.543 | 0.535 | **0.550** | 0.547 |
| en_xnli_acc_gain_base | -- | -3.83% | -3.90% | -7.06% | -2.28% | -0.59% | -1.91% | +0.81% | +0.29% |
| en_xstorycloze_acc | 0.778 | 0.791 | 0.786 | 0.779 | 0.792 | **0.800** | 0.797 | 0.795 | 0.789 |
| en_xstorycloze_acc_gain_base | -- | +1.62% | +1.02% | +0.09% | +1.79% | +2.81% | +2.38% | +2.13% | +1.36% |
| Average of variant across benchmarks | **0.179** | 0.162 | 0.163 | 0.164 | 0.169 | 0.171 | 0.171 | 0.169 | 0.166 |
| Average of variant gain in relation to base across benchmarks | -- | -44.65% | -40.46% | -39.55% | -18.20% | -23.29% | -31.13% | -3.41% | -32.41% |


## Metric notes

| Metric | Benchmark | Language | Meaning and interpretation | Instances |
| --- | --- | --- | --- | ---: |
| flores200_en_to_gn_bleu | FLORES-200 EN→GN | Guarani (gn) | BLEU translation score; higher is better. | 1,012 |
| flores200_en_to_gn_chrf++ | FLORES-200 EN→GN | Guarani (gn) | Character n-gram F-score; higher is better. | 1,012 |
| flores200_es_to_gn_bleu | FLORES-200 ES→GN | Guarani (gn) | BLEU translation score; higher is better. | 1,012 |
| flores200_es_to_gn_chrf++ | FLORES-200 ES→GN | Guarani (gn) | Character n-gram F-score; higher is better. | 1,012 |
| gn_belebele_acc | Belebele | Guarani (gn) | Accuracy; higher is better. | 900 |
| gn_belebele_acc_norm | Belebele | Guarani (gn) | Length-normalized multiple-choice accuracy; higher is better. | 900 |
| gn_global_mmlu_lite_acc | Global MMLU Lite | Guarani (gn) | Accuracy; higher is better. | 400 |
| gn_global_mmlu_lite_acc_norm | Global MMLU Lite | Guarani (gn) | Length-normalized multiple-choice accuracy; higher is better. | 400 |
| gn_multiwikiqa_exact_match | MultiWikiQA | Guarani (gn) | Exact-match accuracy; higher is better. | 5,003 |
| gn_multiwikiqa_f1 | MultiWikiQA | Guarani (gn) | Token-overlap F1 score; higher is better. | 5,003 |
| es_arc_challenge_acc | ARC Challenge | Spanish (es) | Accuracy; higher is better. | 299 |
| es_arc_challenge_acc_norm | ARC Challenge | Spanish (es) | Length-normalized multiple-choice accuracy; higher is better. | 299 |
| es_arc_easy_acc | ARC Easy | Spanish (es) | Accuracy; higher is better. | 570 |
| es_arc_easy_acc_norm | ARC Easy | Spanish (es) | Length-normalized multiple-choice accuracy; higher is better. | 570 |
| es_belebele_acc | Belebele | Spanish (es) | Accuracy; higher is better. | 900 |
| es_belebele_acc_norm | Belebele | Spanish (es) | Length-normalized multiple-choice accuracy; higher is better. | 900 |
| es_copa_acc | Copa | Spanish (es) | Accuracy; higher is better. | 500 |
| es_global_mmlu_lite_acc | Global MMLU Lite | Spanish (es) | Accuracy; higher is better. | 400 |
| es_global_mmlu_lite_acc_norm | Global MMLU Lite | Spanish (es) | Length-normalized multiple-choice accuracy; higher is better. | 400 |
| es_gpqa_diamond_acc | GPQA Diamond | Spanish (es) | Accuracy; higher is better. | 198 |
| es_gpqa_diamond_acc_norm | GPQA Diamond | Spanish (es) | Length-normalized multiple-choice accuracy; higher is better. | 198 |
| es_hellaswag_acc | HellaSwag | Spanish (es) | Accuracy; higher is better. | 9,374 |
| es_hellaswag_acc_norm | HellaSwag | Spanish (es) | Length-normalized multiple-choice accuracy; higher is better. | 9,374 |
| es_mgsm_direct | MGSM | Spanish (es) | Exact-match accuracy; higher is better. | 250 |
| es_mgsm_direct_exact_match_stderr | MGSM | Spanish (es) | Exact-match accuracy; higher is better. | 250 |
| es_multiwikiqa_exact_match | MultiWikiQA | Spanish (es) | Exact-match accuracy; higher is better. | 5,001 |
| es_multiwikiqa_f1 | MultiWikiQA | Spanish (es) | Token-overlap F1 score; higher is better. | 5,001 |
| es_piqa_acc | PIQA | Spanish (es) | Accuracy; higher is better. | 100 |
| es_piqa_acc_bytes | PIQA | Spanish (es) | Accuracy; higher is better. | 100 |
| es_piqa_acc_norm | PIQA | Spanish (es) | Length-normalized multiple-choice accuracy; higher is better. | 100 |
| es_truthfulqa_mc1_acc | TruthfulQA MC1 | Spanish (es) | Accuracy; higher is better. | 789 |
| es_xnli_acc | XNLI | Spanish (es) | Accuracy; higher is better. | 2,490 |
| es_xstorycloze_acc | XStoryCloze | Spanish (es) | Accuracy; higher is better. | 1,511 |
| flores200_gn_to_es_bleu | FLORES-200 GN→ES | Spanish (es) | BLEU translation score; higher is better. | 1,012 |
| flores200_gn_to_es_chrf++ | FLORES-200 GN→ES | Spanish (es) | Character n-gram F-score; higher is better. | 1,012 |
| en_arc_challenge_acc | ARC Challenge | English (en) | Accuracy; higher is better. | 1,172 |
| en_arc_challenge_acc_norm | ARC Challenge | English (en) | Length-normalized multiple-choice accuracy; higher is better. | 1,172 |
| en_arc_easy_acc | ARC Easy | English (en) | Accuracy; higher is better. | 2,376 |
| en_arc_easy_acc_norm | ARC Easy | English (en) | Length-normalized multiple-choice accuracy; higher is better. | 2,376 |
| en_bbh | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | not recorded |
| en_bbh__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | not recorded |
| en_bbh_boolean_expressions | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_boolean_expressions__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_causal_judgement | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 187 |
| en_bbh_causal_judgement__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 187 |
| en_bbh_date_understanding | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_date_understanding__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_disambiguation_qa | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_disambiguation_qa__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_dyck_languages | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_dyck_languages__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_formal_fallacies | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_formal_fallacies__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_geometric_shapes | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_geometric_shapes__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_hyperbaton | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_hyperbaton__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_logical_deduction_five_objects | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_logical_deduction_five_objects__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_logical_deduction_seven_objects | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_logical_deduction_seven_objects__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_logical_deduction_three_objects | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_logical_deduction_three_objects__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_movie_recommendation | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_movie_recommendation__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_multistep_arithmetic_two | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_multistep_arithmetic_two__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_navigate | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_navigate__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_object_counting | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_object_counting__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_penguins_in_a_table | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 146 |
| en_bbh_penguins_in_a_table__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 146 |
| en_bbh_reasoning_about_colored_objects | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_reasoning_about_colored_objects__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_ruin_names | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_ruin_names__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_salient_translation_error_detection | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_salient_translation_error_detection__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_snarks | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 178 |
| en_bbh_snarks__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 178 |
| en_bbh_sports_understanding | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_sports_understanding__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_temporal_sequences | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_temporal_sequences__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_tracking_shuffled_objects_five_objects | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_tracking_shuffled_objects_five_objects__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_tracking_shuffled_objects_seven_objects | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_tracking_shuffled_objects_seven_objects__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_tracking_shuffled_objects_three_objects | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_tracking_shuffled_objects_three_objects__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_web_of_lies | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_web_of_lies__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_word_sorting | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_bbh_word_sorting__stderr | BIG-Bench Hard | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_belebele_acc | Belebele | English (en) | Accuracy; higher is better. | 900 |
| en_belebele_acc_norm | Belebele | English (en) | Length-normalized multiple-choice accuracy; higher is better. | 900 |
| en_global_mmlu_lite_acc | Global MMLU Lite | English (en) | Accuracy; higher is better. | 400 |
| en_global_mmlu_lite_acc_norm | Global MMLU Lite | English (en) | Length-normalized multiple-choice accuracy; higher is better. | 400 |
| en_gpqa_diamond_zeroshot_acc | GPQA Diamond | English (en) | Accuracy; higher is better. | 198 |
| en_gpqa_diamond_zeroshot_acc_norm | GPQA Diamond | English (en) | Length-normalized multiple-choice accuracy; higher is better. | 198 |
| en_hellaswag_acc | HellaSwag | English (en) | Accuracy; higher is better. | 10,042 |
| en_hellaswag_acc_norm | HellaSwag | English (en) | Length-normalized multiple-choice accuracy; higher is better. | 10,042 |
| en_mgsm_direct | MGSM | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_mgsm_direct_exact_match_stderr | MGSM | English (en) | Exact-match accuracy; higher is better. | 250 |
| en_multiwikiqa_exact_match | MultiWikiQA | English (en) | Exact-match accuracy; higher is better. | 4,999 |
| en_multiwikiqa_f1 | MultiWikiQA | English (en) | Token-overlap F1 score; higher is better. | 4,999 |
| en_piqa_acc | PIQA | English (en) | Accuracy; higher is better. | 1,838 |
| en_piqa_acc_norm | PIQA | English (en) | Length-normalized multiple-choice accuracy; higher is better. | 1,838 |
| en_truthfulqa_mc1_acc | TruthfulQA MC1 | English (en) | Accuracy; higher is better. | 817 |
| en_winogrande_acc | WinoGrande | English (en) | Accuracy; higher is better. | 1,267 |
| en_xnli_acc | XNLI | English (en) | Accuracy; higher is better. | 2,490 |
| en_xstorycloze_acc | XStoryCloze | English (en) | Accuracy; higher is better. | 1,511 |
| flores200_gn_to_en_bleu | FLORES-200 GN→EN | English (en) | BLEU translation score; higher is better. | 1,012 |
| flores200_gn_to_en_chrf++ | FLORES-200 GN→EN | English (en) | Character n-gram F-score; higher is better. | 1,012 |
| gn_bits_per_byte | CoreGuapa perplexity | Guarani (gn) | Bits per byte; lower is better. | 66 |
| gn_byte_perplexity | CoreGuapa perplexity | Guarani (gn) | Byte-level perplexity; lower is better. | 66 |
| gn_word_perplexity | CoreGuapa perplexity | Guarani (gn) | Word-level perplexity; lower is better. | 66 |
