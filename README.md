# Dual-Fingerprint-Channel Metamaterial Absorber for Stage-Resolved Optical Detection of Malaria-Infected Red Blood Cells

## Authors

- **Meraj Ahmed**
- **Yaser Mike Banad**
- **Sarah Sharif** *(Corresponding Author: s.sh@ou.edu)*

**Affiliation:** Intelligent Neuromorphic and Quantum Understanding for Innovative Research and Engineering (**INQUIRE**) Laboratory, University of Oklahoma

---

## Project Overview

This repository contains the simulation model, optimization notebook, and source datasets associated with the manuscript **“Dual-Fingerprint-Channel Metamaterial Absorber for Stage-Resolved Optical Detection of Malaria-Infected Red Blood Cells.”**

The project presents a fingerprint-guided Au/SiO₂/Cu metal–insulator–metal (**MIM**) metamaterial absorber biosensor for detecting malaria-infected red blood cells (**RBCs**) and resolving parasite progression across healthy, ring-stage, trophozoite-stage, and schizont-stage RBC conditions. The absorber targets two validated malaria-related biomolecular fingerprint channels at **380 nm** and **432 nm**, associated with NADH- and hemoglobin/heme-related optical responses, respectively.

The released files support the main numerical workflow, including full-wave CST simulation, Random Forest and Genetic Algorithm optimization, stage-wise absorption analysis, angular response, finite-array scalability, substrate/backplane variation, and surface-roughness analysis.

---

## Repository Contents

The repository release contains the following files.

| File | Type | Description |
|---|---|---|
| `FDTD File.cst` | CST Studio Suite model | Full-wave electromagnetic simulation model of the proposed MIM absorber. |
| `python code.ipynb` | Jupyter Notebook | Python notebook for the Random Forest surrogate and Genetic Algorithm optimization workflow. |
| `Training Dataset for Optimization.csv` | CSV dataset | Training data used for surrogate-model-based optimization of the absorber response. |
| `Absorption Dataset of Malaria Stages.csv` | CSV dataset | Wavelength-dependent absorption spectra for healthy and malaria-infected RBC stages. |
| `Incident Angle Analysis in TE Mode.csv` | CSV dataset | Absorption spectra under different oblique incident angles for TE polarization. |
| `Incident Angle Analysis in TM Mode.csv` | CSV dataset | Absorption spectra under different oblique incident angles for TM polarization. |
| `Scaling Dataset.csv` | CSV dataset | Absorption spectra for the periodic reference and scaled finite-array configurations. |
| `Substrate Variation Dataset.csv` | CSV dataset | Absorption spectra for different bottom backplane/substrate materials, including Al, Cr, Cu, and Au. |
| `Surface Roughness of Gold.csv` | CSV dataset | Absorption spectra for different RMS roughness values of the top Au resonator. |

---

## Main Dataset Descriptions

### 1. Optimization dataset

`Training Dataset for Optimization.csv` contains the FDTD-generated training data used to build the surrogate model. The notebook uses this dataset to train a Random Forest regressor, screen candidate geometries, and perform Genetic Algorithm optimization for high absorption near the two fingerprint channels.

### 2. Malaria-stage absorption dataset

`Absorption Dataset of Malaria Stages.csv` contains wavelength-dependent absorption data for the RBC conditions studied in the manuscript. This dataset supports reproduction of the stage-wise spectral response and extraction of resonance position, absorbance, FWHM, quality factor, and sensitivity.

### 3. Incident-angle datasets

`Incident Angle Analysis in TE Mode.csv` and `Incident Angle Analysis in TM Mode.csv` contain absorption spectra as a function of incident angle. These datasets support the angular-stability analysis of the 380 nm and 432 nm fingerprint channels.

### 4. Scaling dataset

`Scaling Dataset.csv` contains absorption spectra for the periodic reference and finite-array configurations. This dataset supports the finite-array scalability analysis and the evaluation of resonance stability as the array size increases.

### 5. Substrate/backplane dataset

`Substrate Variation Dataset.csv` contains absorption spectra obtained by replacing the bottom Cu backplane with other practical materials. This dataset supports the substrate/backplane-related optical-loss analysis.

### 6. Gold surface-roughness dataset

`Surface Roughness of Gold.csv` contains absorption spectra for different RMS roughness values of the top Au layer. This dataset supports the fabrication-feasibility and surface-roughness tolerance analysis.

