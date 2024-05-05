# COVID-19-Lung-CT-Scan-Detection
Repository for storing source code for reproducing and extending "Deep Learning Enables Accurate Diagnosis of Novel Coronavirus (COVID-19) With CT Images" research paper: https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9376253 [1]. Contains a Jupyter notebook, a model checkpoint file, and the training, validation, and testing data. The Jupyter notebook contains the data preprocessing, exploratory data visualization (EDA), model setup, training, and evaluation code with outputs.

## Specification of Dependencies
Run the command `pip install -r requirements.txt` to download all the necessary dependencies as specified in the `requirements.txt` file. If you are running this on Colab (recommended), then you can skip this step.

## Dataset Download Instructions
1. Navigate to the `local_traniner` folder, which stores all relevant lung image data.
2. The training, evaluation, and testing data for all hospital data is located under the `input` folder. This folder contains `train`, `val`, `test`, `testNewHospital`,  `testNewHospitalSmall`, `testSmall`, and `trainProcessedSegmented` folders. The first three folders contain the original data in the paper's GitHub repository [1], the  `testNewHospital` folder contains our curated data for Sao Paulo hospital patients [2], the `testNewHospitalSmall` and `testSmall` folders contain condensed versions of the data for faster evaluation for demonstration purposes (100 lung CT scan images per class), and `trainProcessedSegmented` contains the segmented lung images (the cropped lower lung region).

## Code Execution Instructions
If you are running the Jupyter notebook on Google Colab (recommended), download just the Juputer notebook file (the .ipynb file in the root directory of this repository) and view it in Colab. You do not need to download the other repository contents since the notebook will download them from Google Drive folders. The Google Drive folders store the same training, validation, and testing data, along with model checkpoint files you see in the `input` and `model` directories of this repository, so there is nothing that needs to be modified unless you want to integrate new data.

On the other hand, if you would like to run this code locally, you will need to download the entire repository. Open the notebook in an IDE of your choice. First, remove the `local_traniner` prefix from all paths that access data. Then, you can run the cells in the notebook. Do not run the cells that download Google Drive data with `gdown`.

## Training and Evaluation Code
The training functions, for the different experiments performed, in the Jupyter notebook currently uses pre-trained model checkpoints. This is done by setting the `should_skip_train` and `should_skip_val` flags to `True`. This will cause only the testing script to be executed, and will evaluate the pre-trained models (provided by the model checkpoints) on the test set. If you want to train the existing model with a different hyperparameter configuration or experiment with a new model altogether, you should set to `should_skip_train` and `should_skip_val` flags to `False`.

## Pretrained Models
You can find all the pretrained model checkpoint files under the `model` directory of this repository.

## Results
The following are results of 6 different deep learning models on the test set (test set images located under `input/test` folder).

| Model       | Accuracy | AUC   | Precision | Recall |
|-------------|----------|-------|-----------|--------|
| DRENet with ResNet-50 Base *(reported in paper)*     | **0.86**     | **0.95**  | 0.79      | 0.96   |
| DRENet with ResNet-50 Base *(reproduced result)*   | 0.83     | 0.93  | 0.82      | **1.00**   |
| DRENet with ResNet-101 Base *(custom experiment)*  | 0.69     | 0.71  | 0.62      | **1.00**   |
| InceptionNet *(custom experiment)* | 0.86     | 0.87  | **0.88**      | 0.86   |
| AlexNet *(custom experiment)*     | 0.50     | 0.50  | 0.25      | 0.50   |
| ResNet-50 *(reported in paper)*      | **0.86**    | 0.90  | 0.81      | 0.93   |
| VGG-16 *(reported in paper)*      | 0.84     | 0.91  | 0.80      | 0.89   |
| DenseNet *(reported in paper)*   | 0.82     | 0.87  | 0.76      | 0.93   |


## References
[1] Song, Ying et al. "Deep Learning Enables Accurate Diagnosis of Novel Coronavirus (COVID-19) With
CT Images." IEEE/ACM transactions on computational biology and bioinformatics vol. 18,6 (2021):
2775-2780. doi:10.1109/TCBB.2021.3065361

[2] Soares, Eduardo, Angelov, Plamen, Biaso, Sarah, Higa Froes, Michele, and Kanda Abe, Daniel. "SARS-CoV-2 CT-scan dataset: A large dataset of real patients CT scans for SARS-CoV-2 identification." medRxiv (2020). doi: https://doi.org/10.1101/2020.04.24.20078584.
