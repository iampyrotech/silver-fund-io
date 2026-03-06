# silver-fund-io
Institutional Ownership Signal Research

## Overview

This repository contains research exploring **institutional ownership (IO) as an equity signal**.  
The goal is to evaluate whether the level of institutional ownership in a stock predicts future returns.

Two different data sources are used to construct the signal:

1. **Capital IQ institutional ownership data**
2. **Raw EDGAR 13F filings**

The project compares signals built from these datasets and evaluates their predictive power using portfolio sorts, information coefficients, and factor regressions.

---

## Repository Structure

This repository currently contains three main notebooks.

### 1. `io.ipynb` — Capital IQ Institutional Ownership

This notebook builds the original institutional ownership signal using **Capital IQ data**.

Key steps include:

- Cleaning Capital IQ ownership data
- Linking securities to **Compustat identifiers (GVKEY)**
- Merging ownership data with market and return data
- Constructing institutional ownership percentages
- Running portfolio sorts and signal evaluation

This notebook represents the **first version of the IO signal** using vendor-provided ownership data.

---

### 2. `edgar_io.ipynb` — EDGAR 13F Institutional Ownership

This notebook constructs the same signal using **raw EDGAR 13F filings**.

The workflow includes:

- Parsing hedge fund holdings from 13F filings
- Aggregating holdings across institutions
- Computing institutional ownership percentages
- Merging with CRSP-style return data
- Creating the institutional ownership signal
- Evaluating performance via quintile portfolios and factor regressions

This approach recreates institutional ownership **directly from regulatory filings** rather than vendor datasets.

---

### 3. `getdata2.ipynb` — EDGAR Data Extraction

This notebook pulls **13F filings directly from the EDGAR API**.

It performs:

- API requests to EDGAR
- Downloading institutional filing data
- Parsing holdings information
- Exporting cleaned filing data to CSV

This notebook serves as the **data ingestion pipeline** for the EDGAR-based signal.

---

## Research Objective

The core research question is:

> Do stocks with higher institutional ownership generate different future returns than stocks with lower institutional ownership?

The analysis evaluates the signal using:

- **Quintile portfolio sorts**
- **Long–short spread returns**
- **Information coefficients (IC)**
- **Fama–French factor regressions**

---

## Future Work

Planned extensions include:

- Expanding the EDGAR dataset to additional time periods
- Evaluating **changes in institutional ownership** as a signal
- Sector-neutral and factor-neutral signal testing
- Portfolio optimization and backtesting using the Silver Fund research framework

---

## Authors

Chase Nielsen
Ethan Evans
BYU Silver Fund – Quantitative Research
