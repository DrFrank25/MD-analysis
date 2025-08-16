# Molecular Dynamics Analysis Toolkit

This repository contains Python scripts designed for the analysis and visualization of **Molecular Dynamics (MD)** simulation data, with a focus on trajectory descriptors frequently used in structural biology and computational chemistry.  

The scripts support input files in **GROMACS `.xvg` format** and produce high-quality publication-ready plots.

---

## Features

### 1. **Root Mean Square Deviation (RMSD)**
- Reads RMSD `.xvg` files from GROMACS.
- Applies **Savitzky–Golay smoothing** or running average filters to reduce noise.
- Plots both raw and smoothed curves for multiple independent runs (replicates).
- Calculates:
  - Per-run **mean** and **standard deviation**.  
  - **Global average and standard deviation** across all runs.  
- Saves figures in **high resolution (1200 dpi)** for publication.

### 2. **Root Mean Square Fluctuation (RMSF)**
- Reads RMSF `.xvg` data.
- Plots residue-wise fluctuations.
- Highlights flexible vs. stable regions of the protein.

### 3. **Radius of Gyration (Rg)**
- Processes `.xvg` files from `gmx gyrate`.
- Displays the time evolution of the protein’s compactness.  
- Calculates mean and standard deviation across replicates.

### 4. **Solvent Accessible Surface Area (SASA)**
- Reads `.xvg` data from `gmx sasa`.
- Plots SASA curves with optional smoothing.
- Supports averaging across multiple simulation runs.

---

## Output

- **Plots**: High-quality, publication-ready PNG figures.  
- **Statistics**: Mean and standard deviation printed for each run and globally across all runs.  
- **Legends**: Customizable, with run labels (e.g., *Run 1*, *Run 2*, *Run 3*).  
- **Export**: Figures can be downloaded directly in Google Colab or saved locally.

---

## Requirements

- Python 3.8+
- NumPy
- Pandas
- Matplotlib
- SciPy
- Google Colab (for interactive use)

---

## Usage

1. Upload `.xvg` files (RMSD, RMSF, Rg, SASA) into the Colab notebook.  
2. Run the corresponding script.  
3. Figures and statistics will be generated automatically.  
4. Download the figures using:

```python
from google.colab import files
files.download("rmsd_NMDA.png")
