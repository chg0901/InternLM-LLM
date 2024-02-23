## 作业

**基础作业**

- 使用 OpenCompass 评测 InternLM2-Chat-7B 模型在 C-Eval 数据集上的性能

**进阶作业**

- 使用 OpenCompass 评测 InternLM2-Chat-7B 模型使用 LMDeploy 0.2.0 部署后在 C-Eval 数据集上的性能

备注：**由于进阶作业较难，完成基础作业之后就可以先提交作业了，在后续的大作业项目中使用这些技术将作为重要的加分点！**



# 基础作业

```bash

cd ~/opencompass
conda activate opencompass

python run.py --datasets ceval_gen --hf-path /root/share/model_repos/internlm2-chat-7b/ --tokenizer-path /root/share/model_repos/internlm2-chat-7b/ --tokenizer-kwargs padding_side='left' truncation='left' trust_remote_code=True --model-kwargs trust_remote_code=True device_map='auto' --max-seq-len 2048 --max-out-len 16 --batch-size 4 --num-gpus 1 --debug

```
## 输出结果
```bash
02/23 12:54:03 - OpenCompass - INFO - write summary to /root/opencompass/outputs/default/20240223_123055/summary/summary_20240223_123055.txt
02/23 12:54:03 - OpenCompass - INFO - write csv to /root/opencompass/outputs/default/20240223_123055/summary/summary_20240223_123055.csv
```

