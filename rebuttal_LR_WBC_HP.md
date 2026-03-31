## Dataset

| Parameter | Value |
|---|---|
| Dataset | `breast_cancer` (sklearn `load_breast_cancer`) |
| Input dimensionality | 30 |
| Number of classes | 2 |
| Total samples | 569 |
| Standardization | Yes |
| Precision | float64 |

## Model Architecture

| Parameter | Value |
|---|---|
| Architecture | LR (Logistic Regression) |
| Layers | Single linear layer (30 → 2) |
| Bias | Yes |
| Output | Linear (2 classes) |
| Loss | Cross-entropy + L2 regularization |

## Unlearning Evaluation

| Parameter | Value |
|---|---|
| Epoch budget (T) | 5 |
| Batch size | 64 |
| Weight decay | 0.1 |
| Forget fraction (r_f) range | [6.0e-03, 1.0e-01] |
| Number of r_f grid points | 3 |
| r_f values | 6.0e-03, 2.45e-02, 1.0e-01 |
| Seeds | 2 (seeds 0–1) |

## Unlearning Methods

| Method | Unlearning LR | Decay | α |
|---|---|---|---|
| VRU | 1 | 0.7 | - |
| Fine-Tune (NFT) | 1e-3 | 0.7 | - |
| NegGrad+ | 5e-3 | 0.7 | 0.02 |
| SCRUB | 5e-3 | 0.8 | 0.01 |

## Privacy Evaluation (U-LiRA)

| Parameter | Value |
|---|---|
| Attack type | U-LiRA (Unlearning-adapted LiRA) |
| Number of shadow models | 7 |
| Score function | LiRA (true-class logit minus logsumexp of other logits) |
| Statistical test | Gaussian likelihood ratio (IN vs OUT) |
