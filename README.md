# NGC 104 Star Detection and Surface Density Analysis

## Overview

This project analyzes an astronomical image of the globular cluster **NGC 104** using Python. The analysis focuses on detecting stars in the image, determining their spatial distribution, calculating the stellar surface density as a function of radius, and fitting a King model to the resulting density profile.

The project was developed as part of an astronomy data-analysis assignment and demonstrates the use of Python for astronomical image processing, source detection, statistical analysis, and scientific modelling.

## Objectives

The analysis consists of the following steps:

1. Display the NGC 104 image in pixel coordinates.
2. Check for World Coordinate System (WCS) information in the FITS header.
3. Transform the image to sky coordinates using Right Ascension (RA) and Declination (Dec).
4. Process the image by handling invalid/NaN values and subtracting the background.
5. Detect stars using `DAOStarFinder`.
6. Perform aperture photometry on the detected sources.
7. Estimate the centre of the globular cluster using Gaussian fits to the spatial distribution of detected stars.
8. Calculate the radial surface density of stars.
9. Fit a King model to the surface-density profile.
10. Estimate the core radius of the cluster from the fitted model.

## Methods

### Image and coordinate analysis

The input data is a FITS image:

```text
ic2r02050_drz.fits
```

The image is examined in pixel coordinates and its FITS header is checked for WCS information. When WCS information is available, the image is displayed using sky coordinates (RA and Dec).

### Image preprocessing

Invalid values in the image are masked and the median background is subtracted. Remaining invalid values are replaced with zeros before source detection.

### Star detection

Stars are detected using `DAOStarFinder` from the `photutils` package. The detection threshold is based on an estimate of the image noise using the median absolute deviation.

Aperture photometry is then performed around the detected sources.

### Cluster-centre estimation

The x and y positions of the detected stars are histogrammed separately. Gaussian functions are fitted to these distributions using `scipy.optimize.curve_fit` to estimate the centre of the cluster.

### Surface-density profile

The radial distance of each detected star from the estimated cluster centre is calculated.

The stars are divided into radial annuli, and the stellar surface density is calculated as:

```text
surface density = number of stars / annulus area
```

Uncertainties are estimated from the number of detected stars in each annulus.

### King-model fitting

The resulting surface-density profile is fitted with a King model:

```text
n(r) = n_theta [1 + (r/a)²]^(-γ/2)
```

The fitted parameters are then used to estimate the core radius of the cluster.

## Technologies and Libraries

* Python
* NumPy
* Matplotlib
* SciPy
* Astropy
* Photutils
* Jupyter Notebook


## Results

The notebook produces visualizations of:

* NGC 104 in pixel coordinates
* NGC 104 in sky coordinates
* detected stars
* x and y distributions of detected stars with Gaussian fits
* stellar surface density as a function of radius
* King-model fit to the surface-density profile

The final analysis provides an estimate of the core radius of NGC 104 based on the fitted King model.

## Data

The analysis uses the FITS image:

```text
ic2r02050_drz.fits
```

The original astronomical data file is not included in this repository due to its size. Please refer to the original data source for the dataset and its usage conditions.


