<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# remove the references and export as readme.md file

Here is the perfectly formatted README that you can use as `readme.md`. All reference markers have been removed for a clean export.

***

# MNIST Digit Classification with PyTorch

This project implements two efficient PyTorch models for classifying handwritten digits from the MNIST dataset. Both models follow strict constraints for high accuracy, efficiency, and compact architecture.

***

## Project Goals

- **Validation/Test Accuracy** ≥ 99.4%
- **Parameter Budget**: < 20,000 trainable parameters
- **Regularization**: Batch Normalization (BN), Dropout (p=0.05)
- **Epoch Limit**: < 20 training epochs
- **Network Architecture**: ≥ 1 Fully Connected (FC) layer or Global Average Pooling (GAP)

***

## Model Comparison

| Feature | Cursor1.py | Cursor2.py |
| :-- | :-- | :-- |
| **Total Parameters** | ~15,800 | ~18,100 |
| **Batch Normalization** | Yes | Yes |
| **Dropout** | Yes (p=0.05) | Yes (p=0.05) |
| **FC or GAP Layer** | GAP + FC (28 → 10) | GAP + FC (32 → 10) |
| **Data Augmentation** | No | Yes (light affine transforms) |
| **Optimizer** | Adam | AdamW + OneCycleLR |
| **Epochs to Target** | Not reached 99.4% | Reached 99.4% within 20 |
| **Validation/Test Accuracy** | < 99.4% | **99.46%** |


***

## Cursor2.py: Successful Model

- **Architecture**: Deeper convolutions, BN and Dropout (5%), light image augmentation, GAP layer, single FC output.
- **Training**: AdamW optimizer, OneCycleLR schedule, early stopping on reaching accuracy.
- **Parameter count**: ~18,100 (< 20k).
- **Accuracy achieved**: **99.46% (Validation/Test)**.

***

## Validation/Test Logs

_The following table shows training and validation results for Cursor2.py. The 10K validation set is treated as the test set._


| Epoch | Train Loss | Val Loss | Val Acc (%) | Best Acc (%) | Epoch Best |
| :-- | :-- | :-- | :-- | :-- | :-- |
| 1 | 0.9992 | 0.1623 | 96.85 | 96.85 | 1 |
| 2 | 0.4381 | 0.1406 | 97.35 | 97.35 | 2 |
| 3 | 0.3999 | 0.1532 | 97.10 | 97.35 | 2 |
| 4 | 0.3822 | 0.1122 | 97.86 | 97.86 | 4 |
| 5 | 0.3685 | 0.0797 | 98.85 | 98.85 | 5 |
| 6 | 0.3624 | 0.0825 | 98.83 | 98.85 | 5 |
| 7 | 0.3588 | 0.0737 | 98.94 | 98.94 | 7 |
| 8 | 0.3525 | 0.0655 | 99.11 | 99.11 | 8 |
| 9 | 0.3488 | 0.0608 | 99.27 | 99.27 | 9 |
| 10 | 0.3468 | 0.0772 | 99.16 | 99.27 | 9 |
| 11 | 0.3426 | 0.0688 | 99.18 | 99.27 | 9 |
| 12 | 0.3405 | 0.0635 | 99.19 | 99.27 | 9 |
| 13 | 0.3376 | 0.0619 | 99.34 | 99.34 | 13 |
| 14 | 0.3345 | 0.0563 | **99.46** | **99.46** | 14 |
| 15 | 0.3313 | 0.0580 | 99.33 | **99.46** | 14 |
| 16 | 0.3305 | 0.0556 | 99.43 | **99.46** | 14 |
| 17 | 0.3273 | 0.0586 | 99.38 | **99.46** | 14 |
| 18 | 0.3272 | 0.0546 | 99.41 | **99.46** | 14 |
| 19 | 0.3258 | 0.0557 | 99.42 | **99.46** | 14 |
| 20 | 0.3261 | 0.0562 | 99.40 | **99.46** | 14 |

**Best Validation/Test Accuracy:**
**99.46% at epoch 14**

***

## Usage

1. Load the MNIST dataset with a 50,000/10,000 split.
2. Use the `MNISTNet` class from either `cursor1.py` or `cursor2.py`.
3. Train with Adam (`cursor1.py`) or AdamW + OneCycleLR (`cursor2.py`).
4. Employ BatchNorm, Dropout (5%), and GAP as defined.
5. Evaluate performance on the validation/test set.

***

## Summary \& Recommendations

Cursor2.py surpasses Cursor1.py by introducing data augmentation and advanced learning rate scheduling, achieving the target accuracy (**99.46%**) in fewer than 20 epochs with minimal parameter count and complexity.
For reliable, compact MNIST digit classification, use the Cursor2.py implementation.

---
<span style="display:none">[^1]</span>

<div style="text-align: center">⁂</div>

[^1]: readme.md

"# MNIST_lessParameters_more_accuracy" 
