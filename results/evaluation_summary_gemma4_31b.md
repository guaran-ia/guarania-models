| model_key | variant | training_method | corpus | eval_corpus | lora_rank | profiles | bits_per_byte | byte_perplexity | global_mmlu_lite_acc | global_mmlu_lite_acc_norm | word_perplexity | bits_per_byte_improvement_vs_base_pct | byte_perplexity_improvement_vs_base_pct | global_mmlu_lite_acc_improvement_vs_base_pct | global_mmlu_lite_acc_norm_improvement_vs_base_pct | word_perplexity_improvement_vs_base_pct |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| gemma4_31b | base | base |  | c1_kuatia |  | experiments | 1.4222 | 2.67993 | 0.545 | 0.545 | 2368.11 |  |  |  |  |  |
| gemma4_31b | base | base |  | c2_kuatia_es20 |  | experiments | 1.18511 | 2.2738 | 0.545 | 0.545 | 403.224 |  |  |  |  |  |
| gemma4_31b | base | base |  | c3_kuatia_en20 |  | experiments | 1.19334 | 2.28681 | 0.545 | 0.545 | 390.541 |  |  |  |  |  |
| gemma4_31b | base | base |  | c4_kuatia_es10_en10 |  | experiments | 1.20777 | 2.30981 | 0.545 | 0.545 | 471.794 |  |  |  |  |  |
| gemma4_31b | lora_r128_C1_kuatia | lora | C1_kuatia | c1_kuatia | 128 | experiments | 0.784849 | 1.72291 | 0.5825 | 0.5825 | 72.8096 | 44.8143 | 35.7106 | 6.88073 | 6.88073 | 96.9254 |
| gemma4_31b | lora_r128_C2_kuatia_es20 | lora | C2_kuatia_es20 | c2_kuatia_es20 | 128 | experiments | 0.768236 | 1.70319 | 0.59 | 0.59 | 48.868 | 35.1758 | 25.0952 | 8.25688 | 8.25688 | 87.8807 |
| gemma4_31b | lora_r128_C3_kuatia_en20 | lora | C3_kuatia_en20 | c3_kuatia_en20 | 128 | experiments | 0.767375 | 1.70217 | 0.5375 | 0.5375 | 46.4056 | 35.695 | 25.5657 | -1.37615 | -1.37615 | 88.1176 |
| gemma4_31b | lora_r128_C4_kuatia_es10_en10 | lora | C4_kuatia_es10_en10 | c4_kuatia_es10_en10 | 128 | experiments | 0.775771 | 1.71211 | 0.56 | 0.56 | 52.1669 | 35.7684 | 25.8767 | 2.75229 | 2.75229 | 88.9429 |
