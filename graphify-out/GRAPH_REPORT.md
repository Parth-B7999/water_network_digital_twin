# Graph Report - /Users/parthbrahmbhatt/Library/CloudStorage/OneDrive-UW-Madison/IIT Bombay/Paper/Final_manuscript.pdf  (2026-05-08)

## Corpus Check
- 1 files · ~8,000 words
- Verdict: corpus is large enough that graph structure adds value.

## Summary
- 90 nodes · 99 edges · 8 communities detected
- Extraction: 94% EXTRACTED · 6% INFERRED · 0% AMBIGUOUS · INFERRED: 6 edges (avg confidence: 0.85)
- Token cost: 0 input · 0 output

## Community Hubs (Navigation)
- [[_COMMUNITY_GCN Architecture|GCN Architecture]]
- [[_COMMUNITY_Booster Chlorination & Quality Control|Booster Chlorination & Quality Control]]
- [[_COMMUNITY_Prior Work & Literature|Prior Work & Literature]]
- [[_COMMUNITY_DT Calibration Pipeline|DT Calibration Pipeline]]
- [[_COMMUNITY_Leak Localization|Leak Localization]]
- [[_COMMUNITY_EPANET Simulation|EPANET Simulation]]
- [[_COMMUNITY_C-TOWN Case Study|C-TOWN Case Study]]
- [[_COMMUNITY_SCADA & Data Infrastructure|SCADA & Data Infrastructure]]

## God Nodes (most connected - your core abstractions)
1. `Graph Convolutional Network (GCN) / ChebNet` - 18 edges
2. `Digital Twin (DT)` - 16 edges
3. `Pipe Leak Localization` - 12 edges
4. `Booster Chlorination Dosage Regulation` - 10 edges
5. `Hydraulic Model Calibration` - 9 edges
6. `Multilayer Perceptron (MLP) Proxy Neural Network` - 9 edges
7. `C-TOWN Benchmark Network` - 5 edges
8. `EPANET Simulation Software` - 4 edges
9. `Differential Evolution (DE) Optimization Algorithm` - 4 edges
10. `Water Quality Model Calibration` - 4 edges

## Surprising Connections (you probably didn't know these)
- `Differential Evolution (DE) Optimization Algorithm` --conceptually_related_to--> `Booster Chlorination Dosage Regulation`  [INFERRED]
  Final_manuscript.pdf → Final_manuscript.pdf  _Bridges community 3 → community 1_
- `Multilayer Perceptron (MLP) Proxy Neural Network` --semantically_similar_to--> `Graph Convolutional Network (GCN) / ChebNet`  [INFERRED] [semantically similar]
  Final_manuscript.pdf → Final_manuscript.pdf  _Bridges community 1 → community 0_
- `Pressure Sensor Data` --shares_data_with--> `Multilayer Perceptron (MLP) Proxy Neural Network`  [INFERRED]
  Final_manuscript.pdf → Final_manuscript.pdf  _Bridges community 1 → community 4_
- `Extended Period Simulation (EPS)` --shares_data_with--> `Multilayer Perceptron (MLP) Proxy Neural Network`  [INFERRED]
  Final_manuscript.pdf → Final_manuscript.pdf  _Bridges community 1 → community 5_
- `Extended Period Simulation (EPS)` --shares_data_with--> `Graph Convolutional Network (GCN) / ChebNet`  [INFERRED]
  Final_manuscript.pdf → Final_manuscript.pdf  _Bridges community 0 → community 5_

## Hyperedges (group relationships)
- **DT Calibration Pipeline (DE + Hydraulic + Quality)** — final_manuscript_de_algorithm, final_manuscript_hydraulic_calibration, final_manuscript_quality_calibration [EXTRACTED 1.00]
- **Booster Chlorine Regulation Pipeline (MLP + DE + EPS)** — final_manuscript_mlp, final_manuscript_de_algorithm, final_manuscript_booster_chlorination [EXTRACTED 1.00]
- **GCN Leak Localization Pipeline (Adjacency + Features + ChebNet)** — final_manuscript_adjacency_matrix, final_manuscript_feature_matrix, final_manuscript_chebnet_architecture, final_manuscript_leak_localization [EXTRACTED 1.00]

## Communities

### Community 0 - "GCN Architecture"
Cohesion: 0.12
Nodes (18): Adjacency Matrix, Batch Training (GCN), Categorical Cross Entropy Loss, ChebNet Architecture (K=2, 3 GCN Layers + 2 Dense Layers), Chebyshev Polynomial Approximation, Defferrard et al. 2016 (Convolutional Neural Networks on Graphs / ChebNet), Node Feature Matrix, Fey and Lenssen 2019 (PyTorch Geometric) (+10 more)

### Community 1 - "Booster Chlorination & Quality Control"
Cohesion: 0.13
Nodes (16): Adam Optimizer, Booster Chlorination Dosage Regulation, Chlorine Concentration Constraint (0.2–4 mg/L), Chlorine Concentration Prediction, Disinfection By-Products (DBP), Keras Library, Multilayer Perceptron (MLP) Proxy Neural Network, Mean Squared Error (MSE) Loss (+8 more)

