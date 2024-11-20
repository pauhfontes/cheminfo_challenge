# **Cheminformatics Tech Challenge**

The challenge consists in creating a machine learning model to predict enrichment scores of DEL compounds and evaluate how well it generalizes to real binding affinities (Kd). This repository contains a machine learning model based on mol2vec and XGBoost for SMILES vectorization in order to predict enrichment scores.

## Datasets
All datasets were retrieved from https://42basepairs.com/browse/s3/kin-del-2024

## Packages
  - pandas
  - numpy
  - sklearn
  - rdkit

## Results
For MPK14, the average MSE was 0.085, and _ for DDR1, similar to the results shown on the paper. 


## Potential improvements and alternative approaches
Multiple areas may be improved. For example, in this case, vectors were truncated to 30 elements due to time/RAM limitations, however, PCA can be used to reduce the dimensionality of the mol2vec vector and preserve variance. Additionally, other techniques should be tried to make sure that structural features are not being lost, either by padding or by trying multiple vector lengths.

With additional time, the model should be tested on the held-out test sets, both on-dna and off-dna. Also, this notebook uses {target}_random.parquet splits; disynthon splits should be tried as well. 
Also, hyperparameters can be tuned for the XGboost model in order to improve MSE. 


