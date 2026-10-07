| model_key | variant | training_method | corpus | eval_corpus | lora_rank | profiles | bits_per_byte | byte_perplexity | global_mmlu_lite_acc | global_mmlu_lite_acc_norm | word_perplexity | bits_per_byte_improvement_vs_base_pct | byte_perplexity_improvement_vs_base_pct | global_mmlu_lite_acc_improvement_vs_base_pct | global_mmlu_lite_acc_norm_improvement_vs_base_pct | word_perplexity_improvement_vs_base_pct |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| gemma4_26b_a4b | base | base |  | c1_kuatia |  | experiments | 1.50165 | 2.83166 | 0.485 | 0.485 | 3655.29 |  |  |  |  |  |
| gemma4_26b_a4b | base | base |  | c2_kuatia_es20 |  | experiments | 1.24939 | 2.3774 | 0.485 | 0.485 | 558.302 |  |  |  |  |  |
| gemma4_26b_a4b | base | base |  | c3_kuatia_en20 |  | experiments | 1.25313 | 2.38357 | 0.485 | 0.485 | 526.643 |  |  |  |  |  |
| gemma4_26b_a4b | base | base |  | c4_kuatia_es10_en10 |  | experiments | 1.27217 | 2.41525 | 0.485 | 0.485 | 655.125 |  |  |  |  |  |
| gemma4_26b_a4b | lora_r128_C1_kuatia | lora | C1_kuatia | c1_kuatia | 128 | experiments | 0.945531 | 1.9259 | 0.5325 | 0.5325 | 175.16 | 37.0338 | 31.987 | 9.79381 | 9.79381 | 95.208 |
| gemma4_26b_a4b | lora_r128_C2_kuatia_es20 | lora | C2_kuatia_es20 | c2_kuatia_es20 | 128 | experiments | 0.850678 | 1.80335 | 0.55 | 0.55 | 74.1789 | 31.9123 | 24.1462 | 13.4021 | 13.4021 | 86.7135 |
| gemma4_26b_a4b | lora_r128_C3_kuatia_en20 | lora | C3_kuatia_en20 | c3_kuatia_en20 | 128 | experiments | 0.856457 | 1.81059 | 0.565 | 0.565 | 72.4498 | 31.6544 | 24.039 | 16.4948 | 16.4948 | 86.2431 |
| gemma4_26b_a4b | lora_r128_C4_kuatia_es10_en10 | lora | C4_kuatia_es10_en10 | c4_kuatia_es10_en10 | 128 | experiments | 0.865021 | 1.82137 | 0.49 | 0.49 | 82.2196 | 32.0044 | 24.5889 | 1.03093 | 1.03093 | 87.4498 |
| gemma4_26b_a4b | lora_r256_C1_kuatia | lora | C1_kuatia | c1_kuatia | 256 | experiments | 0.863227 | 1.8191 | 0.5275 | 0.5275 | 111.726 | 42.5147 | 35.7585 | 8.76289 | 8.76289 | 96.9434 |
| gemma4_26b_a4b | lora_r256_C2_kuatia_es20 | lora | C2_kuatia_es20 | c2_kuatia_es20 | 256 | experiments | 0.819826 | 1.76519 | 0.505 | 0.505 | 63.4527 | 34.3817 | 25.7512 | 4.12371 | 4.12371 | 88.6347 |
| gemma4_26b_a4b | lora_r256_C3_kuatia_en20 | lora | C3_kuatia_en20 | c3_kuatia_en20 | 256 | experiments | 0.828801 | 1.77621 | 0.5375 | 0.5375 | 63.0921 | 33.8613 | 25.4813 | 10.8247 | 10.8247 | 88.0199 |
| gemma4_26b_a4b | lora_r256_C4_kuatia_es10_en10 | lora | C4_kuatia_es10_en10 | c4_kuatia_es10_en10 | 256 | experiments | 0.825918 | 1.77266 | 0.4775 | 0.4775 | 67.3613 | 35.0781 | 26.6054 | -1.54639 | -1.54639 | 89.7178 |
| gemma4_26b_a4b | lora_r512_C1_kuatia | lora | C1_kuatia | c1_kuatia | 512 | experiments | 0.794355 | 1.7343 | 0.5 | 0.5 | 76.6909 | 47.1012 | 38.7532 | 3.09278 | 3.09278 | 97.9019 |
| gemma4_26b_a4b | lora_r512_C2_kuatia_es20 | lora | C2_kuatia_es20 | c2_kuatia_es20 | 512 | experiments | 0.765875 | 1.7004 | 0.4875 | 0.4875 | 48.2873 | 38.6999 | 28.4765 | 0.515464 | 0.515464 | 91.351 |
| gemma4_26b_a4b | lora_r512_C3_kuatia_en20 | lora | C3_kuatia_en20 | c3_kuatia_en20 | 512 | experiments | 0.781425 | 1.71883 | 0.46 | 0.46 | 49.7836 | 37.6419 | 27.8886 | -5.15464 | -5.15464 | 90.547 |
| gemma4_26b_a4b | lora_r512_C4_kuatia_es10_en10 | lora | C4_kuatia_es10_en10 | c4_kuatia_es10_en10 | 512 | experiments | 0.806277 | 1.74869 | 0.4575 | 0.4575 | 60.9436 | 36.6221 | 27.5979 | -5.6701 | -5.6701 | 90.6974 |
| gemma4_26b_a4b | lora_r64_C1_kuatia | lora | C1_kuatia | c1_kuatia | 64 | experiments | 0.984955 | 1.97925 | 0.5225 | 0.5225 | 217.257 | 34.4085 | 30.1029 | 7.73196 | 7.73196 | 94.0564 |
| gemma4_26b_a4b | lora_r64_C2_kuatia_es20 | lora | C2_kuatia_es20 | c2_kuatia_es20 | 64 | experiments | 0.887196 | 1.84958 | 0.5425 | 0.5425 | 89.2417 | 28.9894 | 22.2017 | 11.8557 | 11.8557 | 84.0155 |
| gemma4_26b_a4b | lora_r64_C3_kuatia_en20 | lora | C3_kuatia_en20 | c3_kuatia_en20 | 64 | experiments | 0.907125 | 1.8753 | 0.5325 | 0.5325 | 93.3421 | 27.611 | 21.3238 | 9.79381 | 9.79381 | 82.276 |
| gemma4_26b_a4b | lora_r64_C4_kuatia_es10_en10 | lora | C4_kuatia_es10_en10 | c4_kuatia_es10_en10 | 64 | experiments | 0.911201 | 1.88061 | 0.5025 | 0.5025 | 104.042 | 28.3745 | 22.136 | 3.60825 | 3.60825 | 84.1188 |
