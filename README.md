# Reproducible-ML4SE
This is the replication package for the paper entitles "On Randomization and Reproducibility in Machine Learning for Software Engineering" by Cynthia C.S. Liem and Annibale Panichella


We provide:
- complete performance results in tabular form in the file `Full_tabular_results.pdf`;
- exact input data files as used in our ML training procedures, structured per predictive SE task, in the folder `Data`;
- random seeds, 10-fold cross-validation partition specification, and results for all models, libraries and research questions, in the folder `Results`.

## Structure of the `Results` folder

    Results
    ├── [task]
    │   ├── [dataset]
    │   │   ├── folds.csv (used for RQ1)
    │   │   ├── random_seeds.csv (used for RQ2)
    │   │   │   ├── [RQ]    
    │   │   │   │   ├── [ML model]  
    │   │   │   │   │   ├── [library]
    │   │   │   │   │   │   ├── performance_metrics.csv

Each `performance_metrics.csv` file gives performance results per run for the three metrics of interest (F-measure, AUC, Matthews Correlation Coefficient).

## How to read folds.csv files

Column `fold_j` specifies the 10-fold cross-validation partitioning for the j-th experimental run.
Column `data_row_index` considers the row index of each data point in the dataset.

For example, the row where `data_row_index`=1 refers to the 1st data point in the csv file in the `Data` folder for the dataset of interest.
If we consider this row, for each column `fold_j`, the fold index (for 10-fold cross-validation: an integer in the range [1,10]) is specified to which this data point was allocated for the j-th 10-fold cross-validation run.