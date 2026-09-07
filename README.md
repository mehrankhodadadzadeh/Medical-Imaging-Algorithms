# Medical Imaging Algorithms and Simulation

Four hands-on Python implementations covering MRI processing, brain-tumor segmentation, CT image reconstruction, and PET acquisition simulation. The notebooks were completed as part of the Medical Imaging course at the **Electronics and Informatics Department (ETRO), Vrije Universiteit Brussel (VUB)**.

> **Educational and research use only.** These implementations are not clinical software and must not be used for diagnosis, treatment planning, or patient care.

## Projects

| Notebook | Topic | Main methods |
|---|---|---|
| `01_mri_enhancement_and_filtering.ipynb` | MRI enhancement and artifact correction | Contrast stretching, histogram equalization, CLAHE, Gaussian/median/mean filtering, Homomorphic Unsharp Masking |
| `02_brain_tumor_segmentation.ipynb` | Brain-tumor segmentation from FLAIR MRI | Multi-level Otsu thresholding, connected components, region growing, morphology, segmentation metrics |
| `03_ct_image_formation_and_reconstruction.ipynb` | CT image formation and reconstruction | Radon transform, sinograms, forward projection, backprojection, ramp-filtered reconstruction, ring-artifact correction |
| `04_pet_monte_carlo_simulation.ipynb` | PET acquisition simulation | Activity-weighted source sampling, isotropic emission directions, line-of-response intersections, sensitivity estimation, sinogram generation |

## Highlights

- Implemented MRI enhancement and denoising workflows using intensity transformations, local histogram methods, spatial filters, and bias-field correction.
- Segmented a brain tumor from a BraTS-derived FLAIR MRI using classical image-processing methods; morphological post-processing improved the reported Dice score to **0.71**.
- Built custom CT forward- and back-projection implementations, then applied Fourier-domain ramp filtering to reduce reconstruction blur.
- Simulated **100,000 PET emission events** from a 3D activity phantom. Increasing simulated scanner coverage improved sensitivity from **34.37% to 64.09%**.

## Repository structure

```text
.
├── notebooks/
│   ├── 01_mri_enhancement_and_filtering.ipynb
│   ├── 02_brain_tumor_segmentation.ipynb
│   ├── 03_ct_image_formation_and_reconstruction.ipynb
│   └── 04_pet_monte_carlo_simulation.ipynb
├── data/
│   └── README.md
├── requirements.txt
├── .gitignore
└── README.md
```

## Installation

Python 3.9+ is recommended.

```bash
git clone https://github.com/mehrankhodadadzadeh/Medical-Imaging-Algorithms.git
cd Medical-Imaging-Algorithms

python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

Open the relevant notebook from the `notebooks/` folder and run its cells in sequence.

## Data and reproducibility

The source notebooks rely on course-provided image files and phantoms, including `.mha`, `.bin`, and `.npy` files. These datasets are **not included** in this repository to respect distribution restrictions and keep the repository lightweight.

Where a dataset path appears in a notebook, replace it with the path to your authorized local copy. The algorithms, visualizations, and evaluation logic remain available for study and reproduction with equivalent data.

## Technical stack

Python, NumPy, SimpleITK, SciPy, scikit-image, Matplotlib, and Jupyter.

## Notes on the brain-tumor notebook

The tumor-segmentation notebook implements **classical image-processing methods**, not a deep-learning U-Net. Its focus is thresholding, region growing, connected-component analysis, post-processing, and metric-based evaluation using Dice, Jaccard, false-positive/false-negative error, and Hausdorff distance.

## Contact

Mehran Khodadadzadeh — [mehrankhodadadzadeh90@gmail.com](mailto:mehrankhodadadzadeh90@gmail.com)
