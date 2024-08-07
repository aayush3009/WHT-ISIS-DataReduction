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

### Notes

- The code was originally based on scripts by Steve Crawford, with modifications for specific reduction steps like wavelength calibration and flat processing.
- Update the paths and object names as per your observation details.

## Acknowledgments

The starting point for this code was the helpful scripts of Steve Crawford, with various modifications for specific processing steps.

---

For detailed documentation and further instructions, refer to the comments within the Jupyter Notebook.

## Changelog:
7/12/2019 - Added wavelength calibration and 1D spectrum extraction