## 查看文件
```bash
20240223_123055
tabulate format
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
dataset                                         version    metric         mode      opencompass.models.huggingface.HuggingFace_model_repos_internlm-chat-7b
----------------------------------------------  ---------  -------------  ------  -------------------------------------------------------------------------
ceval-computer_network                          db9ce2     accuracy       gen                                                                         31.58
ceval-operating_system                          1c2571     accuracy       gen                                                                         36.84
ceval-computer_architecture                     a74dad     accuracy       gen                                                                         28.57
ceval-college_programming                       4ca32a     accuracy       gen                                                                         32.43
ceval-college_physics                           963fa8     accuracy       gen                                                                         26.32
ceval-college_chemistry                         e78857     accuracy       gen                                                                         16.67
ceval-advanced_mathematics                      ce03e2     accuracy       gen                                                                         21.05
ceval-probability_and_statistics                65e812     accuracy       gen                                                                         38.89
ceval-discrete_mathematics                      e894ae     accuracy       gen                                                                         18.75
ceval-electrical_engineer                       ae42b9     accuracy       gen                                                                         35.14
ceval-metrology_engineer                        ee34ea     accuracy       gen                                                                         50
ceval-high_school_mathematics                   1dc5bf     accuracy       gen                                                                         22.22
ceval-high_school_physics                       adf25f     accuracy       gen                                                                         31.58
ceval-high_school_chemistry                     2ed27f     accuracy       gen                                                                         15.79
ceval-high_school_biology                       8e2b9a     accuracy       gen                                                                         36.84
ceval-middle_school_mathematics                 bee8d5     accuracy       gen                                                                         26.32
ceval-middle_school_biology                     86817c     accuracy       gen                                                                         61.9
ceval-middle_school_physics                     8accf6     accuracy       gen                                                                         63.16
ceval-middle_school_chemistry                   167a15     accuracy       gen                                                                         60
ceval-veterinary_medicine                       b4e08d     accuracy       gen                                                                         47.83
ceval-college_economics                         f3f4e6     accuracy       gen                                                                         41.82
ceval-business_administration                   c1614e     accuracy       gen                                                                         33.33
ceval-marxism                                   cf874c     accuracy       gen                                                                         68.42
ceval-mao_zedong_thought                        51c7a4     accuracy       gen                                                                         70.83
ceval-education_science                         591fee     accuracy       gen                                                                         58.62
ceval-teacher_qualification                     4e4ced     accuracy       gen                                                                         70.45
ceval-high_school_politics                      5c0de2     accuracy       gen                                                                         26.32
ceval-high_school_geography                     865461     accuracy       gen                                                                         47.37
ceval-middle_school_politics                    5be3e7     accuracy       gen                                                                         52.38
ceval-middle_school_geography                   8a63be     accuracy       gen                                                                         58.33
ceval-modern_chinese_history                    fc01af     accuracy       gen                                                                         73.91
ceval-ideological_and_moral_cultivation         a2aa4a     accuracy       gen                                                                         63.16
ceval-logic                                     f5b022     accuracy       gen                                                                         31.82
ceval-law                                       a110a1     accuracy       gen                                                                         25
ceval-chinese_language_and_literature           0f8b68     accuracy       gen                                                                         30.43
ceval-art_studies                               2a1300     accuracy       gen                                                                         60.61
ceval-professional_tour_guide                   4e673e     accuracy       gen                                                                         62.07
ceval-legal_professional                        ce8787     accuracy       gen                                                                         39.13
ceval-high_school_chinese                       315705     accuracy       gen                                                                         63.16
ceval-high_school_history                       7eb30a     accuracy       gen                                                                         70
ceval-middle_school_history                     48ab4a     accuracy       gen                                                                         59.09
ceval-civil_servant                             87d061     accuracy       gen                                                                         53.19
ceval-sports_science                            70f27b     accuracy       gen                                                                         52.63
ceval-plant_protection                          8941f9     accuracy       gen                                                                         59.09
ceval-basic_medicine                            c409d6     accuracy       gen                                                                         47.37
ceval-clinical_medicine                         49e82d     accuracy       gen                                                                         40.91
ceval-urban_and_rural_planner                   95b885     accuracy       gen                                                                         45.65
ceval-accountant                                002837     accuracy       gen                                                                         26.53
ceval-fire_engineer                             bc23f5     accuracy       gen                                                                         22.58
ceval-environmental_impact_assessment_engineer  c64e2d     accuracy       gen                                                                         64.52
ceval-tax_accountant                            3a5e3c     accuracy       gen                                                                         34.69
ceval-physician                                 6e277d     accuracy       gen                                                                         40.82
ceval-stem                                      -          naive_average  gen                                                                         35.09
ceval-social-science                            -          naive_average  gen                                                                         52.79
ceval-humanities                                -          naive_average  gen                                                                         52.58
ceval-other                                     -          naive_average  gen                                                                         44.36
ceval-hard                                      -          naive_average  gen                                                                         23.91
ceval                                           -          naive_average  gen                                                                         44.16
$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$

-------------------------------------------------------------------------------------------------------------------------------- THIS IS A DIVIDER --------------------------------------------------------------------------------------------------------------------------------

csv format
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
dataset,version,metric,mode,opencompass.models.huggingface.HuggingFace_model_repos_internlm-chat-7b
ceval-computer_network,db9ce2,accuracy,gen,31.58
ceval-operating_system,1c2571,accuracy,gen,36.84
ceval-computer_architecture,a74dad,accuracy,gen,28.57
ceval-college_programming,4ca32a,accuracy,gen,32.43
ceval-college_physics,963fa8,accuracy,gen,26.32
ceval-college_chemistry,e78857,accuracy,gen,16.67
ceval-advanced_mathematics,ce03e2,accuracy,gen,21.05
ceval-probability_and_statistics,65e812,accuracy,gen,38.89
ceval-discrete_mathematics,e894ae,accuracy,gen,18.75
ceval-electrical_engineer,ae42b9,accuracy,gen,35.14
ceval-metrology_engineer,ee34ea,accuracy,gen,50.00
ceval-high_school_mathematics,1dc5bf,accuracy,gen,22.22
ceval-high_school_physics,adf25f,accuracy,gen,31.58
ceval-high_school_chemistry,2ed27f,accuracy,gen,15.79
ceval-high_school_biology,8e2b9a,accuracy,gen,36.84
ceval-middle_school_mathematics,bee8d5,accuracy,gen,26.32
ceval-middle_school_biology,86817c,accuracy,gen,61.90
ceval-middle_school_physics,8accf6,accuracy,gen,63.16
ceval-middle_school_chemistry,167a15,accuracy,gen,60.00
ceval-veterinary_medicine,b4e08d,accuracy,gen,47.83
ceval-college_economics,f3f4e6,accuracy,gen,41.82
ceval-business_administration,c1614e,accuracy,gen,33.33
ceval-marxism,cf874c,accuracy,gen,68.42
ceval-mao_zedong_thought,51c7a4,accuracy,gen,70.83
ceval-education_science,591fee,accuracy,gen,58.62
ceval-teacher_qualification,4e4ced,accuracy,gen,70.45
ceval-high_school_politics,5c0de2,accuracy,gen,26.32
ceval-high_school_geography,865461,accuracy,gen,47.37
ceval-middle_school_politics,5be3e7,accuracy,gen,52.38
ceval-middle_school_geography,8a63be,accuracy,gen,58.33
ceval-modern_chinese_history,fc01af,accuracy,gen,73.91
ceval-ideological_and_moral_cultivation,a2aa4a,accuracy,gen,63.16
ceval-logic,f5b022,accuracy,gen,31.82
ceval-law,a110a1,accuracy,gen,25.00
ceval-chinese_language_and_literature,0f8b68,accuracy,gen,30.43
ceval-art_studies,2a1300,accuracy,gen,60.61
ceval-professional_tour_guide,4e673e,accuracy,gen,62.07
ceval-legal_professional,ce8787,accuracy,gen,39.13
ceval-high_school_chinese,315705,accuracy,gen,63.16
ceval-high_school_history,7eb30a,accuracy,gen,70.00
ceval-middle_school_history,48ab4a,accuracy,gen,59.09
ceval-civil_servant,87d061,accuracy,gen,53.19
ceval-sports_science,70f27b,accuracy,gen,52.63
ceval-plant_protection,8941f9,accuracy,gen,59.09
ceval-basic_medicine,c409d6,accuracy,gen,47.37
ceval-clinical_medicine,49e82d,accuracy,gen,40.91
ceval-urban_and_rural_planner,95b885,accuracy,gen,45.65
ceval-accountant,002837,accuracy,gen,26.53
ceval-fire_engineer,bc23f5,accuracy,gen,22.58
ceval-environmental_impact_assessment_engineer,c64e2d,accuracy,gen,64.52
ceval-tax_accountant,3a5e3c,accuracy,gen,34.69
ceval-physician,6e277d,accuracy,gen,40.82
ceval-stem,-,naive_average,gen,35.09
ceval-social-science,-,naive_average,gen,52.79
ceval-humanities,-,naive_average,gen,52.58
ceval-other,-,naive_average,gen,44.36
ceval-hard,-,naive_average,gen,23.91
ceval,-,naive_average,gen,44.16
$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$

-------------------------------------------------------------------------------------------------------------------------------- THIS IS A DIVIDER --------------------------------------------------------------------------------------------------------------------------------

raw format
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
-------------------------------
Model: opencompass.models.huggingface.HuggingFace_model_repos_internlm-chat-7b
ceval-computer_network: {'accuracy': 31.57894736842105}
ceval-operating_system: {'accuracy': 36.84210526315789}
ceval-computer_architecture: {'accuracy': 28.57142857142857}
ceval-college_programming: {'accuracy': 32.432432432432435}
ceval-college_physics: {'accuracy': 26.31578947368421}
ceval-college_chemistry: {'accuracy': 16.666666666666664}
ceval-advanced_mathematics: {'accuracy': 21.052631578947366}
ceval-probability_and_statistics: {'accuracy': 38.88888888888889}
ceval-discrete_mathematics: {'accuracy': 18.75}
ceval-electrical_engineer: {'accuracy': 35.13513513513514}
ceval-metrology_engineer: {'accuracy': 50.0}
ceval-high_school_mathematics: {'accuracy': 22.22222222222222}
ceval-high_school_physics: {'accuracy': 31.57894736842105}
ceval-high_school_chemistry: {'accuracy': 15.789473684210526}
ceval-high_school_biology: {'accuracy': 36.84210526315789}
ceval-middle_school_mathematics: {'accuracy': 26.31578947368421}
ceval-middle_school_biology: {'accuracy': 61.904761904761905}
ceval-middle_school_physics: {'accuracy': 63.1578947368421}
ceval-middle_school_chemistry: {'accuracy': 60.0}
ceval-veterinary_medicine: {'accuracy': 47.82608695652174}
ceval-college_economics: {'accuracy': 41.81818181818181}
ceval-business_administration: {'accuracy': 33.33333333333333}
ceval-marxism: {'accuracy': 68.42105263157895}
ceval-mao_zedong_thought: {'accuracy': 70.83333333333334}
ceval-education_science: {'accuracy': 58.620689655172406}
ceval-teacher_qualification: {'accuracy': 70.45454545454545}
ceval-high_school_politics: {'accuracy': 26.31578947368421}
ceval-high_school_geography: {'accuracy': 47.368421052631575}
ceval-middle_school_politics: {'accuracy': 52.38095238095239}
ceval-middle_school_geography: {'accuracy': 58.333333333333336}
ceval-modern_chinese_history: {'accuracy': 73.91304347826086}
ceval-ideological_and_moral_cultivation: {'accuracy': 63.1578947368421}
ceval-logic: {'accuracy': 31.818181818181817}
ceval-law: {'accuracy': 25.0}
ceval-chinese_language_and_literature: {'accuracy': 30.434782608695656}
ceval-art_studies: {'accuracy': 60.60606060606061}
ceval-professional_tour_guide: {'accuracy': 62.06896551724138}
ceval-legal_professional: {'accuracy': 39.130434782608695}
ceval-high_school_chinese: {'accuracy': 63.1578947368421}
ceval-high_school_history: {'accuracy': 70.0}
ceval-middle_school_history: {'accuracy': 59.09090909090909}
ceval-civil_servant: {'accuracy': 53.191489361702125}
ceval-sports_science: {'accuracy': 52.63157894736842}
ceval-plant_protection: {'accuracy': 59.09090909090909}
ceval-basic_medicine: {'accuracy': 47.368421052631575}
ceval-clinical_medicine: {'accuracy': 40.909090909090914}
ceval-urban_and_rural_planner: {'accuracy': 45.65217391304348}
ceval-accountant: {'accuracy': 26.53061224489796}
ceval-fire_engineer: {'accuracy': 22.58064516129032}
ceval-environmental_impact_assessment_engineer: {'accuracy': 64.51612903225806}
ceval-tax_accountant: {'accuracy': 34.69387755102041}
ceval-physician: {'accuracy': 40.816326530612244}
ceval-stem: {'naive_average': 35.09356534942919}
ceval-social-science: {'naive_average': 52.78796324667468}
ceval-humanities: {'naive_average': 52.57983339778566}
ceval-other: {'naive_average': 44.36193216316587}
ceval-hard: {'naive_average': 23.90807748538011}
ceval: {'naive_average': 44.15596847357301}
$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$


```

