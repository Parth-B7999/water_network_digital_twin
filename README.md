# Digital Twin for Water Distribution Networks

**Paper:** [Digital twin assisted decision support system for quality regulation and leak localization task in large-scale water distribution networks](paper/Final_manuscript.pdf)  
**Journal:** Digital Chemical Engineering 9 (2023) 100127  
**DOI:** https://doi.org/10.1016/j.dche.2023.100127  
**Authors:** Parth Brahmbhatt, Abhilasha Maheshwari, Ravindra D. Gudi — IIT Bombay

---

## Overview

An EPANET-based Digital Twin (DT) framework for the C-TOWN benchmark water distribution network, supporting two decision-making applications:

1. **Booster Chlorination Optimization** — MLP proxy model + Differential Evolution to keep chlorine residuals in 0.2–4 mg/L across all nodes
2. **Pipe Leak Localization** — Graph Convolutional Network (ChebNet) that classifies the leaking pipe from pressure sensor readings with **94.85% accuracy**

![C-TOWN Network](figures/CTown.png)

## Pipeline (run in order)

```
01 → 02 → 03 → 04 → 05 → 06 → 07
```

| Step | Notebook | Task | Key result |
|------|----------|------|------------|
| 01 | [hydraulic_calibration.ipynb](01_hydraulic_calibration/hydraulic_calibration.ipynb) | DE calibration of roughness C + demand multipliers | Calibrated EPANET model |
| 01 | [hydraulic_calibration_viz.ipynb](01_hydraulic_calibration/hydraulic_calibration_viz.ipynb) | Visualization of calibration results | Est_P/Q/F plots |
| 02 | [data_generation.ipynb](02_data_generation/data_generation.ipynb) | 16-week EPANET simulation → CSV data files | P/Q/F/pattern CSVs |
| 03 | [demand_multiplier_mlp.ipynb](03_demand_multiplier_nn/demand_multiplier_mlp.ipynb) | MLP for demand multiplier prediction | R² = 0.987 |
| 04 | [quality_calibration.ipynb](04_quality_calibration/quality_calibration.ipynb) | DE calibration of wall decay coefficients | R² = 0.896 |
| 05 | [quality_prediction_mlp.ipynb](05_quality_prediction/quality_prediction_mlp.ipynb) | Keras MLP to predict chlorine at all nodes | R² = 0.903 |
| 06 | [booster_chlorination.ipynb](06_booster_chlorination/booster_chlorination.ipynb) | DE optimization of booster dosing rates | Chlorine within 0.2–4 mg/L |
| 07 | [leak_localization_gcn.ipynb](07_leak_localization/leak_localization_gcn.ipynb) | ChebNet GCN for pipe leak classification | 94.85% accuracy (429 pipes) |

## Quick Start

```bash
pip install wntr numpy pandas scipy scikit-learn matplotlib torch torch-geometric torch-scatter torch-sparse keras tensorflow tqdm
```

**Step 1:** Run `02_data_generation/data_generation.ipynb` to generate the large simulation CSV files (not tracked in git — ~130 MB total).

**Step 2:** Run steps 03–07 in order. Each notebook reads data files from its own folder or from `02_data_generation/`.

## Network: C-TOWN

The [C-TOWN benchmark network](https://github.com/scy-phy/ICS-EPANET-Datasets) has:
- 429 pipes, 388 junctions, 7 tanks, 1 reservoir, 11 pumps
- 5 District Metered Areas (DMAs)
- 7 booster chlorination stations

The EPANET `.INP` file is included in each step folder.

## Knowledge Graph

An interactive knowledge graph of the paper's methodology is available in [`graphify-out/graph.html`](graphify-out/graph.html) — open in any browser. Built with [graphify](https://github.com/safishamsi/graphifyy).

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