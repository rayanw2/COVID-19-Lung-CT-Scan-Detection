# COVID-19-Lung-CT-Scan-Detection
Repository for storing source code for reproducing and extending "Deep Learning Enables Accurate Diagnosis of Novel Coronavirus (COVID-19) With CT Images" research paper: https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9376253 [1]. Contains a Jupyter notebook, a model checkpoint file, and the training, validation, and testing data. The Jupyter notebook contains the data preprocessing, exploratory data visualization (EDA), model setup, training, and evaluation code with outputs.

## Dataset Download Instructions
1. Navigate to the `local_traniner` folder, which stores all relevant lung image data.
2. The training, evaluation, and testing data for all hospital data is located under the `input` folder. This folder contains `train`, `val`, `test`, and `testNewHospital` folders. The first three folders contain the original data in the paper's GitHub repository [1], and the the `testNewHospital` folder contains our curated data for Sao Paulo hospital patients [2].

## Code Execution Instructions
Download the Jypyter notebook file (.ipynb) in the root directory of this repository. Open the notebook in an IDE of your choice. To run the code, simply run the cells in the notebook. The Jupyter notebook will access the training, validation, and testing data from a Google Drive folder, so there is nothing that needs to be modified unless you want to integrate new data.

The training functions, for the different experiments performed, in the Jupyter notebook currently uses pre-trained model checkpoints. These model checkpoints are pulled in from a remote location. This is done by setting the `should_skip_train` and `should_skip_val` flags to `True`. This will cause only the testing script to be executed. If you want to train the existing model with a different hyperparameter configuration or experiment with a new model altogether, you should set to `should_skip_train` and `should_skip_val` flags to `False`.

Note that the `input` and `model` folders of this repository are solely for download purposes and are not used anywhere within the notebook.

## References
[1] Song, Ying et al. "Deep Learning Enables Accurate Diagnosis of Novel Coronavirus (COVID-19) With
CT Images." IEEE/ACM transactions on computational biology and bioinformatics vol. 18,6 (2021):
2775-2780. doi:10.1109/TCBB.2021.3065361

[2] Soares, Eduardo, Angelov, Plamen, Biaso, Sarah, Higa Froes, Michele, and Kanda Abe, Daniel. "SARS-CoV-2 CT-scan dataset: A large dataset of real patients CT scans for SARS-CoV-2 identification." medRxiv (2020). doi: https://doi.org/10.1101/2020.04.24.20078584.
