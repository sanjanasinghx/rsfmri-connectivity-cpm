# Resting-State Functional Connectivity and Connectome-Based Predictive Modeling

Resting-state fMRI connectivity analysis: parcellation, Fisher-z connectivity matrices, an ANOVA across age groups, and out-of-sample prediction of executive function from functional edges.

Coursework for CG 614 Human Brain Mapping, IIT Gandhinagar, 2026. [Report (PDF)](./report.pdf) | [Academia.edu](https://telaviv.academia.edu/SanjanaSingh)

## What's in the notebook

Three analyses on two open datasets:

1. Parcellation and connectivity matrix: one HCP subject's resting-state fMRI parcellated with the Schaefer 400-parcel / Yeo 17-network atlas, giving a 400 x 400 Fisher z connectivity matrix.
2. Lifespan connectivity: AABC Release 2 covariance matrices (Glasser HCP-MMP1, 379 ROIs) for 1,390 subjects in four age bins (36-50, 50-65, 65-80, 80+), with an edge-wise one-way ANOVA and Bonferroni correction.
3. Connectome-based predictive modeling (CPM): LOOCV prediction of the NIH Toolbox Flanker score (n = 1,379) from resting-state edges (positive, negative and combined networks).

## Results

- The single-subject matrix shows clear block-diagonal Yeo network structure (visual mean *z* = 0.535; DMN *z* = 0.226).
- 77,931 of 143,641 edges (54.25%) show a significant age effect after Bonferroni correction. Mean covariance drops steadily from 141.4 (age 36-50) to 54.1 (80+).
- Positive-network CPM: *r* = 0.080, *p* = 0.003. The prediction is small but significant, probably limited by ceiling effects in the Flanker scores.

Libraries: `nibabel`, `numpy`, `scipy.stats`, `statsmodels`, `matplotlib`, `seaborn`, `pandas`.

## Data

| Source | Citation |
| --- | --- |
| HCP S1200 resting-state fMRI | Van Essen et al., 2013, *NeuroImage* |
| AABC Release 2 connectivity matrices | balsa.wustl.edu |
| Schaefer 400-parcel / Yeo 17-network atlas | Schaefer et al., 2018, *Cerebral Cortex* |
| Glasser HCP-MMP1 atlas | Glasser et al., 2016, *Nature* |

## Running it

```bash
git clone https://github.com/sanjanasinghx/rsfmri-connectivity-cpm.git
cd rsfmri-connectivity-cpm
pip install -r requirements.txt
jupyter notebook rsfmri_connectivity_cpm.ipynb
```

The data has to be downloaded separately from HCP (db.humanconnectome.org, needs a DUA) and BALSA.

## Related repos

- [`eeg-erp-auditory-oddball`](https://github.com/sanjanasinghx/eeg-erp-auditory-oddball): single-subject EEG/ERP pipeline in MNE-Python
- [`infant-eeg-spectral-fooof`](https://github.com/sanjanasinghx/infant-eeg-spectral-fooof): infant EEG spectral and aperiodic analysis

## License

Code: MIT. Report text: CC BY 4.0. The datasets keep their original licenses. If you use this, please cite the datasets above and link this repo.
