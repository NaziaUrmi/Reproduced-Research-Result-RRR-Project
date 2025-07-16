# Reproduced Research Results (RRR) Project

This repository contains my work on reproducing results from selected research papers in the field of machine learning, computer vision, and neuroscience. For each paper, I analyze the publication, locate or reconstruct any missing code and datasets, and attempt to reproduce the reported results. Successful reproductions are documented in individual Jupyter notebooks.

## Table of Contents

- [Overview](#overview)
- [Repository Structure](#repository-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Adding a New Reproduction](#adding-a-new-reproduction)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

---

## Overview

The goal of the RRR Project is to increase transparency and reproducibility in research by systematically reproducing results from influential papers. Each subfolder contains:

- The original paper reference and link.
- A Jupyter notebook that documents the reproduction process step by step.
- Any scripts, configuration files, or helper modules required for execution.

If code or datasets were not publicly released, I search for alternatives or re-implement missing pieces based on the paper's description.

## Repository Structure

```plaintext
├── AdaSlot.ipynb           # Reproduction of "AdaSlot" paper experiments
├── DFRSC_result_jupiter_notebook.ipynb   # Reproduction of DFRSC results
├── fmri.ipynb              # fMRI analysis reproduction
├── NEXTGQA.ipynb           # "NEXTGQA" paper reproduction
├── satmae.ipynb            # "SatMAE" paper experiments
├── textnerf.ipynb          # "TextNeRF" paper reproduction
├── datasets/               # Downloaded or preprocessed datasets
│   ├── AdaSlot/            # Datasets for AdaSlot
│   └── ...
├── src/                    # Helper scripts and modules
│   ├── data_loader.py
│   ├── utils.py
│   └── ...
├── requirements.txt        # Python dependencies
└── README.md               # Project overview and instructions
