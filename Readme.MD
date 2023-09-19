This repository contains datasets, model code and notebooks used for all experiments in the [PROSTATA: Protein Stability Assessment using
Transformers](https://www.biorxiv.org/content/10.1101/2022.12.25.521875v1) paper.

## Directories

- `DATA` contains the datasets used for PROSTATA training and testing in the format used by the datasets authors. Also the dataset introduced in this article is available [here](https://github.com/mitiau/PROSTATA/blob/main/DATA/dataset_our_w_clusters_v2.5.pkl).
- `DATASETS` contains the same datasets converted to a format used for model training.
- `PDB` contains the PDB files downloaded during conversion.
- `ACDC_FOLDS` - converted acdc-nn train folds from [here](https://github.com/compbiomed-unito/acdc-nn/tree/master/datasets) and PROSTATA test results on Ssym and Ssym_r folds from [here](https://github.com/compbiomed-unito/acdc-nn/tree/master/results_replication/Ssym_cv.mut).

## Notebooks

- `00.generate_datasets.ipynb` - Process the `DATA` directory and generate the `DATASETS` directory.
- `01.add_megadataset_and_split_on_train_test_sets.ipynb` Expand dataset with megadatasets data. Split on train and test sets. Generate `PROSTATA_EXPERIMENTS` directory.
- `02.test_models_by_folds.ipynb` - Test each individual model in the ensemble using 5-fold cross validation
- `03.test_models_on_other_datasets_ensemble.ipynb` - test the PROSTATA ensemble on various combinations of train and test datasets. `test_*_with_predictions.csv` containts tests set with prediction (`pred_ddg`) column. 
- `04.train_final_ensemble.ipynb` - train the ensemble on all data for the online tool.
- `PROSTATA_tool.ipynb` - Colab notebook for PROSTATA. Predict DDG Values for single mutation on a user sequence.

## Other files

- `environment.yml` - conda environment.
- `PROSTATA_experiments_pearson.log` - Logs of experiments run by 03.test_models_on_other_datasets_ensemble.ipynb notebook.
- `LICENSE` - Apache License 2.0
- `Readme.MD` - This file
