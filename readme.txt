Article title: 
Stage-resolved malaria detection using a fingerprint-guided dual-band metamaterial optical biosensor
Authors: 
Meraj Ahmed1,2, Yaser Mike Banad1, Sarah Sharif1,2,*

1 School of Electrical and Computer Engineering, University of Oklahoma
2 Center for Quantum Research and Technology, University of Oklahoma
* Corresponding Author, email: s.sh@ou.edu






Python Code and CSV Datasets for Fingerprint-Guided Dual-Band Metamaterial Biosensor Analysis

OVERVIEW
This folder contains the Python analysis code and CSV datasets used to generate all numerical results, figures, and performance metrics reported in the manuscript titled:

“Stage-resolved malaria detection using a fingerprint-guided dual-band metamaterial optical biosensor”

The released materials support full post-processing reproducibility of the absorption spectra, resonance shifts, sensitivity, quality factor (Q), and figure of merit (FOM) presented in the paper. The analysis can be reproduced without access to any commercial electromagnetic simulation software.

WHAT IS INCLUDED

Python analysis notebook (python_code.ipynb)

CSV files containing wavelength-dependent absorption data

Datasets covering:

Healthy and malaria-infected red blood cell stages

Incident-angle analysis under TE and TM polarization

Surface roughness analysis of the gold resonator

Training data used in the optimization workflow

No CST project files are included.
CST Studio Suite is not required to run the Python code.

FOLDER STRUCTURE

python_code.ipynb

Absorption Dataset of Malaria Stages.csv

Incident Angle Analysis in TE Mode.csv

Incident Angle Analysis in TM Mode.csv

Surface Roughness of Gold.csv

Training Dataset for Optimization.csv

README.txt

DESCRIPTION OF CSV DATASETS

Absorption Dataset of Malaria Stages
This file contains absorption spectra for healthy red blood cells and malaria-infected cells at the ring, trophozoite, and schizont stages. These data are used for stage-resolved detection analysis and to generate the absorption spectra reported in the main manuscript.

Incident Angle Analysis (TE and TM Modes)
These datasets contain absorption responses under varying incident angles for transverse electric (TE) and transverse magnetic (TM) polarization modes. They support the angular stability analysis discussed in the manuscript and supplementary material.

Surface Roughness of Gold
This dataset describes how absorption changes as a function of the RMS surface roughness of the gold resonator. It is used to evaluate fabrication feasibility and surface morphology effects.

Training Dataset for Optimization
This dataset contains geometry–response data used to train surrogate models and support the hybrid optimization framework described in the paper.

All datasets use wavelength in nanometers (nm) and normalized absorption values between 0 and 1.

PYTHON CODE DESCRIPTION
The Python notebook performs the following tasks:

Loads CSV datasets directly

Identifies resonance peaks near 380 nm and 432 nm

Extracts full width at half maximum (FWHM)

Computes sensitivity, quality factor (Q), and figure of merit (FOM)

Generates publication-quality figures consistent with the manuscript

All equations and performance definitions follow those reported in the manuscript and its Supplementary Information.

SOFTWARE REQUIREMENTS
The code was tested using:

Python version 3.9 or higher

Required Python packages:
numpy
pandas
matplotlib
scipy

Required packages can be installed using:
pip install numpy pandas matplotlib scipy

HOW TO RUN

Ensure all CSV files are located in the same directory as the Python notebook or in the specified data path

Open the notebook using:
jupyter notebook python_code.ipynb

Run all cells sequentially

Figures will be displayed inline and may be saved if enabled in the notebook

IMPORTANT NOTE ON CST SOFTWARE
CST Studio Suite was used only to generate the original electromagnetic simulation data. The Python code provided here does not access, require, or interface with CST in any way. All post-processing and figure generation are performed exclusively using the released CSV files.

RELATION TO THE MANUSCRIPT
The provided code and datasets reproduce results reported in:

Optimized absorption spectra

Stage-resolved malaria detection analysis

Sensitivity, Q-factor, and FOM calculations

Angular stability analysis

Fabrication feasibility and tolerance studies

These materials are provided to support transparency and reproducibility of the reported results.

LICENSE AND USAGE
The data and code are released for academic and non-commercial research use only. If these materials are used in derivative work, please cite the associated manuscript.
