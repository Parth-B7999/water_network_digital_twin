# Digital Twin for Water Distribution Networks

**Paper:** Digital twin assisted decision support system for quality regulation and leak localization task in large-scale water distribution networks  
**Journal:** Digital Chemical Engineering 9 (2023) 100127  
**DOI:** https://doi.org/10.1016/j.dche.2023.100127  
**Authors:** Parth Brahmbhatt, Abhilasha Maheshwari, Ravindra D. Gudi — IIT Bombay

---

## Overview

An EPANET-based Digital Twin (DT) framework for the C-TOWN benchmark water distribution network, supporting two decision-making applications:

1. **Booster Chlorination Optimization** — MLP proxy model + Differential Evolution to keep chlorine residuals in 0.2–4 mg/L across all nodes
2. **Pipe Leak Localization** — Graph Convolutional Network (ChebNet) that classifies the leaking pipe from pressure sensor readings with **94.85% accuracy**

## Pipeline (run in order)

```
01 → 02 → 03 → 04 → 05 → 06 → 07
```

| Step | Notebook | Task | Key result |
|------|----------|------|------------|
| 01 | [hydraulic_calibration.ipynb](01_hydraulic_calibration/hydraulic_calibration.ipynb) | DE calibration of roughness C + demand multipliers | R²=0.9927 (pressure) |
| 01 | [hydraulic_calibration_viz.ipynb](01_hydraulic_calibration/hydraulic_calibration_viz.ipynb) | Calibration result visualization | Scatter plots |
| 02 | [data_generation.ipynb](02_data_generation/data_generation.ipynb) | 32-week EPANET EPS → CSV data files | 5376 samples |
| 03 | [demand_multiplier_mlp.ipynb](03_demand_multiplier_nn/demand_multiplier_mlp.ipynb) | MLP for demand multiplier prediction | R²=0.987 |
| 04 | [quality_calibration.ipynb](04_quality_calibration/quality_calibration.ipynb) | DE calibration of wall decay coefficients | R²=0.9574 (concentration) |
| 05 | [quality_prediction_mlp.ipynb](05_quality_prediction/quality_prediction_mlp.ipynb) | Keras MLP: 97→256→256→256→351 | R²=0.91 overall |
| 06 | [booster_chlorination.ipynb](06_booster_chlorination/booster_chlorination.ipynb) | DE optimization of 7 booster dosing rates | Chlorine within 0.2–4 mg/L |
| 07 | [leak_localization_gcn.ipynb](07_leak_localization/leak_localization_gcn.ipynb) | ChebNet GCN: 429-pipe classification | 94.85% accuracy |

## Quick Start

```bash
pip install wntr numpy pandas scipy scikit-learn matplotlib torch torch-geometric torch-scatter torch-sparse keras tensorflow tqdm
```

**Step 1:** Run `02_data_generation/data_generation.ipynb` — generates the large simulation CSV files (gitignored, ~130 MB total: `P_quality_gt1.csv`, `Q_quality_gt1.csv`, `F_quality_gt1.csv`, `patt_quality_gt1.csv`, `dossing_gt1.csv`).

**Step 2:** Copy or symlink generated CSVs to each step folder that needs them (03–07), then run notebooks in order.

## Network: C-TOWN

388 junctions · 429 pipes · 7 tanks · 1 reservoir · 11 pumps · 5 DMAs · 45 pressure/flow/quality sensors · 7 booster stations (R1, J301, J287, J238, J178, J142, J131)

## Key Hyperparameters

**DE Calibration (step 01 & 04):** `popsize=10, strategy='best1bin', maxiter=10, tol=1e-4, mutation=0.5`  
**Booster DE (step 06):** `popsize=10, strategy='randtobest1', maxiter=60, tol=1e-7, mutation=0.5`  
**MLP (step 05):** 3 hidden layers × 256 neurons, Adam lr=0.001, epochs=100, MSE loss, 80/20 split  
**ChebNet (step 07):** K=2, layers 17→64→64→256, global max+mean pool → 512 → 429, Adam lr=0.01, 3000 epochs

## Knowledge Graph

An interactive knowledge graph of the paper's methodology is in [`graphify-out/graph.html`](graphify-out/graph.html) — open in any browser.

## Citation

```bibtex
@article{brahmbhatt2023digital,
  title={Digital twin assisted decision support system for quality regulation and leak localization task in large-scale water distribution networks},
  author={Brahmbhatt, Parth and Maheshwari, Abhilasha and Gudi, Ravindra D.},
  journal={Digital Chemical Engineering},
  volume={9},
  pages={100127},
  year={2023},
  publisher={Elsevier},
  doi={10.1016/j.dche.2023.100127}
}
```
