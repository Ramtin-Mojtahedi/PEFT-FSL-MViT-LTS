# Results and Discussion

## LoRA Ranks Comparison
The performance of Swin UNETR fine-tuned with various LoRA ranks is summarized below:

| **Method**            | **Trainable Parameters (M)** | **Avg. Dice** | **Avg. HD95 (mm)** |
|-----------------------|-----------------------------|---------------|--------------------|
| LoRA Rank 2          | 54.4                       | 0.659         | 53.6              |
| LoRA Rank 4          | 54.6                       | 0.618         | 86.5              |
| **LoRA Rank 8**      | **55.2**                   | **0.666**     | **49.4**          |
| LoRA Rank 16         | 56.2                       | 0.655         | 65.5              |
| Traditional Fine-Tuning | 62.2                    | 0.578         | 144               |

LoRA with rank 8 achieved the best segmentation performance, with an average Dice score of 0.666 and HD95 of 49.4 mm, significantly outperforming traditional fine-tuning.

---

## Few-Shot Learning (FSL) with LoRA Rank 8
The performance of LoRA Rank 8 across different sample sizes is shown below:

| **Sample Size**       | **Avg. Dice** | **Avg. HD95 (mm)** |
|-----------------------|---------------|--------------------|
| 5                     | 0.620         | 89.5              |
| 10                    | 0.666         | 49.4              |
| 15                    | 0.666         | 79.3              |
| Whole Training Set    | 0.668         | 36.7              |

With only 10 training samples, the model achieved a Dice score of 0.666, just 0.3% lower than the score obtained using the full training set. The HD95 for 10 samples was 49.4 mm compared to 36.7 mm for the entire training set, showing high adaptability even with limited data.

---

## Key Observations
- **Optimal Rank**: LoRA Rank 8 balances segmentation accuracy and computational efficiency.
- **Few-Shot Efficiency**: The model performs well with only 10 samples, highlighting its robustness in data-scarce scenarios.
- **Improvement over Traditional Fine-Tuning**: LoRA fine-tuning significantly reduces HD95 and increases Dice scores compared to traditional methods.

These results demonstrate the effectiveness of LoRA in parameter-efficient fine-tuning and its potential for medical imaging applications with limited annotated data.
