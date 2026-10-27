
# Optical Detectors: HST & Sentinel Analysis

## Overview

This repository contains two data analysis workflows focused on **optical detector calibration** and **Earth observation**:

1. **HST Calibration Assignment**: a calibration workflow for Hubble Space Telescope (HST) datasets, including bias, dark, and flat-field corrections.
2. **Sentinel-2 / Hunga Tonga Analysis**: a study of land area and vegetation changes using Sentinel-2 satellite imagery and Google Earth imagery.


## Repository Structure

| Folder / File | Description |
| --- | --- |
| `hst-calibration/` | Raw calibration files for HST datasets `ubai2505m`, `ubai2507m`, and `ubai2508m`. |
| `hst-processed/` | Processed, science-ready FITS files used for comparison and destination for calibrated data |
| `sentinel-data/` | Sentinel-2 and Google Earth imagery used for land and vegetation analysis. |
| `hst-assignment.ipynb` | Jupyter notebook implementing the HST calibration pipeline. |
| `sentinel-assignment.ipynb` | Jupyter notebook analysing Hunga Tonga land area and vegetation changes. |

##  HST Calibration Pipeline

The HST workflow includes:

1. **Masking** using `MASKFILE`.
2. **Bias correction** using `BLEVFILE` and `BIASFILE`.
3. **Dark subtraction** using the exposure time and `DARKFILE`.
4. **Flat-field correction** using `FLATFILE`.
5. **Photometric calibration** using `PHOTTAB` parameters, including `PHOTFLAM`, `PHOTZPT`, and `ZP_CORR`.

### Results

Each calibrated dataset (`ubai2505m`, `ubai2507m`, and `ubai2508m`) is compared with its science-ready reference image.

The relative differences in the mean and standard deviation are **below 1%**, indicating close agreement with the reference images.

## Sentinel-2 / Hunga Tonga Analysis

This project explores **volcanic island evolution and vegetation recovery** using:

- **Google Earth imagery (2014–2023)** for land area estimation.
- **Sentinel-2 imagery** for vegetation mapping using the Normalised Difference Vegetation Index (NDVI).

### Analysis Workflow

1. **Land detection** through brightness thresholding.
2. **NDVI calculation** using near-infrared and red band files.
3. **Vegetation area estimation** using pixel-to-ground area transforms.
4. **Validation** by comparing custom NDVI results with pipeline-generated NDVI outputs.

### Results

The analysis indicates vegetation recovery during **2017–2019**, with the estimated vegetated area increasing steadily over that period.
