[![Developed For: ACS](https://img.shields.io/badge/developed%20for-ACS-orange.svg?style=flat)](http://www.stsci.edu/hst/acs) [![Powered By: STScI](https://img.shields.io/badge/powered%20by-STScI-blue.svg?colorA=707170&colorB=3e8ddd&style=flat)](http://www.stsci.edu/) 

![ACS logo](acs_logo.png)

# acs-notebook

This repository contains Jupyter notebooks to demonstrate how to calibrate and analyze data from the *Hubble Space Telescope* (*HST*) Advanced Camera for Surveys (ACS). Users are advised to visit the [ACS website](http://www.stsci.edu/hst/acs), [Instrument Handbook](http://www.stsci.edu/hst/acs/documents/handbooks/current/cover.html), and [Data Handbook](http://www.stsci.edu/hst/acs/documents/handbooks/currentDHB/acs_cover.html) for more information about the current status of ACS, instrument specifications, and data analysis.

Users who need help transitioning from IRAF/PyRAF to Python should see the [stak-notebooks](https://github.com/spacetelescope/stak-notebooks) repository. 

If you have questions about HST data analysis, calibration software, instrument capabilities, and/or the methods discussed in this repository, please visit the [HST Help Desk](http://hsthelp.stsci.edu). Through the help desk portal, you can explore the HST Knowledge Base and request additional help from experts.

# Getting Started

To download the notebooks in this repository, simply open a terminal, go to the directory where you would like the notebooks to be, and type
```
git clone https://github.com/spacetelescope/acs-notebook.git
```
which will create a new acs-notebook/ directory containing the contents of this repository.
 
___Warning:___ Before running these examples, you must install or update to the latest version of [stenv](https://stenv.readthedocs.io/en/latest/).

Jupyter Notebooks allow code to be packaged with formatted text to create illustrative examples. Users who are unfamiliar with Jupyter Notebooks should also see the [short guide](https://jupyter-notebook-beginner-guide.readthedocs.io/en/latest/) for how to use these tools.

# Contents

## Simple Example Notebooks

* **acs_subarrays**: Instructions for how to use the `acstools.acs_destripe_plus` module to calibrate, de-stripe, and correct ACS subarray observations for charge transfer efficiency (CTE). Also included are instructions for updating the `OSCNTAB` reference file to subtract the bias level from the prescan columns in user-defined subarray observations.

* **acs_pixel_area_maps**: This notebook shows how to use Python to create pixel area maps (PAMs) to account for the effects of geometric distortion in distorted images. This enables users to perform photometry on distorted images.

* **acs_polarization_tools**: ACS/WFC offers two sets of polarizers, UV and visible, for imaging polarimetry and imaging spectropolarimetry. This notebook provides guidance on using the `acstools.polarization_tools` module to retrieve polarization calibration coefficients and calculate polarization properties of a source.

## Complex Workflow Notebooks

* **acs_reduction**: This worked example demonstrates how to use the CALACS pipeline to re-process raw ACS data retrieved from MAST. Users are shown how to update reference files in the image headers, retrieve reference files from the Calibration Reference Data System (CRDS), and how to toggle steps in the calibration pipeline (e.g., CTE correction).

* **acs_cte_forward_model** The capability to simulate the readout of an ACS image at a given epoch is a feature of CALACS that does not run during standard calibration. This example demonstrates how to take a pristine image, or one corrected for time-dependent CTE loss, and simulate CTE losses for an arbitrary observation date using `acstools.acscteforwardmodel`.

* **acs_saturation_trails** The ACS/WFC CCDs remain linear beyond the full-well saturation, which allows users the opportunity to perform photometry on saturated stars. This notebook demonstrates the methods and caveats when performing saturated star photometry.

* **acs_sbc_dark_analysis**: The ACS Solar Blind Channel (SBC) has nominally negligible dark current. However, the temperature of the SBC detector increases steadily over time while it is in use, and the dark current is proportional to temperature. At temperatures above 25 ºC, the dark current is no longer negligible and must be subracted. This workflow demonstrates how to account for dark current in ACS/SBC observations.

* **acs_findsat_mrt_example.ipynb**: ACS/WFC imaging data is often affected by contamination by artificial satellites, compromising science data. The `acstools.findsat_mrt` module can be used to identify satellite trails and create masks to reject affected pixels from further analysis.

## Contributing

If you have feedback concerning our documentation or examples presented here on GitHub, please open an [issue](https://github.com/spacetelescope/acs-notebook/issues). For feedback concerning content exclusively from the ACS website, Instrument Handbook, or Data Handbook, or for questions about ACS in general, please contact the ACS Branch at STScI via the [Hubble Space Telescope Help Desk portal](http://hsthelp.stsci.edu). 