# 进阶作业
使用 OpenCompass 评测 InternLM2-Chat-7B 模型使用 LMDeploy 0.2.0 部署后在 C-Eval 数据集上的性能
## 进阶作业solutions:
采用上一节的`/root/lmdeploy/quant_outputW4A16/`模型来进行测评

```bash

cd ~/opencompass
conda activate opencompass

python run.py --datasets ceval_gen --hf-path /root/lmdeploy/quant_outputW4A16/ --tokenizer-path /root/lmdeploy/quant_outputW4A16/ --tokenizer-kwargs padding_side='left' truncation='left' trust_remote_code=True --model-kwargs trust_remote_code=True device_map='auto' --max-seq-len 2048 --max-out-len 16 --batch-size 4 --num-gpus 1 --debug

```
## 输出结果

不知在什么地方出问题了, 很多的任务accuracy都是0
```bash
ceval-computer_network                          db9ce2     accuracy       gen                                                                        0
ceval-operating_system                          1c2571     accuracy       gen                                                                        0
ceval-computer_architecture                     a74dad     accuracy       gen                                                                        0
ceval-college_programming                       4ca32a     accuracy       gen                                                                        0
ceval-college_physics                           963fa8     accuracy       gen                                                                        0
ceval-college_chemistry                         e78857     accuracy       gen                                                                        0
ceval-advanced_mathematics                      ce03e2     accuracy       gen                                                                        0
ceval-probability_and_statistics                65e812     accuracy       gen                                                                       27.78
ceval-discrete_mathematics                      e894ae     accuracy       gen                                                                        0
ceval-electrical_engineer                       ae42b9     accuracy       gen                                                                        0
ceval-metrology_engineer                        ee34ea     accuracy       gen                                                                        0
ceval-high_school_mathematics                   1dc5bf     accuracy       gen                                                                       33.33
ceval-high_school_physics                       adf25f     accuracy       gen                                                                        0
ceval-high_school_chemistry                     2ed27f     accuracy       gen                                                                        0
ceval-high_school_biology                       8e2b9a     accuracy       gen                                                                        0
ceval-middle_school_mathematics                 bee8d5     accuracy       gen                                                                        0
ceval-middle_school_biology                     86817c     accuracy       gen                                                                        0
ceval-middle_school_physics                     8accf6     accuracy       gen                                                                        0
ceval-middle_school_chemistry                   167a15     accuracy       gen                                                                        0
ceval-veterinary_medicine                       b4e08d     accuracy       gen                                                                        0
ceval-college_economics                         f3f4e6     accuracy       gen                                                                        0
ceval-business_administration                   c1614e     accuracy       gen                                                                        0
ceval-marxism                                   cf874c     accuracy       gen                                                                        0
ceval-mao_zedong_thought                        51c7a4     accuracy       gen                                                                        0
ceval-education_science                         591fee     accuracy       gen                                                                        0
ceval-teacher_qualification                     4e4ced     accuracy       gen                                                                        0
ceval-high_school_politics                      5c0de2     accuracy       gen                                                                        0
ceval-high_school_geography                     865461     accuracy       gen                                                                       15.79
ceval-middle_school_politics                    5be3e7     accuracy       gen                                                                        0
ceval-middle_school_geography                   8a63be     accuracy       gen                                                                        0
ceval-modern_chinese_history                    fc01af     accuracy       gen                                                                        0
ceval-ideological_and_moral_cultivation         a2aa4a     accuracy       gen                                                                       26.32
ceval-logic                                     f5b022     accuracy       gen                                                                        0
ceval-law                                       a110a1     accuracy       gen                                                                        0
ceval-chinese_language_and_literature           0f8b68     accuracy       gen                                                                       30.43
ceval-art_studies                               2a1300     accuracy       gen                                                                        0
ceval-professional_tour_guide                   4e673e     accuracy       gen                                                                        0
ceval-legal_professional                        ce8787     accuracy       gen                                                                        0
ceval-high_school_chinese                       315705     accuracy       gen                                                                        0
ceval-high_school_history                       7eb30a     accuracy       gen                                                                        0
ceval-middle_school_history                     48ab4a     accuracy       gen                                                                        0
ceval-civil_servant                             87d061     accuracy       gen                                                                        0
ceval-sports_science                            70f27b     accuracy       gen                                                                        0
ceval-plant_protection                          8941f9     accuracy       gen                                                                        0
ceval-basic_medicine                            c409d6     accuracy       gen                                                                        0
ceval-clinical_medicine                         49e82d     accuracy       gen                                                                        0
ceval-urban_and_rural_planner                   95b885     accuracy       gen                                                                        0
ceval-accountant                                002837     accuracy       gen                                                                       32.65
ceval-fire_engineer                             bc23f5     accuracy       gen                                                                        0
ceval-environmental_impact_assessment_engineer  c64e2d     accuracy       gen                                                                        0
ceval-tax_accountant                            3a5e3c     accuracy       gen                                                                        0
ceval-physician                                 6e277d     accuracy       gen                                                                        0
ceval-stem                                      -          naive_average  gen                                                                        3.06
ceval-social-science                            -          naive_average  gen                                                                        1.58
ceval-humanities                                -          naive_average  gen                                                                        5.16
ceval-other                                     -          naive_average  gen                                                                        2.97
ceval-hard                                      -          naive_average  gen                                                                        7.64
ceval                                           -          naive_average  gen                                                                        3.2
02/23 21:26:40 - OpenCompass - INFO - write summary to /root/opencompass/outputs/default/20240223_210400/summary/summary_20240223_210400.txt
02/23 21:26:40 - OpenCompass - INFO - write csv to /root/opencompass/outputs/default/20240223_210400/summary/summary_20240223_210400.csv


```
