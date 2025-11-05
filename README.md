# Hydrologic Routing and Optimization using Genetic Algorithms and Network Flow

This notebook demonstrates the application of hydrologic routing models, specifically the Residual Storage Model (RSM) and the Muskingum Model, coupled with optimization techniques for flood management in a river network.

## Overview

The notebook covers the following key aspects:

1.  **Data Loading and Preprocessing**: Loading and preparing inflow and outflow hydrograph data for calibration and validation.
2.  **Exploratory Data Analysis (EDA)**: Basic analysis of the input data, including plotting hydrographs to understand flow dynamics.
3.  **Hydrologic Routing Models**: Implementation of the Residual Storage Model (RSM) and the Muskingum Model.
4.  **Genetic Algorithm-Based Calibration**: Using a Genetic Algorithm (GA) to calibrate the parameters of the routing models by minimizing the Root Mean Square Error (RMSE).
5.  **Model Validation**: Evaluating the performance of the calibrated models using metrics like RMSE, Nash–Sutcliffe Efficiency (NSE), R², peak flow error, and lag error.
6.  **Visualization and Model Comparison**: Plotting observed vs. simulated hydrographs and storage-outflow loops to visually compare model performance.
7.  **Network Flow Structure**: Building a network representation of a river system with nodes (reservoirs, junctions) and arcs (river reaches).
8.  **Linear Optimization for Network Flow**: Formulating and solving a linear programming problem for optimal flow routing in the network.
9.  **RSM-based Network Optimization**: Integrating the Residual Storage Model into the network optimization framework to enforce hydrologic constraints.
10. **Post-Optimization Analysis**: Analyzing the results of the optimization, including reservoir releases, downstream flows, storage variations, and peak flow reductions.

## Requirements

The notebook requires the following libraries:

-   `numpy`
-   `pandas`
-   `matplotlib`
-   `seaborn`
-   `networkx`
-   `pulp`
-   `pygad`
-   `scipy`
-   `sklearn`

These libraries are installed at the beginning of the notebook using `pip`.

## Data

The notebook uses two CSV files:

-   `wilson_event_calibration.csv`: Data for calibrating the routing models.
-   `wilson_event_validation.csv`: Data for validating the calibrated models.

These files are expected to be in a directory specified by the `DATA_PATH` variable (default: `/content/data/`).

## Usage

1.  Run all cells in the notebook sequentially.
2.  The notebook will perform data loading, preprocessing, model calibration using GA, model validation, visualization, network construction, RSM-based network optimization, and post-optimization analysis.
3.  Outputs, including model performance metrics, plots, and optimization results, will be displayed within the notebook.

## Model Details

### Residual Storage Model (RSM)

A conceptual routing model with parameters `alpha` (storage coefficient) and `TT` (transit time).

### Muskingum Model

A common hydrologic routing model with parameters `K` (storage time constant) and `x` (weighting factor).

### Genetic Algorithm (GA)

Used to find the optimal parameters for the RSM and Muskingum models by minimizing the RMSE between simulated and observed outflows.

### Network Flow Optimization

Formulates a linear programming problem to optimize flow distribution in a river network based on mass balance and flow constraints.

### RSM Network Optimization

Extends the network flow optimization by incorporating the RSM to represent storage-outflow relationships in reservoirs within the optimization framework.

## Results

The notebook outputs include:

-   Performance metrics (RMSE, NSE, R², etc.) for the calibrated and validated models.
-   Plots comparing observed and simulated hydrographs.
-   Storage-outflow loops for both models.
-   Sample reservoir releases and downstream flow peak reductions from the network optimization.

This analysis helps in understanding the effectiveness of the routing models and the impact of the optimization on flood mitigation.
