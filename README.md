# Stellar Data Analysis: Star Detection, Surface Density & Transit Analysis

This repository contains two Python/Jupyter notebook projects focused on **astronomical data analysis**, combining image-based stellar population analysis with time-series analysis of stellar light curves.

The notebooks demonstrate a practical workflow for working with astronomical observations: data preprocessing, feature extraction, statistical analysis, visualization, and physical model fitting.

## Projects

### 1. NGC 104 — Star Detection and Surface Density Analysis

**Notebook:** `surface_density_analysis.ipynb`

This project analyses an astronomical image of the globular cluster **NGC 104 (47 Tucanae)**. The analysis focuses on detecting stars in the image and studying their spatial distribution.

Main steps include:

- Astronomical image preprocessing and inspection
- Star detection using `DAOStarFinder`
- Aperture photometry of detected sources
- Gaussian fitting to stellar profiles
- Construction of radial stellar-density profiles
- Analysis of the spatial distribution of stars
- Fitting a **King model** to the observed surface-density profile
- Estimation of cluster structural properties such as the core radius

**Data-analysis skills demonstrated:**

- Processing scientific imaging data
- Feature/source detection
- Data cleaning and transformation
- Statistical modelling
- Parameter estimation
- Exploratory data visualization
- Model fitting and interpretation

---

### 2. TESS Light-Curve Analysis

**Notebook:** `light_curve_analysis.ipynb`

This project analyses **TESS stellar light-curve data** to identify and model a transit signal.

The analysis includes:

- Loading and cleaning observational time-series data
- Handling missing values
- Separating time and flux measurements
- Visualizing raw and cleaned light curves
- Applying moving-window smoothing
- Identifying the transit region
- Modelling the expected stellar flux during a planetary transit
- Fitting the transit model to the observed light curve using `scipy.optimize.curve_fit`

The project demonstrates a typical astronomical time-series workflow, from raw observational data to a fitted physical model.

---


## Technologies

- Python
- Jupyter Notebook
- NumPy
- SciPy
- Matplotlib
- Astropy
- Photutils

## Key Methods

### Astronomical Image Analysis

The NGC 104 notebook uses astronomical image-processing techniques to identify stellar sources and quantify their spatial distribution. Detected stars are measured photometrically and used to construct a radial surface-density profile, which is then compared with a King-model description of the cluster.

### Time-Series Analysis

The TESS notebook works with stellar flux measurements as a function of time. The data are cleaned and smoothed before a transit model is fitted to the observed signal using numerical optimization.

## Skills Demonstrated

**Data Analysis**
- Data cleaning and preprocessing
- Exploratory data analysis
- Feature extraction
- Time-series analysis
- Statistical analysis
- Numerical optimization
- Model fitting

**Scientific Computing**
- NumPy
- SciPy
- Astropy
- Photutils
- Matplotlib
- Jupyter

**Astronomical Data**
- FITS/image data
- Stellar source detection
- Aperture photometry
- Surface-density analysis
- TESS light curves
- Transit modelling

