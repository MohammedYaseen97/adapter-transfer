# idiomaticity-detection

**Objective**: Run the idiomaticity detection experiment to establish if adapter-based models and contrastive fine-tuning models detect idiomatic usage better than BERT model

## Dataset used
The experiments have been performed using [SemEval 2022 Task-2](https://github.com/H-TayyarMadabushi/SemEval_2022_Task2-idiomaticity) data

## Experiment Setup
- The original source code that runs both training and evaluation is obtained from [here](https://github.com/H-TayyarMadabushi/AStitchInLanguageModels/blob/main/Dataset/Task2/Utils/run_glue_f1_macro.py).
- A separate code file is used to run and evaluate for adapter-based approach. Based on the modified version available [here](https://github.com/adapter-hub/adapter-transformers/blob/master/examples/pytorch/text-classification/run_glue.py). It has been modified further for the sake of this experiment and local copy is available at [run_glue_f1_macro_adapters.py](./scripts/run_glue_f1_macro_adapters.py).

### Experiment Tracker

| Experiment | Notebook | Single Token Rep | Dataset  | Model | Context | Status |
|:-----------|:---------|:-----------------|:---------|:------|:--------|:-------|
| exp0 | [exp0](./experiments/exp0) | No | Zero-shot | BERT base (cased) | No Context | Done (3GPUs) |
| exp1 | [exp1](./notebooks/exp1) | No | Zero-shot | XLNet base (cased) | No Context | Done (4GPUs) | 
| exp2 | [exp2](./notebooks/exp2) | No | Zero-shot | *BERT base (cased)* | All Context | Done (4GPUs) |
| **exp3A_1**| [exp3A_1](./notebooks/exp3A_1) | Yes | Zero-shot | *BERT base (cased)* | No Context | Done (4GPUs) |
| **exp3A_2**| [exp3A_2](./notebooks/exp3A_2) | Yes | Zero-shot | *BERT base (cased)* | No Context | Done (4GPUs) |
| **exp3B_1**| [exp3B_1](./notebooks/exp3B_1) | Yes | Zero-shot | ToBeDecided | ToBeDecided | TODO |
| **exp3B_2**| [exp3B_2](./notebooks/exp3B_2) | Yes | Zero-shot | ToBeDecided | ToBeDecided | TODO |
| exp4 | [exp4](./notebooks/exp4) | ToBeDecided | One-shot | ToBeDecided | ToBeDecided | TODO |
| exp5 | [exp5](./notebooks/exp5) | ToBeDecided | Few-shot | ToBeDecided | ToBeDecided | TODO |

# TODO
- Have to attempt to use transfer learning with the help of adapters (MAD-X architecture) to pinpoint if idioms are a lingual task or a separate task.
- Perform the contrastive based tuning on idioms rather than words to see if there is any improvement in detecting idioms.

## Results

| Experiment | Dev Accuracy | Dev F1 | Test Accuracy | Test F1 |
|:-----------|:-------------|:-------|:--------------|:--------|
| exp0 | 85.16 | 83.00 | 0.0 | 0.0 |
| exp1 | 87.60 | 85.38 | 0.0 | 0.0 |
| exp2 | 84.91 | 81.50 | 0.0 | 0.0 |
| exp3A_1| 78.26 | 67.54 | 0.0 | 0.0 |
| exp3A_2| 80.39 | 74.21 | 0.0 | 0.0 |

# TODO
- Track & Visualise Training progress
- Hyperparameter tuning

## References
[1] H. Tayyar Madabushi, E. Gow-Smith, C. Scarton, and A. Villavicencio, “AStitchInLanguageModels: Dataset and Methods for the Exploration of Idiomaticity in Pre-Trained Language Models,” in Findings of the Association for Computational Linguistics: EMNLP 2021, Punta Cana, Dominican Republic, 2021, pp. 3464–3477. doi: 10.18653/v1/2021.findings-emnlp.294.

[2] Harish Tayyar Madabushi, Edward Gow-Smith, Marcos Garcia, Carolina Scarton, Marco Idiart, and Aline Villavicencio. 2022. SemEval-2022 Task 2: Multilingual Idiomaticity Detection and Sentence Embedding. In Proceedings of the 16th International Workshop on Semantic Evaluation (SemEval-2022), pages 107–121, Seattle, United States. Association for Computational Linguistics.

[3] Jonas Pfeiffer, Ivan Vulić, Iryna Gurevych, and Sebastian Ruder. 2020. MAD-X: An Adapter-Based Framework for Multi-Task Cross-Lingual Transfer. In Proceedings of the 2020 Conference on Empirical Methods in Natural Language Processing (EMNLP), pages 7654–7673, Online. Association for Computational Linguistics.

[4] Qianchu Liu, Fangyu Liu, Nigel Collier, Anna Korhonen, and Ivan Vulić. 2021. MirrorWiC: On Eliciting Word-in-Context Representations from Pretrained Language Models. In Proceedings of the 25th Conference on Computational Natural Language Learning, pages 562–574, Online. Association for Computational Linguistics.

## License
TODO
