# CropSmart: Predictive Modeling for Agricultural Resilience

**NAFSI 2026 Data Challenge, Track 1**

**Team:** Binxin Gao (bgao666@umd.edu), University of Maryland

## Overview

This repository contains the analysis notebook and report for the NAFSI 2026 CropSmart Data Challenge. The project uses three operational geospatial datasets (CDL, NDVI, SMAP) to analyze vegetation dynamics, detect crop rotation patterns, quantify soil moisture anomalies, and build a crop type classification model for the U.S. Corn Belt (Iowa).

## Tasks

1. **NDVI Time Series Analysis**: Compares seasonal NDVI phenological curves for corn vs. soybean in Iowa (2020).
2. **Crop Rotation Pattern Identification**: Classifies 10-year crop rotation patterns (2013-2022) in central Iowa into five categories.
3. **Soil Moisture Anomaly Calculation**: Analyzes the 2019 Midwest flood using SMAP soil moisture anomalies and assesses agricultural impact.
4. **Crop Mapping Prediction Model**: Trains a Random Forest classifier to predict 2023 crop types using historical CDL features.

## Repository Structure

```
.
├── CropSmart_NAFSI_Track1.ipynb   # Main analysis notebook (all 4 tasks)
├── requirements.txt                # Python dependencies
├── README.md                       # This file
└── ../data/raw/                    # Cached geospatial data (downloaded by notebook)
```

## Setup & Reproduction

### Prerequisites

- Python 3.10+
- Internet connection (for downloading data from CropSmart WPS/WCS endpoints)

### Installation

```bash
pip install -r requirements.txt
```

### Running the Notebook

```bash
jupyter notebook CropSmart_NAFSI_Track1.ipynb
```

Run all cells from top to bottom. The notebook will:
1. Download CDL, NDVI, and SMAP data from CropSmart endpoints (cached locally after first run)
2. Execute all four analysis tasks
3. Generate figures and metrics
4. Display report answers

**Note:** The first run requires significant data downloads (~2 GB for CDL, ~100 MB for NDVI, ~10 MB for SMAP). Subsequent runs use cached data and complete much faster.

## Data Sources

| Dataset | Resolution | Period | Source |
|---------|-----------|--------|--------|
| Cropland Data Layer (CDL) | 30m | 2008-2025 | USDA NASS via CropSmart WPS |
| Vegetation Index (NDVI) | 250m | 2000-2026 | MODIS via CropSmart WCS |
| Soil Moisture (SMAP) | 9km | 2015-2025 | NASA SMAP via CropSmart WPS |

All data is accessed programmatically through the CropSmart Digital Twin platform at https://cloud.csiss.gmu.edu/CropSmart.

