# RHESSys_SA_with_in-build_parameters

     Sensitivity Analysis for RHESSys Model Parameters

        Author: Tejendra Kandel
     Affiliation: University of Virginia

Overview

This repository contains the workflow and Python code used to perform sensitivity analysis for streamflow simulation within the RHESSys ecohydrological model. The purpose of this analysis is to identify which model parameters exert the greatest influence on watershed hydrologic responses, particularly streamflow.

The analysis uses multiple performance metrics including:

Nash–Sutcliffe Efficiency (NSE)

Log-transformed NSE (logNSE) – provides sensitivity to low flows

Coefficient of Determination (R²)

Root Mean Square Error (RMSE)

These metrics provide a quantitative basis for evaluating which parameters most strongly control hydrological behavior within the modeled watershed.

Repository Structure
.
│-- SA_MORRIS_with_RHESSys_inbuild_parameters_final.ipynb  # Main sensitivity analysis notebook
│-- Parameters_range_values_with_inbuild_parameters.csv     # Parameter list and ranges for sampling
│-- README.md                                               # Documentation (this file)


Methodology

Parameter Range Definition
Parameter bounds were defined based on RHESSys documentation and previous studies.

Sampling Strategy
Morris Sampling (a global sensitivity screening method) was implemented to explore parameter space efficiently.

Model Execution
For each sampled parameter set, RHESSys was executed to generate daily streamflow outputs.

Performance Metrics
Observed vs. simulated streamflow was evaluated using:

NSE → Sensitivity to overall hydrograph shape

logNSE → Sensitivity to low flows (baseflow conditions)

r² → General goodness of fit

RMSE → Error magnitude

Parameter Sensitivity Evaluation
Morris sensitivity indices (μ*, σ) were calculated:

μ* = overall influence magnitude

σ = parameter interaction / nonlinearity

Key Output Interpretation
Metric	Meaning	Interpretation
μ*	Mean Absolute Effect	Larger μ* → More sensitivity
σ	Standard Deviation of Effects	Larger σ → Parameter interacts with others / has nonlinear behavior

Parameters with:

High μ* and Low σ → Strong, stable influence

High μ* and High σ → Important but highly interactive

Low μ* → Minimal effect on streamflow