### Community 2 - "Prior Work & Literature"
Cohesion: 0.14
Nodes (14): Andronie et al. 2021 (Sustainable Digital Twin Review), Berglund et al. 2023 (Digital Twins for Water Distribution Systems), Bonilla et al. 2022 (Graph Neural Network DT for WDN), Conejos Fuertes et al. 2020 (WDN Digital Twin), Cyber-Physical System (CPS), Decision Support System, Digital Twin (DT), GitHub Repository (SCEPTER-Lab EPANET-based Digital Twin) (+6 more)

### Community 3 - "DT Calibration Pipeline"
Cohesion: 0.15
Nodes (13): Differential Evolution (DE) Optimization Algorithm, Demand Multiplier / Demand Pattern, First-Order Chlorine Decay Kinetics, Hazen-Williams Roughness Coefficient, Hydraulic Model Calibration, Meirelles et al. 2017 (Calibration Model for WDN), MSE / MAE / MAPE Performance Metrics, Ormsbee and Lingireddy 1997 (Calibrating Hydraulic Network Models) (+5 more)

### Community 4 - "Leak Localization"
Cohesion: 0.18
Nodes (11): Classification Accuracy Metric, Caputo and Pelagagge 2003 (Neural Networks for Pipe Monitoring), Da Silva and Mashford 2009 (Computer Aided Leak Location), Pipe Leak Localization, Mounce and Machell 2007 (Burst Detection with ANNs), One-Hot Encoding, Pressure-Flow Deviation Method (Leak Detection), Pressure Sensor Data (+3 more)

### Community 5 - "EPANET Simulation"
Cohesion: 0.29
Nodes (7): Crowl and Louvar 1990 (Chemical Process Safety / Leak Demand Equation), EPANET Simulation Software, Extended Period Simulation (EPS), Klise et al. 2020 (WNTR User Manual), Leak Demand Model (Crowl-Louvar Equation), Rossman et al. 2020 (EPANET 2.2 User Manual), WNTR (Water Network Tool for Resilience)

### Community 6 - "C-TOWN Case Study"
Cohesion: 0.29
Nodes (7): Abokifa et al. 2019 (Booster Station Optimization), Booster Station (Chlorine Injection Point), C-TOWN Benchmark Network, District Metered Area (DMA), Dominic Boccelli et al. 1998 (Optimal Scheduling of Booster Disinfection), Ostfeld et al. 2011 (Battle of Water Calibration Networks / C-TOWN), Tsiami and Makropoulos 2021 (Cyber-Physical Attack Detection in WDS)

### Community 7 - "SCADA & Data Infrastructure"
Cohesion: 0.5
Nodes (4): Advanced Metering Infrastructure (AMI), Data Lake, Programmable Logic Controllers (PLC), SCADA System

## Knowledge Gaps
- **61 isolated node(s):** `Water Distribution Network (WDN)`, `Hazen-Williams Roughness Coefficient`, `Demand Multiplier / Demand Pattern`, `Wall Decay Coefficient`, `District Metered Area (DMA)` (+56 more)
  These have ≤1 connection - possible missing edges or undocumented components.

## Suggested Questions
_Questions this graph is uniquely positioned to answer:_

- **Why does `Digital Twin (DT)` connect `Prior Work & Literature` to `Booster Chlorination & Quality Control`, `DT Calibration Pipeline`, `Leak Localization`, `EPANET Simulation`, `C-TOWN Case Study`, `SCADA & Data Infrastructure`?**
  _High betweenness centrality (0.609) - this node is a cross-community bridge._
- **Why does `Graph Convolutional Network (GCN) / ChebNet` connect `GCN Architecture` to `Booster Chlorination & Quality Control`, `Leak Localization`, `EPANET Simulation`?**
  _High betweenness centrality (0.357) - this node is a cross-community bridge._
- **Why does `Pipe Leak Localization` connect `Leak Localization` to `GCN Architecture`, `Prior Work & Literature`?**
  _High betweenness centrality (0.356) - this node is a cross-community bridge._
- **Are the 2 inferred relationships involving `Graph Convolutional Network (GCN) / ChebNet` (e.g. with `Multilayer Perceptron (MLP) Proxy Neural Network` and `Extended Period Simulation (EPS)`) actually correct?**
  _`Graph Convolutional Network (GCN) / ChebNet` has 2 INFERRED edges - model-reasoned connections that need verification._
- **Are the 2 inferred relationships involving `Booster Chlorination Dosage Regulation` (e.g. with `Differential Evolution (DE) Optimization Algorithm` and `Proxy Model (Data-Driven Surrogate)`) actually correct?**
  _`Booster Chlorination Dosage Regulation` has 2 INFERRED edges - model-reasoned connections that need verification._
- **What connects `Water Distribution Network (WDN)`, `Hazen-Williams Roughness Coefficient`, `Demand Multiplier / Demand Pattern` to the rest of the system?**
  _61 weakly-connected nodes found - possible documentation gaps or missing edges._
- **Should `GCN Architecture` be split into smaller, more focused modules?**
  _Cohesion score 0.12 - nodes in this community are weakly interconnected._