# Reproduced Research Results (RRR) Project

## Overview

**Reproduced Research Results (RRR)** is an open-source initiative to tackle the reproducibility crisis in computational research. Reproducibility is a cornerstone of scientific progress, yet many published results are difficult or impossible to replicate independently. In fact, a 2016 survey in *Nature* found that over 70% of researchers could not reproduce another scientist's experiments, and about 60% were unable to reproduce even their own results:contentReference[oaicite:0]{index=0}. Such irreproducibility wastes time and resources and undermines public trust in science:contentReference[oaicite:1]{index=1}. In monetary terms, one analysis estimated that irreproducible preclinical research alone costs about $28 **billion** annually:contentReference[oaicite:2]{index=2}. These sobering figures highlight the need for greater transparency and verification of research findings.

RRR aims to help bridge this gap by providing a curated collection of **reproduced results from research papers** across machine learning and other computational fields. Each entry in this repository attempts to **replicate the experiments and outcomes** of a published study, using available code and data, or reimplementing methods when necessary. The goal is to verify whether the reported results can be obtained under the described conditions, and to provide a clear, step-by-step guide for others to follow. By sharing these reproductions, we hope to: (1) encourage reliability and integrity in research, (2) make it easier for practitioners to learn and build upon proven findings, and (3) identify which results are robust and which might need further investigation. We welcome the community to use these reproductions for learning, to suggest improvements, and to contribute their own reproducibility efforts to the project.

## Repository Structure

The repository is organized to make it easy to find and run each reproduced result. Notable files and directories include:

- **Reproductions (Jupyter Notebooks)** – Each paper or experiment has its own Jupyter Notebook (and possibly a dedicated folder) that contains the reproduction steps, explanations, and results:
  - `AdaSlot.ipynb` – Reproduction of *Adaptive Slot Attention: Object Discovery with Dynamic Slot Number* (CVPR 2024), demonstrating the adaptive slot mechanism on object discovery tasks.
  - `DFRSC_result_jupiter_notebook.ipynb` – Reproduction of *Rolling Shutter Correction with Intermediate Distortion Flow Estimation* (CVPR 2024), including setup of the original code and validation of its key results.
  - `fmri.ipynb` – Reproduction of results from an fMRI analysis study, illustrating the process of replicating statistical findings in a neuroscience context (e.g., brain imaging data processing and analysis).
  - `NEXTGQA.ipynb` – Reproduction related to the *NExT-GQA* video question answering benchmark, verifying results of a model or method applied to the NExT-GQA dataset (including evaluation of question-answering performance on video frames).
  - `satmae.ipynb` – Reproduction of *SatMAE: Pre-training Transformers for Temporal and Multi-Spectral Satellite Imagery* (NeurIPS 2022), showing how to pre-train and fine-tune the SatMAE model and comparing its performance to the paper's claims.
  - `textnerf.ipynb` – Reproduction of *TextNeRF: A Novel Scene-Text Image Synthesis Method based on Neural Radiance Fields* (CVPR 2024), demonstrating the method for synthesizing scene text in images using Neural Radiance Fields and validating the results reported by the authors.

- **Datasets/Outputs (optional)** – *Not tracked in this repository.* Large datasets or model weights required for reproductions are not included in the repo. Instead, instructions to download or prepare data are provided in each notebook. Similarly, any output files (e.g. generated images or logs) are either generated on the fly or shown in the notebooks. We avoid storing bulky data to keep the repository lightweight.

