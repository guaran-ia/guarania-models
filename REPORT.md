# Building the GuaranIA LLM

This is a living document that describes the approach followed to develop the LLMs for the project 
[GuaranIA](https://www.guarania.org). The building process follows the 
[BYOL](https://arxiv.org/abs/2601.10804) methodology, which is implemented through 
the in-house framework [Guaratune](https://github.com/guaran-ia/guaratune).
**The main idea is to adapt a multilingual open-source multilingual base model (e.g., Goolge Gemma-4) 
to Guarani while aiming to retain its existing capabilities.**

## BYOL methodology in a nutshell

The BYOL methodology consists of three steps: `continual pretraining (CPT)`, where the
base model continues training on a curated langage corpus, `supervised fine-tuning (SFT)`, 
where the CPT model is futher trained on instruction-and-response examples, and `model 
merging`, where the adapted model is combined with the original model in weight space.
See the [BYOL paper](https://arxiv.org/abs/2601.10804) for more information about 
the framework.

## GuaranIA approach

### Continual pretraining (CPT)

#### Finding the dataset configuration

The guarani corpus [Kuatia](https://huggingface.co/datasets/guaran-ia/kuatia)
augmented with [Spanish](https://huggingface.co/datasets/Helsinki-NLP/fineweb-edu-translated) 
and [English](https://huggingface.co/datasets/HuggingFaceFW/fineweb-edu) FineWeb-Edu 
samples are proposed to be used to build the GuaranIA LLMs. The three sources were 
combined into eigth different data configurations for `full CPT` (i.e., all model weights are updated) of [Gemma-4 E4B-PT](https://huggingface.co/google/gemma-4-E4B) to identify the most promising configuration.

* `C1`: Kuatia (`43,677,319` tokens)
* `C2`: Kuatia without synthetic documents (`27,994,685` tokens)
* `C3`: Kuatia + 20% Spanish FineWeb-Edu (`52,415,631` tokens)
* `C4`: Kuatia without synthetic documents + 20% Spanish FineWeb-Edu (`36,732,997` tokens)
* `C5`: Kuatia + 20% FineWeb-Edu (`52,412,827` tokens)
* `C6`: Kuatia without synthetic documents + 20% FineWeb-Edu (`36,730,193` tokens)
* `C7`: Kuatia + 10% Spanish FineWeb-Edu + 10% FineWeb-Edu (`52,415,521` tokens)
* `C8`: Kuatia without synthetic documents + 10% Spanish FineWeb-Edu + 10% FineWeb-Edu (`36,732,887` tokens)

##### CPT Hyperparameters

For Gemma-4 E4B CPT, the experiment configuration uses a sequence length of `2,048`,
four epochs, a per-device batch size of `1`, and a learning rate of `2e-5` with a cosine
scheduler and `2e-6` minimum. Training uses packed sequences, `bfloat16`, AdamW
(betas `0.9` and `0.999`), `3%` warmup, and gradient clipping at `1.0`. Evaluation runs
at the end of each epoch. Full CPT uses gradient accumulation of `32` and weight decay of `0.01`.

#### Evaluation

The eight trained variants (C1-C8) are evaluated against the base model on Guarani, Spanish, 
and English benchmarks, including language understanding, reading comprenhension, 
question answering, translation, and perplexity tasks.  The table below lists each benchmark, 
its language (`GN` = Guarani, `ES` = Spanish, `EN` = English), the capability and task it 
assesses, as well as the metric, number of evaluation instances, number of shots, 
and score split.

| Benchmark | Language | Capacity | Task | Metric | Instances | Shots | Score Split |
| --- | --- | --- | --- | --- | --- | --- | --- |
| [ARC Challenge](https://huggingface.co/datasets/BSC-LT/arc_es/viewer/ARC_Challenge_es) | ES | Specialized reasoning (science) | Multiple-choice QA | Normalized accuracy | 299 | 25 | validation |
| [ARC Challenge](https://huggingface.co/datasets/allenai/ai2_arc/viewer/ARC-Challenge/validation) | EN | Specialized reasoning (science) | Multiple-choice QA | Normalized accuracy | 299 | 25 | validation |
| [ARC Easy](https://huggingface.co/datasets/BSC-LT/arc_es/viewer/ARC_Easy_es) | ES | Specialized reasoning (science) | Multiple-choice QA | Normalized accuracy | 570 | 0 | validation |
| [ARC Easy](https://huggingface.co/datasets/allenai/ai2_arc/viewer/ARC-Easy/validation) | EN | Specialized reasoning (science) | Multiple-choice QA | Normalized accuracy | 570 | 0 | validation |
| [Belebele](https://huggingface.co/datasets/facebook/belebele/viewer/grn_Latn) | GN | Reading comprehension | Multiple-choice QA | Accuracy | 900 | 1 | test |
| [Belebele](https://huggingface.co/datasets/facebook/belebele/viewer/spa_Latn) | ES | Reading comprehension | Multiple-choice QA | Accuracy | 900 | 1 | test |
| [Belebele](https://huggingface.co/datasets/facebook/belebele/viewer/eng_Latn) | EN | Reading comprehension | Multiple-choice QA | Accuracy | 900 | 1 | test |
| [COPA](https://huggingface.co/datasets/BSC-LT/COPA-es) | ES | Causal reasoning | Multiple-choice QA | Accuracy | 100 | 0 | validation |
| [COPA](https://huggingface.co/datasets/aps/super_glue/viewer/copa/validation) | EN | Causal reasoning | Multiple-choice QA | Accuracy | 100 | 0 | validation |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus/viewer/gug_Latn/dev) | GN | Translation | Generation | BLEU, chrF++ | 997 | 1 | dev |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus/viewer/spa_Latn/dev) | ES | Translation | Generation | BLEU, chrF++ | 997 | 1 | dev |
| [FLORES+](https://huggingface.co/datasets/openlanguagedata/flores_plus/viewer/eng_Latn/dev) | EN | Translation | Generation | BLEU, chrF++ | 997 | 1 | dev |
| [Global MMLU Lite](data/evaluation/global-mmlu-lite) | GN | General knowledge | Multiple-choice QA | Accuracy | 400 | 5 | test |
| [Global MMLU Lite](https://huggingface.co/datasets/CohereLabs/Global-MMLU-Lite/viewer/es/test) | ES | General knowledge | Multiple-choice QA | Accuracy | 400 | 5 | test |
| [Global MMLU Lite](https://huggingface.co/datasets/CohereLabs/Global-MMLU-Lite/viewer/en/test) | EN | General knowledge | Multiple-choice QA | Accuracy | 400 | 5 | test |
| [Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel/viewer/spa_latn_spai) | ES | Common sense & inference | Multiple-choice QA | Normalized accuracy | 100 | 0 | test |
| [Global PIQA](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel/viewer/eng_latn) | EN | Common sense & inference | Multiple-choice QA | Normalized accuracy | 100 | 0 | test |
| [GPQA Main](https://huggingface.co/datasets/ellamind/gpqa-multilingual/viewer/spa) | ES | Specialized reasoning (biology, physics, chemistry) | Multiple-choice QA | Accuracy | 448 | 5 | train |
| [GPQA Main](https://huggingface.co/datasets/Idavidrein/gpqa/viewer/gpqa_main) | EN | Specialized reasoning (biology, physics, chemistry) | Multiple-choice QA | Accuracy | 448 | 5 | train |
| [HellaSwag](https://huggingface.co/datasets/alvarobartt/hellaswag-okapi-eval-es) | ES | Common sense & inference | Multiple-choice QA | Normalized accuracy | 9,374 | 10 | val |
| [HellaSwag](https://huggingface.co/datasets/Rowan/hellaswag/viewer/default/validation) | EN | Common sense & inference | Multiple-choice QA | Normalized accuracy | 10,042 | 10 | validation |
| [MGSM](data/evaluation/mgsm) | GN | Specialized reasoning (mathematics) | Generation | Exact match | 142 | 5 | test |
| [MGSM](https://huggingface.co/datasets/juletxara/mgsm/viewer/es/test) | ES | Specialized reasoning (mathematics) | Generation | Exact match | 250 | 0 | test |
| [MGSM](https://huggingface.co/datasets/juletxara/mgsm/viewer/en/test) | EN | Specialized reasoning (mathematics) | Generation | Exact match | 250 | 0 | test |
| [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa/viewer/gn) | GN | Reading comprehension | Generation | Exact match, F1 | 5,003 | 2 | train |
| [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa/viewer/es) | ES | Reading comprehension | Generation | Exact match, F1 | 5,001 | 2 | train |
| [MultiWikiQA](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa/viewer/en) | EN | Reading comprehension | Generation | Exact match, F1 | 4,999 | 2 | train |
| [TruthfulQA MC1](https://huggingface.co/datasets/HiTZ/truthfulqa-multi/viewer/es/validation) | ES | Truthfulness and factuality | Multiple-choice QA | Accuracy | 789 | 6 | val |
| [TruthfulQA MC1](https://huggingface.co/datasets/HiTZ/truthfulqa-multi/viewer/en/validation) | EN | Truthfulness and factuality | Multiple-choice QA | Accuracy | 817 | 6 | validation |
| [WNLI](data/evaluation/wnli) | GN | Common sense & inference | Multiple-choice QA | Accuracy | 49 | 5 | dev |
| [WNLI](https://huggingface.co/datasets/PlanTL-GOB-ES/wnli-es/blob/main/wnli-test-shuffled-es.csv) | ES | Common sense & inference | Multiple-choice QA | Accuracy | 71 | 5 | validation |
| [WNLI](https://huggingface.co/datasets/nyu-mll/glue/viewer/wnli/test) | EN | Common sense & inference | Multiple-choice QA | Accuracy | 71 | 5 | validation |
| [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze/viewer/es/eval) | ES | Common sense & inference | Multiple-choice QA | Accuracy | 1,511 | 5 | eval |
| [XStoryCloze](https://huggingface.co/datasets/juletxara/xstory_cloze/viewer/en/eval) | EN | Common sense & inference | Multiple-choice QA | Accuracy | 1,511 | 5 | eval |

> [!Important]
> Complementing the mentioned benchkmarks, we assess the language modeling capacity of the adapted model through `perplexity` on [COREGUAPA](https://corpus.spl.gov.py), a high-quality proprietary corpus curated by the [Paraguayan Secretariat of Linguistic Policy](https://spl.gov.py).

>[!Note]
> A Guarani version of `Global MMLU Lite`, `MGSM`, and `WLNI` were 
> created by language experts and are available at the framework [Guaratune](https://github.com/guaran-ia/guaratune/tree/main/data/evaluation) repo.

##### Data configuration results

**Perplexity**

Across the **`COREGUAPA` perplexity** evaluation, every `CPT` variant scores below the 
`Gemma-4 E4B` base model on all three reported metrics (i.e., `word perplexity`, 
`byte perplexity`, and `bits per byte`). As shown in the table below, **`C7`** (the data configuration 
that includes `Kuatia` both real and synthetic plus English and Spanish FineWeb-Edu) 
**has the lowest `word perplexity`, `byte perplexity`, and  `bits per byte` values**, compared with the base model. 

| Perplexity metric | base | C1 | C2 | C3 | C4 | C5 | C6 | C7 | C8 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| word perplexity | 3058.27 | 469.16 | 533.09 | 476.78 | 542.04 | 485.26 | 553.65 | **463.10** | 521.08 |
| byte perplexity | 2.64 | 2.11 | 2.14 | 2.11 | 2.14 | 2.11 | 2.15 | **2.10** | 2.13 |
| bits per byte | 1.40 | 1.07 | 1.10 | 1.08 | 1.10 | 1.08 | 1.10 | **1.07** | 1.09 |

*Note: In bold the lowest value per row*

The other `CPT` variants are close on `byte perplexity` (`2.11`–`2.15`) and 
`bits per byte` (`1.07`–`1.10`), so `C7`'s lead on those measures is small. **Lower 
values indicate better prediction of the evaluation text**. The report covers `66` 
`COREGUAPA` examples, so these results describe performance on thist high-quality 
set but they do not alone represent broad language ability, which is checked next. 

**Guarani performance**

The full CPT variants show a mixed pattern across the Guarani benchmarks. **All eight 
configurations improve on the base model in each of the four `FLORES+` translation directions**. `C3` 
has the highest `chrF++` for `English→Guarani` (`30.82` vs. `8.48` for the base), and 
`C1` is highest for `Spanish→Guarani` (`29.81` vs. `9.30`). `C7` produces the best 
scores for both `Guarani→English` (`44.47` vs. `37.94`) and `Guarani→Spanish` 
(`37.11` vs. `33.40`). Overall, **`C7` has the strongest translation profile**, leading
both directions from Guarani and performing close to the top variants on translations
into Guarani, as shown in the table below.

| benchmark | base | C1 | Gain C1 | C2 | Gain C2 | C3 | Gain C3 | C4 | Gain C4 | C5 | Gain C5 | C6 | Gain C6 | C7 | Gain C7 | C8 | Gain C8 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| FLORES+ EN->GN (chrF++) | 8.48 | 30.24 | +21.76 | 29.56 | +21.08 | **30.82** | +22.34 | 30.24 | +21.76 | 30.45 | +21.97 | 30.02 | +21.54 | 30.05 | +21.57 | 29.88 | +21.40 |
| FLORES+ ES->GN (chrF++) | 9.30 | **29.81** | +20.51 | 28.45 | +19.15 | 29.69 | +20.39 | 29.53 | +20.23 | 29.66 | +20.36 | 29.49 | +20.19 | 29.60 | +20.30 | 29.29 | +19.99 |
| FLORES+ GN->EN (chrF++) | 37.94 | 43.96 | +6.02 | 43.35 | +5.41 | 43.85 | +5.91 | 43.00 | +5.06 | 44.16 | +6.22 | 42.67 | +4.73 | **44.47** | +6.53 | 43.18 | +5.24 |
| FLORES+ GN->ES (chrF++) | 33.40 | 36.72 | +3.32 | 36.37 | +2.97 | 36.94 | +3.54 | 36.52 | +3.12 | 36.59 | +3.19 | 35.68 | +2.28 | **37.11** | +3.71 | 36.27 | +2.87 |

*Note: In bold the highest value per row. Gain columns show signed score-point differences from the corresponding base model.*

On the other tasks, gains are limited: **`C7` has the highest `Belebele` accuracy** 
(`55.56` vs. `52.22` for the base), and `C8` has the highest `WNLI` accuracy 
(`59.18` vs. `44.90`). As the table below outlines, every CPT variant scores below the base on Guarani 
`Global MMLU Lite` (`46.00`) and `MGSM` exact match (`9.86`), while all variants 
also trail the base on `MultiWikiQA` F1 (`42.83`). However, **C7 comes close to the 
base on the first two tasks**, with differences of only `0.50` points on 
`Global MMLU Lite` and `0.71` points on `MGSM`. These results migth suggest that 
the base model's existing Guarani capacity for these tasks limits what continued 
training on the available corpus can improve.

| benchmark | base | C1 | Gain C1 | C2 | Gain C2 | C3 | Gain C3 | C4  | Gain C4 | C5  | Gain C5 | C6  | Gain C6 | C7  | Gain C7 | C8  | Gain C8 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Belebele GN (acc) | 52.22 (48.95, 55.49) | 55.44 (52.19, 58.69) | +3.22 | 50.11 (46.84, 53.38) | -2.11 | 52.67 (49.41, 55.93) | +0.45 | 53.00 (49.74, 56.26) | +0.78 | 52.89 (49.63, 56.15) | +0.67 | 52.56 (49.30, 55.82) | +0.34 | **55.56 (52.31, 58.81)** | +3.34 | 55.11 (51.86, 58.36) | +2.89 |
| WNLI GN (acc) | 44.90 (30.83, 58.97) | 44.90 (30.83, 58.97) | +0.00 | 44.90 (30.83, 58.97) | +0.00 | 40.82 (26.92, 54.72) | -4.08 | 42.86 (28.86, 56.86) | -2.04 | 44.90 (30.83, 58.97) | +0.00 | 38.78 (25.00, 52.56) | -6.12 | 48.98 (34.84, 63.12) | +4.08 | **59.18 (45.28, 73.08)** | +14.28 |
| Global MMLU Lite GN (acc) | **46.00 (41.11, 50.89)** | 44.25 (39.38, 49.12) | -1.75 | 42.50 (37.65, 47.35) | -3.50 | 43.75 (38.88, 48.62) | -2.25 | 44.50 (39.62, 49.38) | -1.50 | 44.50 (39.62, 49.38) | -1.50 | 43.00 (38.14, 47.86) | -3.00 | 45.50 (40.61, 50.39) | -0.50 | 44.75 (39.87, 49.63) | -1.25 |
| MGSM GN (exact_match) | **9.86 (4.94, 14.78)** | 4.23 (0.91, 7.55) | -5.63 | 8.45 (3.86, 13.04) | -1.41 | 4.93 (1.36, 8.50) | -4.93 | 7.75 (3.34, 12.16) | -2.11 | 7.04 (2.82, 11.26) | -2.82 | 6.34 (2.32, 10.36) | -3.52 | 9.15 (4.39, 13.91) | -0.71 | 6.34 (2.32, 10.36) | -3.52 |
| MultiWikiQA GN (F1) | **42.83 (41.66, 44.00)** | 36.15 (35.05, 37.25) | -6.68 | 32.13 (31.07, 33.19) | -10.70 | 36.79 (35.68, 37.90) | -6.04 | 32.57 (31.51, 33.63) | -10.26 | 34.44 (33.35, 35.53) | -8.39 | 34.55 (33.45, 35.65) | -8.28 | 36.32 (35.21, 37.43) | -6.51 | 36.25 (35.13, 37.37) | -6.58 |

*Note: In bold the highest value per row. In parentheses the 95% confidence intervals (CI), which are approximate normal intervals computed as the score or average ± 1.96 times its standard error. Gain columns show signed score-point differences from the corresponding base model.*

Considering its leading results on both translation directions from Guarani, strong
`Belebele` score, and near-base results on `Global MMLU Lite` and `MGSM`, **`C7` highlights 
as the most promising variant for the Guarani capabilities emphasized here**, although 
`C8` showed the highest displayed average across all Guarani tasks (`37.81` vs. `37.42` of `C7`). 
So `C7` recommendation reflects the balance of capabilities described above rather than the aggregate average alone.

**Multilingual performance**

Across Spanish and English benchmarks, the CPT variants sometimes score above the base
and sometimes below it, as the tables below depict. Although the average scores are 
generally lower, the gaps from the base are modest. The smallest `Spanish` gap is `2.83` points 
(`C8=62.82` vs. `base=65.65`), and the smallest English gap is `2.20` points (`C5=63.15` vs. `base=65.35`). 
This overall proximity suggests that **multilingual performance is retained through CPT, despite task-level gains and losses**.

**Spanish benchmarks**

| benchmark | base  | C1  | Gain C1 | C2  | Gain C2 | C3  | Gain C3 | C4  | Gain C4 | C5  | Gain C5 | C6  | Gain C6 | C7  | Gain C7 | C8  | Gain C8 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Global MMLU Lite ES (acc) | **70.00 (65.50, 74.50)** | 63.75 (59.03, 68.47) | -6.25 | 63.50 (58.78, 68.22) | -6.50 | 63.75 (59.03, 68.47) | -6.25 | 62.75 (58.01, 67.49) | -7.25 | 63.25 (58.52, 67.98) | -6.75 | 63.75 (59.03, 68.47) | -6.25 | 63.50 (58.78, 68.22) | -6.50 | 63.25 (58.52, 67.98) | -6.75 |
| Belebele ES (acc) | **84.78 (82.43, 87.13)** | 78.56 (75.88, 81.24) | -6.22 | 77.89 (75.18, 80.60) | -6.89 | 79.11 (76.45, 81.77) | -5.67 | 78.22 (75.52, 80.92) | -6.56 | 78.67 (75.99, 81.35) | -6.11 | 79.56 (76.92, 82.20) | -5.22 | 80.33 (77.73, 82.93) | -4.45 | 79.78 (77.15, 82.41) | -5.00 |
| MultiWikiQA ES (F1) | **79.63 (78.72, 80.54)** | 70.36 (69.32, 71.40) | -9.27 | 68.14 (67.06, 69.22) | -11.49 | 70.27 (69.22, 71.32) | -9.36 | 69.63 (68.57, 70.69) | -10.00 | 71.19 (70.15, 72.23) | -8.44 | 71.25 (70.20, 72.30) | -8.38 | 70.76 (69.71, 71.81) | -8.87 | 70.15 (69.10, 71.20) | -9.48 |
| ARC Easy ES (acc_norm) | **89.47 (86.95, 91.99)** | 86.49 (83.68, 89.30) | -2.98 | 87.02 (84.26, 89.78) | -2.45 | 88.77 (86.18, 91.36) | -0.70 | 87.72 (85.02, 90.42) | -1.75 | 82.63 (79.52, 85.74) | -6.84 | 88.07 (85.41, 90.73) | -1.40 | 87.37 (84.64, 90.10) | -2.10 | 87.54 (84.83, 90.25) | -1.93 |
| ARC Challenge ES (acc_norm) | **81.94 (77.57, 86.31)** | 79.26 (74.66, 83.86) | -2.68 | 77.26 (72.50, 82.02) | -4.68 | 80.27 (75.75, 84.79) | -1.67 | 77.26 (72.50, 82.02) | -4.68 | 79.26 (74.66, 83.86) | -2.68 | 80.27 (75.75, 84.79) | -1.67 | 77.59 (72.86, 82.32) | -4.35 | 78.93 (74.30, 83.56) | -3.01 |
| PIQA ES (acc_norm) | **83.00 (75.60, 90.40)** | 79.00 (70.98, 87.02) | -4.00 | 78.00 (69.84, 86.16) | -5.00 | 76.00 (67.59, 84.41) | -7.00 | 79.00 (70.98, 87.02) | -4.00 | 80.00 (72.12, 87.88) | -3.00 | 77.00 (68.71, 85.29) | -6.00 | 79.00 (70.98, 87.02) | -4.00 | 78.00 (69.84, 86.16) | -5.00 |
| HellaSwag ES (acc_norm) | **73.49 (72.60, 74.38)** | 71.74 (70.83, 72.65) | -1.75 | 71.64 (70.73, 72.55) | -1.85 | 71.75 (70.84, 72.66) | -1.74 | 71.86 (70.95, 72.77) | -1.63 | 72.58 (71.68, 73.48) | -0.91 | 72.27 (71.36, 73.18) | -1.22 | 71.83 (70.92, 72.74) | -1.66 | 72.05 (71.14, 72.96) | -1.44 |
| COPA ES (acc) | 82.00 (74.43, 89.57) | 76.00 (67.59, 84.41) | -6.00 | 82.00 (74.43, 89.57) | +0.00 | 79.00 (70.98, 87.02) | -3.00 | 80.00 (72.12, 87.88) | -2.00 | 78.00 (69.84, 86.16) | -4.00 | 79.00 (70.98, 87.02) | -3.00 | **83.00 (75.60, 90.40)** | +1.00 | 77.00 (68.71, 85.29) | -5.00 |
| XStoryCloze ES (acc) | 75.25 (73.07, 77.43) | 73.66 (71.44, 75.88) | -1.59 | 74.59 (72.39, 76.79) | -0.66 | 74.12 (71.91, 76.33) | -1.13 | **75.31 (73.14, 77.48)** | +0.06 | 74.72 (72.53, 76.91) | -0.53 | 74.72 (72.53, 76.91) | -0.53 | 74.39 (72.19, 76.59) | -0.86 | 75.18 (73.00, 77.36) | -0.07 |
| TruthfulQA-MC1 ES (acc) | **32.07 (28.81, 35.33)** | 29.15 (25.98, 32.32) | -2.92 | 31.94 (28.68, 35.20) | -0.13 | 28.26 (25.12, 31.40) | -3.81 | 30.80 (27.58, 34.02) | -1.27 | 29.28 (26.10, 32.46) | -2.79 | 28.52 (25.37, 31.67) | -3.55 | 27.63 (24.51, 30.75) | -4.44 | 28.52 (25.37, 31.67) | -3.55 |
| WNLI ES (acc) | 43.66 (32.04, 55.28) | 52.11 (40.41, 63.81) | +8.45 | 45.07 (33.41, 56.73) | +1.41 | 47.89 (36.19, 59.59) | +4.23 | 40.85 (29.33, 52.37) | -2.81 | 43.66 (32.04, 55.28) | +0.00 | 43.66 (32.04, 55.28) | +0.00 | 42.25 (30.68, 53.82) | -1.41 | **59.15 (47.63, 70.67)** | +15.49 |
| MGSM ES (exact_match) | **27.20 (21.67, 32.73)** | 19.60 (14.67, 24.53) | -7.60 | 23.60 (18.33, 28.87) | -3.60 | 17.60 (12.87, 22.33) | -9.60 | 20.40 (15.39, 25.41) | -6.80 | 22.00 (16.85, 27.15) | -5.20 | 18.40 (13.59, 23.21) | -8.80 | 22.40 (17.22, 27.58) | -4.80 | 15.20 (10.74, 19.66) | -12.00 |
| GPQA Main ES (acc) | 31.03 (26.74, 35.32) | 28.12 (23.95, 32.29) | -2.91 | 29.69 (25.45, 33.93) | -1.34 | 31.47 (27.16, 35.78) | +0.44 | 30.36 (26.10, 34.62) | -0.67 | 27.68 (23.53, 31.83) | -3.35 | 25.45 (21.41, 29.49) | -5.58 | 28.12 (23.95, 32.29) | -2.91 | **31.92 (27.60, 36.24)** | +0.89 |
| Average | **65.65 (64.18, 67.12)** | 62.14 (60.62, 63.66) | -3.51 | 62.33 (60.82, 63.84) | -3.32 | 62.17 (60.66, 63.68) | -3.48 | 61.86 (60.36, 63.36) | -3.79 | 61.76 (60.25, 63.27) | -3.89 | 61.69 (60.19, 63.19) | -3.96 | 62.17 (60.69, 63.65) | -3.48 | 62.82 (61.32, 64.32) | -2.83 |

*Note: In bold the highest value per row. In parentheses the 95% confidence intervals (CI), which are approximate normal intervals computed as the score or average ± 1.96 times its standard error. Gain columns show signed score-point differences from the corresponding base model.*

**English benchmarks**

| benchmark | base  | C1  | Gain C1 | C2  | Gain C2 | C3  | Gain C3 | C4  | Gain C4 | C5  | Gain C5 | C6  | Gain C6 | C7  | Gain C7 | C8  | Gain C8 |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Global MMLU Lite EN (acc) | **74.25 (69.96, 78.54)** | 68.00 (63.42, 72.58) | -6.25 | 65.00 (60.32, 69.68) | -9.25 | 66.50 (61.87, 71.13) | -7.75 | 66.75 (62.13, 71.37) | -7.50 | 64.75 (60.06, 69.44) | -9.50 | 68.50 (63.94, 73.06) | -5.75 | 69.00 (64.46, 73.54) | -5.25 | 66.25 (61.61, 70.89) | -8.00 |
| Belebele EN (acc) | **89.78 (87.80, 91.76)** | 84.33 (81.95, 86.71) | -5.45 | 85.22 (82.90, 87.54) | -4.56 | 83.33 (80.89, 85.77) | -6.45 | 85.56 (83.26, 87.86) | -4.22 | 83.67 (81.25, 86.09) | -6.11 | 87.44 (85.27, 89.61) | -2.34 | 86.33 (84.08, 88.58) | -3.45 | 85.22 (82.90, 87.54) | -4.56 |
| MultiWikiQA EN (F1) | **81.52 (80.64, 82.40)** | 74.09 (73.10, 75.08) | -7.43 | 71.49 (70.45, 72.53) | -10.03 | 73.70 (72.68, 74.72) | -7.82 | 73.09 (72.06, 74.12) | -8.43 | 73.35 (72.33, 74.37) | -8.17 | 74.39 (73.38, 75.40) | -7.13 | 73.90 (72.89, 74.91) | -7.62 | 73.75 (72.73, 74.77) | -7.77 |
| ARC Easy EN (acc_norm) | **83.51 (80.46, 86.56)** | 78.77 (75.41, 82.13) | -4.74 | 77.54 (74.11, 80.97) | -5.97 | 78.07 (74.67, 81.47) | -5.44 | 79.47 (76.15, 82.79) | -4.04 | 77.72 (74.30, 81.14) | -5.79 | 80.53 (77.28, 83.78) | -2.98 | 77.72 (74.30, 81.14) | -5.79 | 77.54 (74.11, 80.97) | -5.97 |
| ARC Challenge EN (acc_norm) | **65.22 (59.81, 70.63)** | 59.87 (54.30, 65.44) | -5.35 | 58.86 (53.27, 64.45) | -6.36 | 60.54 (54.99, 66.09) | -4.68 | 56.19 (50.56, 61.82) | -9.03 | 62.54 (57.04, 68.04) | -2.68 | 61.20 (55.67, 66.73) | -4.02 | 61.20 (55.67, 66.73) | -4.02 | 63.55 (58.09, 69.01) | -1.67 |
| PIQA EN (acc_norm) | **83.00 (75.60, 90.40)** | 79.00 (70.98, 87.02) | -4.00 | 80.00 (72.12, 87.88) | -3.00 | 82.00 (74.43, 89.57) | -1.00 | 80.00 (72.12, 87.88) | -3.00 | 82.00 (74.43, 89.57) | -1.00 | 81.00 (73.27, 88.73) | -2.00 | 79.00 (70.98, 87.02) | -4.00 | 80.00 (72.12, 87.88) | -3.00 |
| HellaSwag EN (acc_norm) | **81.29 (80.53, 82.05)** | 80.59 (79.82, 81.36) | -0.70 | 80.11 (79.33, 80.89) | -1.18 | 80.66 (79.89, 81.43) | -0.63 | 79.67 (78.88, 80.46) | -1.62 | 80.84 (80.07, 81.61) | -0.45 | 80.58 (79.81, 81.35) | -0.71 | 80.61 (79.84, 81.38) | -0.68 | 80.60 (79.83, 81.37) | -0.69 |
| WNLI EN (acc) | 30.99 (20.16, 41.82) | 35.21 (24.02, 46.40) | +4.22 | 32.39 (21.43, 43.35) | +1.40 | 32.39 (21.43, 43.35) | +1.40 | 32.39 (21.43, 43.35) | +1.40 | **39.44 (27.99, 50.89)** | +8.45 | 30.99 (20.16, 41.82) | +0.00 | 33.80 (22.72, 44.88) | +2.81 | 33.80 (22.72, 44.88) | +2.81 |
| COPA EN (acc) | 88.00 (81.60, 94.40) | **89.00 (82.84, 95.16)** | +1.00 | 86.00 (79.16, 92.84) | -2.00 | 88.00 (81.60, 94.40) | +0.00 | 88.00 (81.60, 94.40) | +0.00 | 87.00 (80.38, 93.62) | -1.00 | 85.00 (77.97, 92.03) | -3.00 | 87.00 (80.38, 93.62) | -1.00 | 88.00 (81.60, 94.40) | +0.00 |
| XStoryCloze EN (acc) | 80.61 (78.62, 82.60) | 80.54 (78.54, 82.54) | -0.07 | 81.34 (79.37, 83.31) | +0.73 | 81.01 (79.03, 82.99) | +0.40 | 81.67 (79.72, 83.62) | +1.06 | 81.47 (79.51, 83.43) | +0.86 | **81.93 (79.99, 83.87)** | +1.32 | 81.80 (79.85, 83.75) | +1.19 | 81.87 (79.93, 83.81) | +1.26 |
| MGSM EN (exact_match) | **30.80 (25.07, 36.53)** | 20.80 (15.76, 25.84) | -10.00 | 18.40 (13.59, 23.21) | -12.40 | 14.40 (10.04, 18.76) | -16.40 | 14.00 (9.69, 18.31) | -16.80 | 30.00 (24.31, 35.69) | -0.80 | 21.60 (16.49, 26.71) | -9.20 | 26.40 (20.92, 31.88) | -4.40 | 20.80 (15.76, 25.84) | -10.00 |
| GPQA Main EN (acc) | 32.14 (27.81, 36.47) | 34.60 (30.19, 39.01) | +2.46 | 31.03 (26.74, 35.32) | -1.11 | **35.04 (30.62, 39.46)** | +2.90 | 32.37 (28.03, 36.71) | +0.23 | 32.14 (27.81, 36.47) | +0.00 | 32.37 (28.03, 36.71) | +0.23 | 34.60 (30.19, 39.01) | +2.46 | 33.71 (29.33, 38.09) | +1.57 |
| TruthfulQA-MC1 EN (acc) | **28.40 (25.31, 31.49)** | 24.24 (21.30, 27.18) | -4.16 | 25.46 (22.47, 28.45) | -2.94 | 23.50 (20.59, 26.41) | -4.90 | 24.72 (21.76, 27.68) | -3.68 | 26.07 (23.06, 29.08) | -2.33 | 24.97 (22.00, 27.94) | -3.43 | 24.24 (21.30, 27.18) | -4.16 | 24.24 (21.30, 27.18) | -4.16 |
| Average | **65.35 (63.93, 66.77)** | 62.23 (60.78, 63.68) | -3.12 | 60.99 (59.54, 62.44) | -4.36 | 61.47 (60.05, 62.89) | -3.88 | 61.07 (59.64, 62.50) | -4.28 | 63.15 (61.68, 64.62) | -2.20 | 62.35 (60.91, 63.79) | -3.00 | 62.74 (61.28, 64.20) | -2.61 | 62.26 (60.81, 63.71) | -3.09 |

*Note: In bold the highest value per row. In parentheses the 95% confidence intervals (CI), which are approximate normal intervals computed as the score or average ± 1.96 times its standard error. Gain columns show signed score-point differences from the corresponding base model.*

The language-level averages (see table below) show the same broad pattern: the Guarani average increases
by `3.13`–`6.15` points over the base score, while `English` remains within `2.01`
points of its base average and Spanish within `1.94` points of its base average in the worst cases. 
**These averages further indicate stronger Guarani performance alongside substantial retention of English and Spanish**.

| Variant | Guarani Average | Guarani Gain | English Average | English Gain | Spanish Average | Spanish Gain |
| --- | --- | --- | --- | --- | --- | --- |
| base | 31.66 | -- | **59.73** | -- | **59.75** | -- |
| C1 | 36.19 | +4.53 | 58.88 | -0.85 | 58.29 | -1.46 |
| C2 | 35.09 | +3.43 | 57.72 | -2.01 | 58.34 | -1.40 |
| C3 | 35.58 | +3.93 | 58.25 | -1.47 | 58.33 | -1.42 |
| C4 | 35.55 | +3.89 | 57.81 | -1.92 | 58.01 | -1.73 |
| C5 | 36.07 | +4.41 | 59.71 | **-0.02** | 57.94 | -1.80 |
| C6 | 34.78 | +3.13 | 58.88 | -0.85 | 57.80 | -1.94 |
| C7 | 37.42 | +5.76 | 59.34 | -0.39 | 58.33 | -1.42 |
| C8 | **37.81** | **+6.15** | 58.83 | -0.90 | 58.82 | **-0.93** |

*Note: In bold the highest value per column. Gain columns show signed score-point differences from the corresponding base model.*

**Data configuration finding**

`C7` shows to be the most promising data configuration to carry forward to supervised
fine-tuning. It has the best perplexity results, leads translation from Guarani, scores
highest on Guarani `Belebele`, and comes closest to the base on Guarani `Global MMLU
Lite` and `MGSM`. It also retains multilingual performance well: its English average
ranks second among CPT variants, and its Spanish average is among the strongest. 

> [!IMPORTANT]
> While no single configuration leads every evaluation, the dataset configuration 
> C7 shows to offer the strongest balance across the Guarani capabilities and multilingual retention.

#### Finding the CPT method

With `C7` selected as the most promising data configuration, the next step is to 
compare full CPT with LoRA. The comparison uses models trained on `C7`, with LoRA 
ranks of `64`, `128`, `256`, and `512`.

