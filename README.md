# Cells classification to cancer and healthy ones by their SERS spectra

## Contents
1. [Project topic description](Project-topic-description)
2. [Data description](#Data-description)
3. [Project implementation](#Project-implementation)

## Project topic description

A problem of early-stage cancer detection is currently one of hot topics in early diagnostics. Raman spectroscopy is one of methods of noninvasive analysis of substance contents, inter alia cell analysis. However, Raman signal is usually too low, therefore special enhancing gold or silver nanoparticles may be used that dramatically enhance the signal; such approach is called SERS, Surface-Enhanced Raman Spectroscopy. The obtained spectra represent data with thousand of dimensions (features) that are difficult to be classified by eye due to complex contents of cells. Therefore, methods of data science are used to classify cancer and healthy cells. There is a bunch of papers researching this topic, but too few of them provide data in open access. 

On the paper [Erzina et al](https://doi.org/10.1016/j.snb.2020.127660) , the authors use:
* a convolutional neural network to differentiate a set of cell types;
* cell types include both known cell cultures grown in vitro and cells derived from human;
* spectra of cells with 3 types of enhancing gold nanoparticles (AuNPs): with (COOH)2, COOH and NH2 residues, providing catching cells by different molecules on their surface.

I used the data from this article aiming:
* to focus on just 2 cell types, that are derived from human: heallthy and cancer skin fibroblasts, that makes more sense. Therefore, the task from a multiclass classification becomes a binary classification;
* to explore opportunities to build a much simple model, without neural networks.

## Data description
The data are provided [on Kaggle](https://www.kaggle.com/datasets/andriitrelin/cells-raman-spectra). Tere's the number of spectra provided:
<img src=https://user-images.githubusercontent.com/47527688/221403742-d615b0b8-cc35-4af6-b02b-9ce1f18d3077.png width=50% height=50%>

Each spectra contains 2090 dimensions (features), corresponding to Raman shifts from 100 to 4178 cm-1 (units in which spectral positions are measured):
![image](https://user-images.githubusercontent.com/47527688/221404049-d7196010-8685-417f-8b65-81cf5de4f34e.png)

## Project implementation
Exactly the chapters you'll find in the Jupyter Notebook simple_models_sequenced.ipynb .
Some plots there are implemented in plotly libraries. To watch th file with them, please use this link to nbviewer: https://nbviewer.org/github/Asya23/Raman-SERS-cells-classification/blob/master/simple_models_sequenced.ipynb

* Meet the data
* EDA
  * Statistical testing: normality
  * Savitzky-Golay filter
  * Data test for normality for savgol-filtered data
  * Working with peaks (features) of interest
  * Dividing to train_val and test subsets
  * Correlation matrix
  * Dimensionality reduction: PCA
* Machine Learning Modeling
  * a) Use all 3 spectra types (all 3 types of AuNPs)
    * Logistic Regression
    * Cross Validation
    * Feature importances
  * b) Use only COOH spectra
    * Divide to Train, Validation, (Train+Validation) and Test populations
    * PCA
    * Logistic Regression
    * Cross Validation
    * Feature importances