---

## Optimization Notebook

The file `python code.ipynb` provides the Python workflow for surrogate-assisted optimization. The notebook includes:

1. loading and preprocessing the FDTD-generated training dataset;
2. training a Random Forest regression model;
3. evaluating surrogate prediction accuracy;
4. screening candidate geometries;
5. applying Genetic Algorithm search; and
6. visualizing predicted and optimized absorption responses.

The notebook requires Python 3.x and common scientific-computing libraries.

Recommended Python packages:

```text
numpy
pandas
matplotlib
scikit-learn
scipy
deap
```

---

## CST Simulation File

The file `FDTD File.cst` contains the CST Studio Suite model used for the full-wave electromagnetic simulations. The model can be used to reproduce or extend the absorber analysis by modifying structural parameters, analyte refractive index, incident angle, or material properties.

The optimized geometry used in the manuscript is:

| Parameter | Symbol | Value |
|---|---:|---:|
| Unit-cell period | `d` | 300 nm |
| Cu backplane thickness | `t1` | 200 nm |
| SiO₂ spacer thickness | `t2` | 404.10 nm |
| Au resonator height | `t3` | 80 nm |
| RBC/analyte layer thickness | `t4` | 80 nm |
| Au ring radius | `r1` | 130 nm |
| Au ring width | `p` | 30 nm |

---

## Reproducing the Main Analyses

### Stage-resolved absorption response

Use `Absorption Dataset of Malaria Stages.csv` to reproduce the stage-wise absorption spectra and extract peak positions near the 380 nm and 432 nm fingerprint channels.

### Optimization analysis

Open `python code.ipynb`, load `Training Dataset for Optimization.csv`, and run the notebook cells to reproduce the Random Forest surrogate and Genetic Algorithm optimization workflow.

### Angular-stability analysis

Use `Incident Angle Analysis in TE Mode.csv` and `Incident Angle Analysis in TM Mode.csv` to reproduce the TE/TM angular-response spectra.

### Finite-array scalability analysis

Use `Scaling Dataset.csv` to compare the periodic reference response with scaled finite-array configurations.

### Substrate/backplane analysis

Use `Substrate Variation Dataset.csv` to compare the spectral response for different backplane materials and evaluate substrate-related optical-loss behavior.

### Surface-roughness analysis

Use `Surface Roughness of Gold.csv` to reproduce the roughness-dependent absorption spectra and evaluate fabrication-related optical degradation.

---

## Important Notes

- This repository supports a **simulation-based study**. No fabricated prototype or clinical dataset is included.
- The released CSV files are provided as source data for figure reproduction and independent post-processing.
- The CST model may produce slightly different numerical values depending on CST version, mesh settings, solver configuration, and local machine precision.
- The optimization notebook is intended to reproduce the surrogate-assisted design workflow and may require path updates if file names or directory structure are changed.
- Stage-resolved classification results in the manuscript represent **simulation-based numerical separability under assumed readout noise**, not experimental clinical diagnostic accuracy.
- The middle off-target resonance observed in the absorption spectrum is treated as a physical auxiliary MIM resonance and is not used as a malaria sensing channel because it is not aligned with the validated NADH or hemoglobin/heme fingerprint windows.

---

## Suggested Repository Structure

```text
.
├── FDTD File.cst
├── python code.ipynb
├── Training Dataset for Optimization.csv
├── Absorption Dataset of Malaria Stages.csv
├── Incident Angle Analysis in TE Mode.csv
├── Incident Angle Analysis in TM Mode.csv
├── Scaling Dataset.csv
├── Substrate Variation Dataset.csv
├── Surface Roughness of Gold.csv
└── README.md
```

---

## License

This project is released under the **MIT License**, unless otherwise specified in the repository. You are free to use, modify, and distribute the code and datasets with appropriate attribution.

---

## Citation

If you use this repository, please cite the associated manuscript:

> Meraj Ahmed, Yaser Mike Banad, and Sarah Sharif, “Dual-Fingerprint-Channel Metamaterial Absorber for Stage-Resolved Optical Detection of Malaria-Infected Red Blood Cells,” submitted.

A full citation and DOI will be added after publication.

---

## Contact

For questions, collaboration, or technical inquiries, please contact:

**Sarah Sharif**  
School of Electrical and Computer Engineering, University of Oklahoma  
INQUIRE Laboratory  
Email: **s.sh@ou.edu**
