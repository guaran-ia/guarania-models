# GuaranIA LLMs

This repository contains technical artifacts used to develop and evaluate language models for [GuaranIA](https://www.guarania.org), a project focused on adapting multilingual models to Guarani. The development approach follows the [BYOL methodology](https://arxiv.org/abs/2601.10804) and uses the in-house [Guaratune framework](https://github.com/guaran-ia/guaratune).

## Repository contents

- `cpt/configs/` — corpus, training, and evaluation configuration matrices for Gemma 4 model sizes.
- `cpt/evaluation/lm_eval_tasks/` — benchmark task definitions used for model evaluation.
- `cpt/outputs/` — experiment outputs, including evaluation results and samples.
- `cpt/results/` — benchmark summaries and comparison tables for Gemma 3 and Gemma 4.

## Key files

- [CPT data sources and corpus variants](cpt/configs/data/gemma4_cpt.yaml)
- Training matrices: [Gemma 4 E2B](cpt/configs/train/gemma4-2_cpt_matrix.yaml), [E4B](cpt/configs/train/gemma4-4_cpt_matrix.yaml), and [12B](cpt/configs/train/gemma4-12_cpt_matrix.yaml)
- Evaluation matrices: [Gemma 4 E2B](cpt/configs/evaluation/gemma4-2_eval_matrix.yaml), [E4B](cpt/configs/evaluation/gemma4-4_eval_matrix.yaml), and [12B](cpt/configs/evaluation/gemma4-12_eval_matrix.yaml)
- [Evaluation task definitions](cpt/evaluation/lm_eval_tasks/)
- Results: [Gemma 4 4B benchmark scores](cpt/results/gemma4_4b/evaluation_score_by_benchmark.md), [perplexity](cpt/results/gemma4_4b/evaluation_perplexity.md), and [language averages](cpt/results/gemma4_4b/evaluation_average_score_by_language.md)

For the current experimental design, findings, and interpretation, see [REPORT.md](REPORT.md).
