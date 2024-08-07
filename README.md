# WHT ISIS Long-slit Spectroscopy Reduction

This Jupyter Notebook provides code for reducing long-slit spectroscopic data obtained with the William Herschel Telescope (WHT) using the Intermediate dispersion Spectrograph and Imaging System (ISIS).

## Getting Started

### Prerequisites

Ensure you have the following Python packages installed:
- numpy
- multiprocessing
- astropy
- scipy
- matplotlib
- ccdproc

### Usage

1. **Sync Observation Data:**
   Use `rsync` to copy observation data from the `whtobs` computer:
   ```bash
   $ rsync -av whtobs@taurus.ing.iac.es:/obsdata/whta/20170624/ 20170624/
   ```
   Replace `20170624/` with the relevant observation night.

2. **Run the Notebook:**
   Open the Jupyter Notebook and execute the cells step-by-step to reduce the spectroscopic data.

3. **Outputs:**
   The notebook will generate master bias and flat frames, and process the object frames to create reduced science images.

Sure, I'll provide the updated `README.md` file with a detailed explanation of the Jupyter Notebook for WHT ISIS wavelength calibration without the detailed code explanation.

---

## WHT ISIS Wavelength Calibration

The following section describes a Jupyter Notebook that complements the basic WHT ISIS long slit data reduction scripts. This code can either be implemented separately or added to the basic reduction scripts to create a full pipeline.

### Overview

The Jupyter Notebook provides detailed steps for the wavelength calibration of the WHT ISIS long slit data for both the blue and red arms. It includes the following steps:

1. **Importing Libraries and Setting Up Environment:**
    - The notebook starts by importing necessary libraries such as `numpy`, `astropy`, `mpdaf`, and `matplotlib`.
    - It also defines several helper functions for fitting and calibration purposes.

2. **Blue Arm Calibration:**
    - **Data Loading:** Loads the target data and the relevant arc file for the blue arm.
    - **Normalization:** Normalizes the arc spectrum for easier identification of features.
    - **Feature Identification:** Identifies key features in the arc spectrum and matches them with known wavelengths from the WHT arcs PDF.
    - **Wavelength Solution:** Fits a wavelength solution using the identified features and updates the header of the FITS file with this calibration.

3. **Red Arm Calibration:**
    - Follows similar steps as the blue arm calibration, including data loading, normalization, feature identification, and wavelength solution fitting.

4. **Extraction of 1D Spectrum:**
    - After calibrating the 2D spectra for both arms, the notebook extracts 1D spectra using a defined aperture.
    - The extracted 1D spectra are then saved as FITS files.

### Usage

To use the Jupyter Notebook for wavelength calibration, follow these steps:

1. Ensure all necessary libraries (`numpy`, `astropy`, `mpdaf`, `matplotlib`) are installed in your Python environment.
2. Open the Jupyter Notebook in your preferred environment (e.g., JupyterLab, Jupyter Notebook).
3. Follow the instructions within the notebook to load your data, perform wavelength calibration, and extract 1D spectra.

### Notes

- The code was originally based on scripts by Steve Crawford, with modifications for specific reduction steps like wavelength calibration and flat processing.
- Update the paths and object names as per your observation details.
- The notebook is designed to work with data obtained from the William Herschel Telescope (WHT) using the ISIS spectrograph.
- Ensure that you have access to the arc calibration files and the WHT arcs PDF for accurate wavelength calibration.
- The notebook is flexible and can be adapted for different datasets or calibration requirements.

### Conclusion

This Jupyter Notebook serves as a detailed guide for performing wavelength calibration on WHT ISIS long slit data. By following the steps outlined, users can achieve accurate wavelength solutions for both the blue and red arms and extract high-quality 1D spectra for their astronomical analysis.


## Acknowledgments

The starting point for this code was the helpful scripts of Steve Crawford, with various modifications for specific processing steps.

---

For detailed documentation and further instructions, refer to the comments within the Jupyter Notebook.

## Changelog:
7/12/2019 - Added wavelength calibration and 1D spectrum extraction
