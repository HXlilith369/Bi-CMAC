# Bi-CMAC
This repository contains the code for Bi-directional Cross-Modal Sentiment Analysis (BCMSA), which integrates gated fusion and supervised contrastive learning to enhance multimodal sentiment recognition.
1.Resource Utilization Statement
Our main and ablation experiments were conducted on H20-NVLink (96GB) GPUs. Due to the high computational cost, we report results from relatively strong runs. However, we observed that the performance variance under the same parameter settings was not significant.

2.For binary classification, when class 0 is excluded we recommend disabling the class-imbalance weighting module; for binary classification including class 0 and for the seven-class setting, we enable this module to mitigate label-distribution imbalance.

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

