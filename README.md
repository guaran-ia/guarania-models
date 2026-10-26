# GuaranIA-LLM

This repository contains the technical artifacts (e.g., configuration matrices, data, evaluation tasks) 
used to develop the LLMs for the project [GuaranIA](https://www.guarania.org). The 
building process follows the [BYOL](https://arxiv.org/abs/2601.10804) methodology, 
which is implemented through the in-house framework [Guaratune](https://github.com/guaran-ia/guaratune).

The main idea is to adapt a multilingual base model to Guarani while aiming to retain its existing capabilities.

## BYOL methodology in a nutshell

The BYOL methodology consists of three steps: `continual pretraining (CPT)`, where the
base model continues training on a curated langage corpus, `supervised fine-tuning (SFT)`, 
where the CPT model is futher trained on instruction-and-response examples, and model 
merging, where the language-adapted model is combined with the original model in weight space.
See the [BYOL paper](https://arxiv.org/abs/2601.10804) for more information about 
the framework.

## GuaranIA approach

The guarani corpus [Kuatia](https://huggingface.co/datasets/guaran-ia/kuatia)
augmented with [Spanish](https://huggingface.co/datasets/Helsinki-NLP/fineweb-edu-translated) 
and [English](https://huggingface.co/datasets/HuggingFaceFW/fineweb-edu) FineWeb-Edu 
samples are used to build the GuaranIA LLMs. The three sources were combined through
eigth different data configurations.

* C1: Kuatia (43,677,319 tokens)
* C2: Kuatia without synthetic (27,994,685 tokens)
* C3: Kuatia + 20% Spanish FineWeb-Edu (52,415,631 tokens)
* C4: Kuatia without synthetic + 20% Spanish FineWeb-Edu (36,732,997 tokens)
* C5: Kuatia + 20% FineWeb-Edu (52,412,827 tokens)
* C6: Kuatia without synthetic + 20% FineWeb-Edu (36,730,193 tokens)
* C7: Kuatia + 10% Spanish FineWeb-Edu + 10% FineWeb-Edu (52,415,521 tokens)
* C8: Kuatia without synthetic + 10% Spanish FineWeb-Edu + 10% FineWeb-Edu (36,732,887 tokens)

> [!Note]
> The corpus definitions and source revisions are recorded in [`cpt/configs/data/gemma4_cpt.yaml`](cpt/configs/data/gemma4_cpt.yaml).

Full CPT on [Gemma-4 E4B-PT](https://huggingface.co/google/gemma-4-E4B) are conducted 
on the eigth data configurations to identify the most promising one.

>[!Note]
> Train configuration and hyperparameters are available in [`cpt/configs/train/gemma4-4_cpt_matrix.yaml`](cpt/configs/train/gemma4-4_cpt_matrix.yaml).

The eight trained variants (C1-C8) are evaluated against the base model on Guarani, Spanish, 
and English benchmarks, including language understanding, reading comprenhension, 
question answering, translation, and perplexity tasks. The following table presents 
the benchmarks used to evaluate the trained variants together with their languages,
the capacity they assess and the metric employed.

| Benchmark | Language | Capacity | Task | Metric |
| --- | --- | --- | --- | --- |
| Belele | [GN](https://huggingface.co/datasets/facebook/belebele/viewer/grn_Latn), [EN](https://huggingface.co/datasets/facebook/belebele/viewer/eng_Latn), [ES](https://huggingface.co/datasets/facebook/belebele/viewer/spa_Latn) | Reading comprenhension | Multiple-choice QA | Accuracy |
| MultiWiki-QA | [GN](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa/viewer/gn), [EN](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa/viewer/en), [ES](https://huggingface.co/datasets/alexandrainst/multi-wiki-qa/viewer/es) | Reading comprenhension | Generation | F1, Exact match |
| Flores+ | [GN](https://huggingface.co/datasets/openlanguagedata/flores_plus/viewer/gug_Latn/dev), [EN](https://huggingface.co/datasets/openlanguagedata/flores_plus/viewer/eng_Latn/dev), [ES](https://huggingface.co/datasets/openlanguagedata/flores_plus/viewer/spa_Latn/dev) | Translation | Generation | BLEU, chrf++ |
| Global MMLU Lite | [GN](data/evaluation/global-mmlu-lite), [EN](https://huggingface.co/datasets/CohereLabs/Global-MMLU-Lite/viewer/en/test), [ES](https://huggingface.co/datasets/CohereLabs/Global-MMLU-Lite/viewer/es/test) | General knowledge | Multiple-choice QA | Accuracy |
| MGSM | [GN](data/evaluation/mgsm), [EN](https://huggingface.co/datasets/juletxara/mgsm/viewer/en/test), [ES](https://huggingface.co/datasets/juletxara/mgsm/viewer/es/test) | Specialized reasoning (mathematics) | Generation| Exact match |
| ARC Easy | [EN](https://huggingface.co/datasets/allenai/ai2_arc/viewer/ARC-Easy/validation), [ES](https://huggingface.co/datasets/BSC-LT/arc_es/viewer/ARC_Easy_es) | Specialized reasoning (science) | Multiple-choice QA | Normalized accuracy |
| ARC Challenge | [EN](https://huggingface.co/datasets/allenai/ai2_arc/viewer/ARC-Challenge/validation), [ES](https://huggingface.co/datasets/BSC-LT/arc_es/viewer/ARC_Challenge_es) | Specialized reasoning (science) | Multiple-choice QA | Normalized accuracy |
| GPQA (main) | [EN](https://huggingface.co/datasets/Idavidrein/gpqa/viewer/gpqa_main), [ES](https://huggingface.co/datasets/ellamind/gpqa-multilingual/viewer/spa) | Specialized reasoning (biology, physics, chemistry) | Multiple-choice QA | Accuracy |
| WNLI | [GN](data/evaluation/wnli), [EN](https://huggingface.co/datasets/nyu-mll/glue/viewer/wnli/test), [ES](https://huggingface.co/datasets/PlanTL-GOB-ES/wnli-es/blob/main/wnli-test-shuffled-es.csv) | Common sense & inference | Multiple-choice QA | Accuracy |
| XStoryCloze | [EN](https://huggingface.co/datasets/juletxara/xstory_cloze/viewer/en/eval), [ES](https://huggingface.co/datasets/juletxara/xstory_cloze/viewer/es/eval) | Common sense & inference | Multiple-choice QA | Accuracy |
| HellaSwag | [EN](https://huggingface.co/datasets/Rowan/hellaswag/viewer/default/validation), [ES](https://huggingface.co/datasets/alvarobartt/hellaswag-okapi-eval-es) | Common sense & inference | Multiple-choice QA | Normalized accuracy |
| PIQA | [EN](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel/viewer/eng_latn), [ES](https://huggingface.co/datasets/mrlbenchmarks/global-piqa-nonparallel/viewer/spa_latn_spai) | Common sense & inference | Multiple-choice QA | Normalized accuracy | 
| COPA | [EN](https://huggingface.co/datasets/aps/super_glue/viewer/copa/validation), [ES](https://huggingface.co/datasets/BSC-LT/COPA-es) | Causal reasoning | Multiple-choice QA | Accuracy |
| TruthfulQA-MC1 | [EN](https://huggingface.co/datasets/HiTZ/truthfulqa-multi/viewer/en/validation), [ES](https://huggingface.co/datasets/HiTZ/truthfulqa-multi/viewer/es/validation) | Truthfulness and factuality | Multiple-choice QA | Accuracy |

>[!Note]
> A Guarani version of `Global MMLU Lite`, `MGSM`, and `WLNI` were 
> created by language experts and are available at the [Guaratune repo](https://github.com/guaran-ia/guaratune/tree/main/data/evaluation).

Complementing the evaluations conducted with the mentioned benchkmarks, the framework
assesses model performance through perplexity on [COREGUAPA](https://corpus.spl.gov.py), a high-quality 
proprietary corpus curated by the [Paraguayan Secretariat of Linguistic Policy](https://spl.gov.py).

>[!Note]
> The task and suite definitions are in [`cpt/configs/evaluation/gemma4-4_eval_matrix.yaml`](cpt/configs/evaluation/gemma4-4_eval_matrix.yaml) and [`cpt/evaluation/lm_eval_tasks/`](cpt/evaluation/lm_eval_tasks/).

## Results

### Perplexity

Across the **`COREGUAPA` perplexity** evaluation, every `CPT` variant scores below the 
`Gemma-4 E4B` base model on all three reported metrics (i.e., `word perplexity`, 
`byte perplexity`, and `bits per byte`). **`C7`** (the data configuration 
that includes `Kuatia` both real and synthetic plus English and Spanish FineWeb-Edu) 
**has the lowest values**: `word perplexity` `463.10`, `byte perplexity` `2.10`, and 
`bits per byte` `1.07`, compared with `3058.27`, `2.64`, and `1.40` for the base model. 

The other `CPT` variants are close on `byte perplexity` (`2.11`–`2.15`) and 
`bits per byte` (`1.07`–`1.10`), so `C7`'s lead on those measures is small. **Lower 
values indicate better prediction of the evaluation text**. The report covers 66 
`COREGUAPA` examples, so these results describe performance on that set; they do not 
alone establish broad language ability. Check the complete [perplexity results](cpt/results/gemma4_4b/evaluation_perplexity.md).

### Guarani performance

The full CPT variants show a mixed pattern across the Guarani benchmarks. **All eight 
improve on the base model in each of the four `FLORES+` translation directions**. `C3` 
has the highest `chrF++` for `English→Guarani` (`30.82` vs. `8.48` for the base), and 
`C1` is highest for `Spanish→Guarani` (`29.81` vs. `9.30`). `C7` produces the best 
scores for both `Guarani→English` (`44.47` vs. `37.94`) and `Guarani→Spanish` 
(`37.11` vs. `33.40`). Overall, **`C7` has the strongest translation profile**, leading
both directions from Guarani and performing close to the top variants on translations
into Guarani.

On the other tasks, gains are limited: **`C7` has the highest `Belebele` accuracy** 
(`55.56` vs. `52.22` for the base), and `C8` has the highest `WNLI` accuracy 
(`59.18` vs. `44.90`). Every CPT variant scores below the base on Guarani 
`Global MMLU Lite` (`46.00`) and `MGSM` exact match (`9.86`), while all variants 
also trail the base on `MultiWikiQA` F1 (`42.83`). However, **C7 comes close to the 
base on the first two tasks**, with differences of only `0.50` points on 
`Global MMLU Lite` and `0.71` points on `MGSM`. These results migth suggest that 
the base model's existing Guarani capacity for these tasks limits what continued 
training on the available corpus can improve.

Considering its leading results on both translation directions from Guarani, strong
`Belebele` score, and near-base results on `Global MMLU Lite` and `MGSM`, **`C7` highlights 
as the most promising variant for the Guarani capabilities emphasized here**, although 
`C8` showed the highest displayed average across all Guarani tasks. So `C7` recommendation 
reflects the balance of capabilities described above rather than the aggregate average alone.
See the [Guarani benchmark results](cpt/results/gemma4_4b/evaluation_score_by_benchmark.md) 
for all variant scores and confidence intervals, and the [evaluation information sheet](cpt/results/gemma4_4b/evaluation_information_sheet.md) for benchmark setup.

### Multilingual performance

Across Spanish and English benchmarks, the CPT variants sometimes score above the base
and sometimes below it. Although the average scores are generally lower, the differences
are modest: roughly 2–4 points from the base averages of `65.65` in `Spanish` and `65.35` in
`English`. This overall proximity suggests that **multilingual performance is retained through CPT, despite task-level gains and losses**. See the [benchmark score report](cpt/results/gemma4_4b/evaluation_score_by_benchmark.md) for the full results and confidence intervals.

The language-level averages show the same broad pattern: the Guarani average increases
by `3.13`–`6.15` points over the base score, while `English` remains within `2.01`
points of its base average and Spanish within `1.95` points of its base average. 
**These averages further indicate stronger Guarani performance alongside substantial retention of English and Spanish**. See the [average score by language report](cpt/results/gemma4_4b/evaluation_average_score_by_language.md) for the full
comparison.

## Conclusion

`C7` is the most promising data configuration to carry forward to supervised
fine-tuning. It has the best perplexity results, leads translation from Guarani, scores
highest on Guarani `Belebele`, and comes closest to the base on Guarani `Global MMLU
Lite` and `MGSM`. It also retains multilingual performance well: its English average
ranks second among CPT variants, and its Spanish average is among the strongest. 

>[!Note] 
> While no single configuration leads every evaluation, the dataset configuration 
> C7 shows to offer the strongest balance across the Guarani capabilities and multilingual retention.


