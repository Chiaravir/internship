Author: Chiara Virzi  
Date: []  

# Introduction
## Young Stellar Objects (YSOs)
Young Stellar Objects (YSOs) are stars in the early stages of stellar evolution. They can be identified by their variability. In this report, we focus on the spectral analysis of the Hα band, which allows us to study the activity of the accretion disk. YSOs are crucial for understanding star formation processes and the evolution of planetary systems.

## Young Stellar Object Science
YSOs are classified based on their luminosity and spectral characteristics:
- **Class I**: High luminosity, prominent accretion disk, and often detectable jets and outflows.
- **Class II**: More evolved with a well-defined protoplanetary disk, also known as Classical T-Tauri stars. Some material is still accreting onto the star.
- **Class III**: Nearing the end of their formation phase with little to no accretion disk remaining. These are the transition objects between pre-main sequence and main-sequence stars.

## Accretion Bursts and How to Detect Them
Accretion bursts are sudden increases in luminosity due to material falling onto a young star from its disk. These bursts release energy primarily in the form of thermal radiation and are most often detected in infrared wavelengths. However, the *u* and *g* bands are particularly useful for detecting accretion-related variability, as accretion hotspots emit at higher temperatures. Conversely, variability in the *i* band can indicate dips caused by occultations from circumstellar disk material. Such 'dippers' are associated with dust extinction, which is more pronounced at longer wavelengths.

## Spectral Energy Distribution (SED) and Spectroscopy
The Spectral Energy Distribution (SED) represents the energy emitted by an astronomical object across various wavelengths. For YSOs, the SED is a crucial diagnostic tool that provides insight into their class, mass, and accretion processes. Spectroscopy enables the identification of emission and absorption features, revealing details about the object's physical properties and environment.

# Methods
## Brokers
Data brokers play a key role in modern astronomical research by streamlining the acquisition, filtering, and distribution of massive datasets from wide-field surveys. They enable real-time aggregation and cross-matching of alerts from multiple instruments and wavelengths, helping to promptly identify significant events like accretion bursts or spectral variations. This facilitates timely follow-up observations and collaboration among researchers, enhancing our understanding of stellar evolution.

## Light Curves
A light curve is a plot of an object's brightness over time. By studying the shape and variations in a light curve, astronomers can infer:
- **Periodicity**: Indicating the presence of accretion or disk dynamics.
- **Transients**: Sudden changes in brightness, such as accretion bursts.
Spectroscopy allows for the detailed study of spectral lines in light curves, helping to identify elements in the star’s atmosphere or accretion disk.

# Identifying the Hα Band
```python
import numpy as np
import matplotlib.pyplot as plt

# Sample wavelength and flux data
wavelength = np.linspace(6500, 6600, 100)
flux = np.exp(-0.5 * ((wavelength - 6563)/2)**2) + np.random.normal(0, 0.05, wavelength.shape)

# Hα band window
window_min = 6530.0
window_max = 6590.0
mask_window = (wavelength >= window_min) & (wavelength <= window_max)
w_line = wavelength[mask_window]
f_line = flux[mask_window]
```

# Results
In this study, we analyzed two cases of YSOs:
- **Best Case (Object 1)**: The sky-subtracted and non-sky-subtracted spectra are nearly identical, confirming the reliability of the results.
- **Worst Case (Object 2)**: Nebular noise dominates the signal, making the data unreliable. The width of the Hα line did not exceed the recommended 3 Å threshold from Bonito et al. (2020).

# Discussion and Conclusion
By analyzing the sky-subtracted and non-sky-subtracted spectra, we found that in Object 2, the nebular noise overwhelmed the signal, rendering the data unreliable. Additionally, the width of the Hα line was below the expected threshold, indicating a less active accretion phase.

For Object 1, the good agreement between the spectra confirmed the validity of the results. The width of the Hα line exceeded 14 Å, further supporting its classification as an actively accreting YSO.

This study demonstrates the effectiveness of spectral analysis in characterizing YSOs and highlights the importance of careful data reduction techniques.

## Cross-Sectional Skills
This project helped develop skills in astronomical data analysis, handling FITS files, and visualizing results through graphical representations.