- **Environment/Requirements** – While there is no single unified requirements file at the root (due to each project having unique dependencies), each reproduction notebook or its accompanying instructions will specify the packages needed (often by referencing the original code's `requirements.txt` or environment settings). We recommend using isolated environments (e.g., via Conda or `venv`) for each reproduction to manage dependencies. In some cases, a general `environment.yml` or list of common libraries may be provided to help set up a baseline environment.

- `LICENSE` – The open-source license for this project (MIT License). See the **License** section below for more details.

- `README.md` – This documentation file, providing an overview of the project and guidance on how to use and contribute to it.

*(In future updates, the repository may be restructured to group reproductions into subdirectories by theme or domain if the number of reproductions grows. For now, the above notebooks are accessible at the repository root for convenience.)*

## Prerequisites

Before using this repository to reproduce results, please ensure you have the following prerequisites:

- **Python 3.x** – All reproductions use Python (typically Python 3.8+). Ensure you have a recent Python 3 installation.
- **Package Manager** – You should have `pip` (and/or Conda) available to install required Python packages. We highly recommend using a virtual environment (such as a Conda environment or `python -m venv`) to avoid dependency conflicts.
- **Jupyter Notebook** – The reproductions are provided as Jupyter Notebooks (`.ipynb`). You can use Jupyter Lab, Jupyter Notebook, or an IDE like VS Code to open and run these notebooks.
- **Git** – Many reproductions involve cloning the original authors’ code repositories. Make sure Git is installed so you can fetch those repositories as instructed.
- **Compute Resources** – Some experiments (especially in deep learning) are computationally intensive. Access to a machine with a GPU and sufficient RAM is recommended for reproducing deep learning results (e.g., training or heavy inference for models like AdaSlot, SatMAE, TextNeRF). CPU-only execution is possible for some notebooks, but may be significantly slower or might require reducing model sizes or using smaller subsets of data.
- **Disk Space** – Ensure you have enough storage for any datasets or model weights that need to be downloaded. Some datasets can be several gigabytes in size, and model checkpoints can also be large.
- **Internet Access** – An active internet connection is required to download datasets, clone code repositories, or install packages during the reproduction process.

## Installation

Reproducing experiments reliably requires an isolated environment. Below are detailed steps to set up your system.

### 1. Create a Virtual Environment (Recommended)
Choose one of the following methods to avoid dependency conflicts:

#### a. Using Conda
```bash
# Create an environment named "rrr-env" with Python 3.9
conda create --name rrr-env python=3.9 -y
conda activate rrr-env
```

#### b. Using venv (Linux/macOS)
```bash
# Create and activate a venv environment
python3 -m venv rrr-env
source rrr-env/bin/activate
```

#### c. Using venv (Windows)
```bash
# Create and activate a venv environment on Windows PowerShell
python -m venv rrr-env
.\rrr-env\Scripts\Activate.ps1

```
### 2. Install Core Dependencies
Install libraries commonly used across reproductions:
```bash
pip install --upgrade pip
pip install jupyter numpy pandas matplotlib scipy scikit-learn
```
Tip: If you plan to run deep learning experiments, install a GPU-enabled framework:
```bash
# PyTorch with CUDA (if your GPU and drivers support it)
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu117

```
### 3. Install Reproduction-Specific Requirements
Most notebooks reference their own requirements.txt or environment.yml. From the root directory, run:
```bash
# For pip-based requirements
pip install -r requirements.txt

# For Conda environment files
conda env update --file environment.yml --prune
```
**Note:** If a notebook lives in its own folder with a separate requirements.txt (e.g., satmae/requirements.txt), cd into that folder before running the install command.

### 4. Launch Jupyter
Start the interactive environment and open notebooks:
```bash
# Launch Jupyter Lab (recommended)
jupyter lab

# Or launch classic Jupyter Notebook
jupyter notebook
```
You should see a browser window displaying the repository contents. Click on a .ipynb file to get started.

## Usage
Follow these general guidelines when working with the reproduction notebooks:

**Select a Notebook:** Identify the paper you want to reproduce (e.g., textnerf.ipynb).

**Run Cells Sequentially:** Execute cells in order to ensure environment setup, data download, model execution, and result verification occur in the correct sequence.

**Data Handling:** Notebooks automatically download or preprocess data when possible. If manual steps are required, instructions are provided in markdown cells.

**Verify Results:** Many notebooks include assertions or comparison tables that display the paper’s reported metrics alongside reproduced values.

**Troubleshooting:** Check error messages carefully, ensure you activated the correct environment, and validate that dependencies match the versions specified in the notebook. Opening an issue with detailed logs helps maintainers assist you faster.

Example: To reproduce the AdaSlot experiments:
```bash
1. Open `AdaSlot.ipynb` in Jupyter Lab
2. Run the setup cell (clones the original repo and installs its dependencies)
3. Execute data download cells
4. Run training and evaluation cells
```
## Contributing
We welcome contributions at any level. To add a new reproduction or improve existing ones:

**Fork & Branch:** Fork this repository and create a feature branch.

**Add Your Reproduction:** Follow the Adding a New Reproduction guidelines.

**Document Thoroughly:** Ensure your notebook includes context, code comments, and result comparisons.

**Open a Pull Request:** Describe your changes, link to the paper, and summarize reproduction results.

All contributions should include clear instructions and be tested end-to-end in a fresh environment.

## License
This project is licensed under the MIT License. See the LICENSE file for full details.
Reproduced code relies on third-party repositories and datasets, which maintain their original licenses.

## Contact
**GitHub Issues:** Open issues or discussions in the repository for questions or suggestions.

I appreciate your feedback and contributions to strengthen reproducibility in research!
