# Aerobic biodegradation prediction with XGBoost Regressor

A machine learning model for the aerobic biodegradation prediction (regression) based on XGBoost as the major ML algorithm and MACCS fingerprint as the chemical representation. The repository contains all the related datasets, codes, and model files.

An online predictor was published on [**Aropha AI**](https://www.ai.aropha.com/) at https://www.ai.aropha.com/aerobic-biodegradation/regression/about.html


## Basic information

### Dataset
The regression model was built on more than 4,000 data points and included SMILES strings, guideline (e.g., OECD 301F), principle (e.g., closed respirometer), and reliability (e.g., 1 or 2) as the inputs. The biodegradation percentages are the output.

### ML algorithms
A total of 12 ML algorithms were examined to find the best one, including Ridge, Lasso, K nearest neighbors, Support vector regression, Decision tree, Random forest, Extra trees, Bagging, Adaptive boosting, Gradient boosting, and XGBoost.

XGBoost was found to be the best one.

### Chemical representation
MACCS fingerprints

### Other notes
Bayesian optimization was performed to tune the model hyperparameters. Chemical similarity calculation was conducted using the fingerprint similarity based on Tanimoto index to determine the model applicability domain.

## Explanation of each folder

- **example-smiles-files:** Files containing example SMILES strings that you can directly use for prediction.
- **example:** An example JupyterNotebook that can guide you through the library import, data preparation, prediction, and result saving.
- **model-data:** The original data we used for building the model.
- **models:** The model XGBoost model file you can directly use once loaded (model = pickle.load(open(model, 'rb'))).


## Use the online predictor on Aropha AI
Address: https://www.ai.aropha.com/aerobic-biodegradation/regression/about.html

<img src="/doc/AB_XGB_Regressor.gif?raw=true" align="center">

## Download files to run locally
In addition to using the online predictor, we also encourage you to try the model files locally with your data to have command-line controls over the prediction.
### Dependencies

- **RDkit:** Draw molecules and convert smiles to fingerprints.
- **Numpy:** Create matrices and mathematical operations.
- **Pandas:** Data manipulation.
- **Scikit-learn:** Framework to perform ML models.
- **XGBoost:** Perform a XGBoost model.
- **Pickle:** Load the model files.


### Install the dependencies
#### RDKit
The installation of RDKit using `pip` had been challenging. However, the recent update made it super simple with the following command:
```
pip install rdkit-pypi
```
or traditionally, using `conda`: 
```
conda install -c conda-forge rdkit
```
#### Others
```
pip install numpy
pip install pandas
pip install -U scikit-learn
pip install xgboost
pip install pickle-mixin
```

### Download the model file and follow the JupyterNotebook
You can simply download the model file in the **`models`** folder and follow the JupyterNotebook in the **`example`** folder to run the models for your predictions. 


<img src="/doc/AB_XGB_Regressor_Jupyter.png?raw=true" align="center">
