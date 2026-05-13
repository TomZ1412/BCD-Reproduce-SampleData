# BCD-Reproduce-SampleData

### 1. PREP / PyPREP

**Paper:**  
Bigdely-Shamlo et al., 2015, *The PREP pipeline: standardized preprocessing for large-scale EEG analysis*  
https://www.frontiersin.org/journals/neuroinformatics/articles/10.3389/fninf.2015.00016/full

**Code:**  
PyPREP: https://github.com/sappelhoff/pyprep/tree/main/pyprep

**Notes:**  
PREP is a standardized EEG preprocessing pipeline. Its noisy-channel detection module includes multiple criteria, such as flat channels, abnormal amplitudes, high-frequency noise, low correlation with other channels, and RANSAC-based detection.

---

### 2. LOF-based Bad-Channel Detection

**Paper:**  
Kumaravel et al., 2022, *Adaptable and Robust EEG Bad Channel Detection Using Local Outlier Factor (LOF)*  
https://www.mdpi.com/1424-8220/22/19/7314

**Code:**  
MATLAB implementation: https://github.com/vpKumaravel/detectbadchannelLOF  
Python implementation: `mne.preprocessing.find_bad_channels_lof`

**Notes:**  
This method treats each channel as a sample in a feature space and applies Local Outlier Factor (LOF) to identify channels that behave differently from the majority of channels.

---

### 3. Autoreject / RANSAC

**Paper:**  
Jas et al., 2017, *Autoreject: Automated Artifact Rejection for MEG and EEG Data*  
https://pubmed.ncbi.nlm.nih.gov/28645840/

**Documentation:**  
`autoreject.Ransac`: https://autoreject.github.io/stable/generated/autoreject.Ransac.html

**Code:**  
Python implementation: `autoreject.Ransac`

**Notes:**  
The RANSAC method detects bad sensors based on spatial predictability. A channel is marked as bad if its signal cannot be reliably reconstructed from other channels. Although Autoreject is a broader artifact-rejection framework, the `Ransac` module is specifically useful for bad-sensor detection.
