# COVID-19-Lung-CT-Scan-Detection
Repository for storing source code for reproducing and extending "Deep Learning Enables Accurate Diagnosis of Novel Coronavirus (COVID-19) With CT Images" research paper: https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9376253 [1]. Contains a Jupyter notebook, a model checkpoint file, and the training, validation, and testing data. The Jupyter notebook contains the data preprocessing, exploratory data visualization (EDA), model setup, training, and evaluation code with outputs.

## Dataset Download Instructions
1. Navigate to the `local_traniner` folder, which stores all relevant lung image data.
2. The training, evaluation, and testing data for all hospital data is located under the `input` folder. This folder contains `train`, `val` `folder`, `test`, and `testNewHospital` folders. The first four folders contain the original data in the paper's GitHub repository [1], and the the `testNewHospital` folder contains our curated data for Sao Paulo hospital patients [2].

## References
[1] Song, Ying et al. "Deep Learning Enables Accurate Diagnosis of Novel Coronavirus (COVID-19) With
CT Images." IEEE/ACM transactions on computational biology and bioinformatics vol. 18,6 (2021):
2775-2780. doi:10.1109/TCBB.2021.3065361

[2] Soares, Eduardo, Angelov, Plamen, Biaso, Sarah, Higa Froes, Michele, and Kanda Abe, Daniel. "SARS-CoV-2 CT-scan dataset: A large dataset of real patients CT scans for SARS-CoV-2 identification." medRxiv (2020). doi: https://doi.org/10.1101/2020.04.24.20078584.
