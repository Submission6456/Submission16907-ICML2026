## Dataset

| Parameter | Value |
|---|---|
| Dataset | `digits` (sklearn `load_digits`) |
| Input dimensionality | 64 (8×8 pixel images) |
| Number of classes | 10 |
| Total samples | 1797 |
| Standardization | Yes |
| Precision | float64 |

## Model Architecture

| Parameter | Value |
|---|---|
| Architecture | NN (2-hidden-layer MLP) |
| Hidden layers | 64 → 32 |
| Activations | ReLU |
| Output | Linear (10 classes) |
| Loss | Cross-entropy + L2 regularization |

## Unlearning Evaluation

| Parameter | Value |
|---|---|
| Epoch budget (T) | 10 |
| Batch size | 64 |
| Weight decay | 0.1 |
| Forget fraction (r_f) range | [3.0e-03, 1.0e-01] |
| Number of r_f grid points | 3 |
| r_f values | 3.0e-03, 1.73e-02, 1.0e-01 |
| Seeds | 10 (seeds 0–9) |

## Unlearning Methods

| Method | Unlearning LR | Decay | Timing | κ_dp | alpha |
|---|---|---|---|---|
| VRU | 0.1 | 0.7 | empirical | - |
| Fine-Tune (NFT) | 2e-3 | 0.7 | - |
| NegGrad+ | 2e-3 | 0.7 | 0.01 |
| SCRUB | 1e-3 | 0.7 | 0.01 |

## Privacy Evaluation (U-LiRA)

| Parameter | Value |
|---|---|
| Attack type | U-LiRA (Unlearning-adapted LiRA) |
| Number of shadow models | 100 |
| Score function | LiRA (true-class logit minus logsumexp of other logits) |
| Statistical test | Gaussian likelihood ratio (IN vs OUT) |
