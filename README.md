# Attention Entropy Under Context Stress

**A multi-model study of attention entropy as a predictor of retrieval failure in transformer language models under context stress.**

**DOI:** 10.5281/zenodo.20410919

**Preprint:** [Read on Zenodo](https://zenodo.org/record/20410919)

**Date**: May 24, 2026

## Overview

This repository contains the code, notebooks, results, and LaTeX source for the paper:

> **Attention Entropy Under Context Stress: A Multi-Model Study of Retrieval Failure in Transformer Language Models**

The study investigates whether **attention entropy** at the query token can serve as a lightweight diagnostic signal for retrieval failure in Transformer language models when subjected to increasing context length and token noise.

### Key Findings
- Strong negative correlation between attention entropy and retrieval accuracy in base GPT-2 models (Pearson *r* up to −0.51, ROC-AUC up to 0.78)
- Token noise is a significantly stronger stressor than context length
- TinyLlama exhibits "**confident failure**" — low entropy with near-chance accuracy when evaluated outside its instruction-tuning distribution
- Pooling results across heterogeneous model families can invert correlation signals; **per-model analysis is essential**

## Repository Structure

```
.
├── latex/                  # LaTeX source files for the paper
├── notebooks/              # Jupyter notebooks for experiments & analysis
├── paper/                  # Compiled PDF and figures
├── results/                # Raw results, metrics, and cached data
├── README.md               # This file
├── requirements            # Python package requirements

```

## Setup

```bash
1. Clone the repo
git clone https://github.com/salmanullahkhan1/attention-entropy-context-stress.git
cd attention-entropy-context-stress

2. Install dependencies
pip install -r requirements
```

## Experiments

**Task**: Synthetic key-value retrieval with controlled stress
- Hidden fact: `The secret code for {key} is {value}.`
- Distractor sentences + variable noise
- Query: `What is the secret code for {key}?`

**Conditions**:
- Context lengths: 32, 64, 128, 256, 512 distractors
- Noise ratios: 0.0, 0.1, 0.2, 0.3, 0.4

**Models**:
- GPT-2 (124M)
- GPT-2 Medium (355M)
- GPT-2 Large (774M)
- TinyLlama-1.1B-Chat

## Results

Detailed results, figures, and statistical analysis are available in:
- `paper/attention_entropy_paper.pdf`
- `notebooks/` (reproducible analysis)
- `results/` directory

 ## Citation

If you reference this work, please cite:

```bibtex
@misc{kennedy2026attention,
  author       = {Khan, Salman Ullah},
  title        = {Attention Entropy Under Context Stress: A Multi-Model 
                  Study of Retrieval Failure in Transformer Language Models},
  year         = {2026},
  month        = {May},
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.20410919},
  url          = {https://doi.org/10.5281/zenodo.20410919}
}
```

---

*Independent research project • May 2026*
