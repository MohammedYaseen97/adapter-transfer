# idiomaticity-detection

**Objective**: Run the idiomaticity detection experiment to establish if adapter-based models and contrastive fine-tuning models detect idiomatic usage better than BERT model

## Dataset used
The experiments have been performed using [SemEval 2022 Task-2](https://github.com/H-TayyarMadabushi/SemEval_2022_Task2-idiomaticity) data

## Experiment Setup
- The original source code that runs both training and evaluation is obtained from [here](https://github.com/H-TayyarMadabushi/AStitchInLanguageModels/blob/main/Dataset/Task2/Utils/run_glue_f1_macro.py).
- A separate code file is used to run and evaluate for adapter-based approach. Based on the modified version available [here](https://github.com/adapter-hub/adapter-transformers/blob/master/examples/pytorch/text-classification/run_glue.py). It has been modified further for the sake of this experiment and local copy is available at [run_glue_f1_macro_adapters.py](./scripts/run_glue_f1_macro_adapters.py).

## Results

|     Setting      |     Model                                                          |     Acc       |     F1        |
|------------------|--------------------------------------------------------------------|---------------|---------------|
|     Zero-Shot    |     Baseline : mBERT for EN idiomatic usage detection              |     0.7189    |     0.7026    |
|                  |     Baseline : mBERT for PT idiomatic usage detection              |     0.6117    |     0.5836    |
|                  |     Baseline : mBERT for multilingual idiomatic usage detection    |     0.682     |     0.6809    |
|                  |     AdapterBERT for EN idiomatic usage detection                   |     0.6845    |     0.672     |
|                  |     AdapterBERT for PT idiomatic usage detection                   |     0.6886    |     0.675     |
|                  |     AdapterBERT for EN-PT idiomatic knowledge transfer             |     0.5458    |     0.5406    |
|                  |     AdapterBERT for PT-EN idiomatic knowledge transfer             |     0.5365    |     0.5365    |
|     One-Shot     |     Baseline : mBERT for EN idiomatic usage detection              |     0.8648    |     0.856     |
|                  |     Baseline : mBERT for PT idiomatic usage detection              |     0.8681    |     0.8666    |
|                  |     Baseline : mBERT for multilingual idiomatic usage detection    |     0.8606    |     0.8603    |
|                  |     AdapterBERT for EN idiomatic usage detection                   |     0.8906    |     0.8868    |
|                  |     AdapterBERT for PT idiomatic usage detection                   |     0.8608    |     0.8596    |
|                  |     AdapterBERT for EN-PT idiomatic knowledge transfer             |     0.652     |     0.6436    |
|                  |     AdapterBERT for PT-EN idiomatic knowledge transfer             |     0.6631    |     0.6629    |


## References
[1] H. Tayyar Madabushi, E. Gow-Smith, C. Scarton, and A. Villavicencio, “AStitchInLanguageModels: Dataset and Methods for the Exploration of Idiomaticity in Pre-Trained Language Models,” in Findings of the Association for Computational Linguistics: EMNLP 2021, Punta Cana, Dominican Republic, 2021, pp. 3464–3477. doi: 10.18653/v1/2021.findings-emnlp.294.

[2] Harish Tayyar Madabushi, Edward Gow-Smith, Marcos Garcia, Carolina Scarton, Marco Idiart, and Aline Villavicencio. 2022. SemEval-2022 Task 2: Multilingual Idiomaticity Detection and Sentence Embedding. In Proceedings of the 16th International Workshop on Semantic Evaluation (SemEval-2022), pages 107–121, Seattle, United States. Association for Computational Linguistics.

[3] Jonas Pfeiffer, Ivan Vulić, Iryna Gurevych, and Sebastian Ruder. 2020. MAD-X: An Adapter-Based Framework for Multi-Task Cross-Lingual Transfer. In Proceedings of the 2020 Conference on Empirical Methods in Natural Language Processing (EMNLP), pages 7654–7673, Online. Association for Computational Linguistics.

[4] Qianchu Liu, Fangyu Liu, Nigel Collier, Anna Korhonen, and Ivan Vulić. 2021. MirrorWiC: On Eliciting Word-in-Context Representations from Pretrained Language Models. In Proceedings of the 25th Conference on Computational Natural Language Learning, pages 562–574, Online. Association for Computational Linguistics.

## License
TODO
