| model_key | variant | training_method | corpus | eval_corpus | lora_rank | profiles | bits_per_byte | byte_perplexity | global_mmlu_lite_acc | global_mmlu_lite_acc_norm | word_perplexity | bits_per_byte_improvement_vs_base_pct | byte_perplexity_improvement_vs_base_pct | global_mmlu_lite_acc_improvement_vs_base_pct | global_mmlu_lite_acc_norm_improvement_vs_base_pct | word_perplexity_improvement_vs_base_pct |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| gemma4_12b | base | base |  | c1_kuatia |  | experiments | 1.82623 | 3.5461 | 0.45 | 0.45 | 21530.2 |  |  |  |  |  |
| gemma4_12b | base | base |  | c2_kuatia_es20 |  | experiments | 1.48174 | 2.79285 | 0.45 | 0.45 | 1810.13 |  |  |  |  |  |
| gemma4_12b | base | base |  | c3_kuatia_en20 |  | experiments | 1.48056 | 2.79057 | 0.45 | 0.45 | 1642.32 |  |  |  |  |  |
| gemma4_12b | base | base |  | c4_kuatia_es10_en10 |  | experiments | 1.50731 | 2.8428 | 0.45 | 0.45 | 2172.04 |  |  |  |  |  |
| gemma4_12b | full_C1_kuatia | full | C1_kuatia | c1_kuatia |  | experiments | 1.28766 | 2.44132 | 0.455 | 0.455 | 1135.51 | 29.4909 | 31.1548 | 1.11111 | 1.11111 | 94.726 |
| gemma4_12b | full_C2_kuatia_es20 | full | C2_kuatia_es20 | c2_kuatia_es20 |  | experiments | 1.07654 | 2.10897 | 0.4275 | 0.4275 | 232.727 | 27.3463 | 24.4869 | -5 | -5 | 87.1431 |
| gemma4_12b | full_C3_kuatia_en20 | full | C3_kuatia_en20 | c3_kuatia_en20 |  | experiments | 1.13399 | 2.19465 | 0.4475 | 0.4475 | 290.252 | 23.4082 | 21.355 | -0.555556 | -0.555556 | 82.3267 |
| gemma4_12b | full_C4_kuatia_es10_en10 | full | C4_kuatia_es10_en10 | c4_kuatia_es10_en10 |  | experiments | 1.10172 | 2.14611 | 0.4175 | 0.4175 | 274.777 | 26.9081 | 24.5072 | -7.22222 | -7.22222 | 87.3494 |
| gemma4_12b | lora_r128_C1_kuatia | lora | C1_kuatia | c1_kuatia | 128 | experiments | 0.781 | 1.71832 | 0.5175 | 0.5175 | 71.2946 | 57.2343 | 51.5433 | 15 | 15 | 99.6689 |
| gemma4_12b | lora_r128_C2_kuatia_es20 | lora | C2_kuatia_es20 | c2_kuatia_es20 | 128 | experiments | 0.745689 | 1.67677 | 0.4725 | 0.4725 | 43.5967 | 49.6746 | 39.9618 | 5 | 5 | 97.5915 |
| gemma4_12b | lora_r128_C3_kuatia_en20 | lora | C3_kuatia_en20 | c3_kuatia_en20 | 128 | experiments | 0.78838 | 1.72713 | 0.4475 | 0.4475 | 51.5454 | 46.7513 | 38.1083 | -0.555556 | -0.555556 | 96.8614 |
| gemma4_12b | lora_r128_C4_kuatia_es10_en10 | lora | C4_kuatia_es10_en10 | c4_kuatia_es10_en10 | 128 | experiments | 0.776653 | 1.71315 | 0.4925 | 0.4925 | 52.4019 | 48.4742 | 39.7371 | 9.44444 | 9.44444 | 97.5874 |
| gemma4_12b | lora_r256_C1_kuatia | lora | C1_kuatia | c1_kuatia | 256 | experiments | 0.735918 | 1.66546 | 0.4425 | 0.4425 | 55.7305 | 59.7029 | 53.0341 | -1.66667 | -1.66667 | 99.7412 |
| gemma4_12b | lora_r256_C2_kuatia_es20 | lora | C2_kuatia_es20 | c2_kuatia_es20 | 256 | experiments | 0.741791 | 1.67225 | 0.4425 | 0.4425 | 42.7448 | 49.9377 | 40.1238 | -1.66667 | -1.66667 | 97.6386 |
| gemma4_12b | lora_r256_C3_kuatia_en20 | lora | C3_kuatia_en20 | c3_kuatia_en20 | 256 | experiments | 0.75087 | 1.68281 | 0.4425 | 0.4425 | 42.7293 | 49.2848 | 39.6967 | -1.66667 | -1.66667 | 97.3982 |
| gemma4_12b | lora_r256_C4_kuatia_es10_en10 | lora | C4_kuatia_es10_en10 | c4_kuatia_es10_en10 | 256 | experiments | 2.96514 | 7.80901 | 0.255 | 0.255 | 3.66604e+06 | -96.7173 | -174.695 | -43.3333 | -43.3333 | -168683 |
| gemma4_12b | lora_r512_C1_kuatia | lora | C1_kuatia | c1_kuatia | 512 | experiments | 0.72272 | 1.65029 | 0.4075 | 0.4075 | 51.8533 | 60.4256 | 53.4618 | -9.44444 | -9.44444 | 99.7592 |
| gemma4_12b | lora_r512_C2_kuatia_es20 | lora | C2_kuatia_es20 | c2_kuatia_es20 | 512 | experiments | 3.3238 | 10.0129 | 0.235 | 0.235 | 2.03056e+07 | -124.318 | -258.521 | -47.7778 | -47.7778 | -1.12168e+06 |
| gemma4_12b | lora_r512_C3_kuatia_en20 | lora | C3_kuatia_en20 | c3_kuatia_en20 | 512 | experiments | 3.51067 | 11.3977 | 0.235 | 0.235 | 4.21129e+07 | -137.118 | -308.436 | -47.7778 | -47.7778 | -2.56414e+06 |
| gemma4_12b | lora_r512_C4_kuatia_es10_en10 | lora | C4_kuatia_es10_en10 | c4_kuatia_es10_en10 | 512 | experiments | 0.760486 | 1.69406 | 0.4275 | 0.4275 | 48.2566 | 49.5468 | 40.4086 | -5 | -5 | 97.7783 |
| gemma4_12b | lora_r64_C1_kuatia | lora | C1_kuatia | c1_kuatia | 64 | experiments | 0.836803 | 1.78609 | 0.5225 | 0.5225 | 96.7071 | 54.1787 | 49.6323 | 16.1111 | 16.1111 | 99.5508 |
| gemma4_12b | lora_r64_C2_kuatia_es20 | lora | C2_kuatia_es20 | c2_kuatia_es20 | 64 | experiments | 0.797166 | 1.73768 | 0.4975 | 0.4975 | 56.5758 | 46.2005 | 37.7809 | 10.5556 | 10.5556 | 96.8745 |
| gemma4_12b | lora_r64_C3_kuatia_en20 | lora | C3_kuatia_en20 | c3_kuatia_en20 | 64 | experiments | 0.82327 | 1.76941 | 0.4775 | 0.4775 | 61.3711 | 44.3947 | 36.5932 | 6.11111 | 6.11111 | 96.2631 |
| gemma4_12b | lora_r64_C4_kuatia_es10_en10 | lora | C4_kuatia_es10_en10 | c4_kuatia_es10_en10 | 64 | experiments | 0.792038 | 1.73152 | 0.485 | 0.485 | 56.6768 | 47.4536 | 39.091 | 7.77778 | 7.77778 | 97.3906 |
