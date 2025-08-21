
# Project: Yield Curve Modeling — Nelson-Siegel vs. Svensson

## Overview

This repo accompanies a class presentation comparing yield-curve specifications with a focus on the Nelson–Siegel (NS) family and the extended Svensson model. We study how the decay parameter λ\lambda**λ** affects stability and fit quality, and we evaluate performance during an inverted curve regime.

## Data

* Treasury yield curve snapshots (multiple maturities) used to calibrate term-structure models and assess goodness-of-fit across time.
* “Glimpse on Data” shows the input cross-section across maturities and dates (see “Best plots” below).

## Methods

* **Nelson–Siegel (NS)** with two treatments of the decay parameter λ\lambda**λ**:
  * **Free λ\lambda**λ**:** re-estimated each period → potentially better in-sample fit, but unstable dynamics.
  * **Fixed λ\lambda**λ**:** held constant (chosen at ~0.47) → more stable factor loadings, slightly worse fit.
* **Svensson (NS-S)** : adds a second hump term (two decay parameters) to improve flexibility and fit stability.

## Key Findings

* **Free *λ*** : fits can swing and become hard to predict out-of-sample.
* **Fixed λ≈0.47**  : produces **stable** factors, trading a bit of fit quality for robustness.
* **Svensson model** : delivers  **both stability and strong fit** , capturing curve shapes (including humps) better than NS.
* The framework accurately represents an **inverted yield curve** episode and its cross-maturity behavior.

## What’s in this repo

* Calibration code for NS / Svensson
* Utilities to compare fit metrics (RMSE across maturities) and visualize factor stability
* Reproducible plots for data snapshots, parameter paths, and fitted vs. actual yields
