# Bi-CMAC
This repository contains the code for Bi-directional Cross-Modal Sentiment Analysis (BCMSA), which integrates gated fusion and supervised contrastive learning to enhance multimodal sentiment recognition.

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

