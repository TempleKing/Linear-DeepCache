
# Linear-DeepCache: Non-Uniform Step Scheduling for SDXL Acceleration

This repository presents **Linear-DeepCache**, an optimization strategy that enhances Stable Diffusion XL (SDXL) inference by applying a non-uniform caching schedule. Our method achieves a **+2.1dB PSNR improvement** over the standard DeepCache baseline without any additional computational cost or training.

---

## 🏆 Key Research Highlights
The core of this project is the discovery that U-Net feature evolution in SDXL is non-uniform. By dense-sampling at the early stages and sparse-sampling later (Linear Schedule), we significantly mitigate feature drift.

- **[Read the Full Technical Report](./Linear_Distribution_Cache_paper.pdf)**: Our comprehensive 11-page analysis, including methodology and final conclusions.
---

## 🚀 Quick Start Guide

To reproduce our results, we recommend following these steps to manage compute resources efficiently:

### 1. Environment Setup
```bash
pip install diffusers transformers accelerate DeepCache
```
### 2. Generate a **Read Token** in your [Hugging Face Settings](https://huggingface.co/settings/tokens)

### 3. Dataset Preparation (Recommended)

The full [900k Diffusion Prompts Dataset](https://www.kaggle.com/datasets/tanreinama/900k-diffusion-prompts-dataset/data) is too large for most local environments. We provide a utility script to create a manageable subset:

1.  Open `notebooks/CUT.py` (or your cut code).
    
2.  Adjust the sample size to your preference.
    
3.  Run the script to generate a smaller `.csv` file in the `data/` folder.

### 4. Running the Experiment

Once you have your subset ready, run the main implementation:

-   Open `notebooks/Linear_distribution_cache.ipynb`.
    
-   This notebook will execute the comparison between Uniform and Linear schedules and output the PSNR/CLIP metrics.

## 📂 Repository Structure

-   **`data/`**: Contains `prompts_sample_50.csv` for quick testing.
    
-   **`notebooks/`**: Main experimental code for Linear Step Scheduling.
    
-   **`experiments/`**: Additional research modules
    
-   **`result/`**: High-resolution screenshots and plots of our findings.
    
-   **`Linear_Distribution_Cache_paper.pdf`**: The final technical report.

## 📚 References

1.  **DeepCache**: [arXiv:2312.00858](https://arxiv.org/abs/2312.00858)
    
2.  **SDXL 1.0**: [arXiv:2307.01952](https://arxiv.org/abs/2307.01952)
    
3.  **900k Prompts Dataset**: [Kaggle Link](https://www.kaggle.com/datasets/tanreinama/900k-diffusion-prompts-dataset/data)
