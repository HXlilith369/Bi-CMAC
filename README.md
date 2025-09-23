# Bi-CMAC
This repository contains the code for Bi-directional Cross-Modal Sentiment Analysis (BCMSA), which integrates gated fusion and supervised contrastive learning to enhance multimodal sentiment recognition.

The code in this project was accelerated with the assistance of AI and subsequently verified and/or modified by the authors, who also take responsibility for any potential errors. Some comments were modified with AI support as part of discussions between the authors and the AI.

We release two code versions: an original ipynb notebook that preserves traces of early experiments (including some repetition and verbosity) for learning purposes, and a project version that has been cleaned up and refactored for reproducibility and extension.The project version repository will be made publicly available soon.

The data for testing is shared on Baidu Cloud. Link: https://pan.baidu.com/s/1-XspU7kMl0BQyAIK70xxaA
Extraction code: dqy7
-- Shared by Baidu Cloud Super Member V6.

1.Resource Utilization Statement
Our main and ablation experiments were conducted on H20-NVLink (96GB) GPUs. Due to the high computational cost, we report results from relatively strong runs. However, we observed that the performance variance under the same parameter settings was not significant.

2.For binary classification, when class 0 is excluded we recommend disabling the class-imbalance weighting module; for binary classification including class 0 and for the seven-class setting, we enable this module to mitigate label-distribution imbalance.

3.The key hyperparameters are as follows.

| Parameter                  | Value      | Note               |
| -------------------------- | ---------- | ------------------ |
| Feature dims (text/audio)  | 768 / 1024 | Projected to 768   |
| Attention heads            | 8          | Standard setting   |
| Dropout                    | 0.01       | Small MOSI dataset |
| Weight decay               | 1e-2       | AdamW              |
| Epochs / Patience          | 10 / 5     | Early stopping     |
| Contrastive weight warm-up | 0 → 0.05   | Over 5 epochs      |
| Same-utterance pair weight | 2.0        | SupCon             |
| Temperature                | 0.07       | InfoNCE            |
| Gradient clipping          | 1.0        | Stability          |

