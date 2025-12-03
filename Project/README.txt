Project: Predicting Urban Micromobility Trip Distance Using Linear and Neural Network Models
Author: Bryant Willoughby
Description: This project implements linear regression, SLP, and several nonlinear MLP models
to predict log-transformed micromobility trip distance using a large-scale dataset from the
City of Austin. The repository includes data preparation scripts, modeling notebooks, 
generated figures, and train/validation/test splits.

--------------------------------------------------------------------------------
GITHUB REPOSITORY
--------------------------------------------------------------------------------
All files contained in this project folde are available in the GitHub repository below:

https://github.com/bryant-willoughby/ST-507-Data-Science-Analytics-Using-Python/tree/main/Project 

--------------------------------------------------------------------------------

--------------------------------------------------------------------------------
DATA FILES
--------------------------------------------------------------------------------
austin_micromobility.csv
    - Raw dataset downloaded from the Austin Open Data Portal.
        - available at https://data.austintexas.gov/Transportation-and-Mobility/Shared-Micromobility-Vehicle-Trips-2018-2022-/7d8e-dm7r/about_data 
    - Contains all micromobility trips (bike + scooter), 2018 weekday subset.

austin_micromobility_metadata.txt
    - Describes fields, formats, and metadata associated with the raw dataset.

train_data.csv
test_data.csv
val_data.csv
    - Cleaned and standardized data splits created by DataManipulation.ipynb.
    - Used by all downstream modeling notebooks to ensure reproducibility.

--------------------------------------------------------------------------------
FIGURES
--------------------------------------------------------------------------------
Heatmap.png
    - Origin → destination heatmap of log-transformed district-level trip flows.
    - Generated in DataManipulation.ipynb.

PerceptronLoss.png
    - Training and validation loss curves for the Single-Layer Perceptron (SLP).
    - Generated in LinearModeling.ipynb.

LossMLP.png
    - Training and validation loss curves for nonlinear MLP architectures 
      from the hyperparameter sweeps.
    - Generated in NonLinearModeling.ipynb.

FinalMLP.png
    - Training and validation curves for the final MLP trained using 
      Mini-Batch Gradient Descent (MBGD) on a GPU.
    - Generated in FinalMLP.ipynb.

--------------------------------------------------------------------------------
NOTEBOOKS
--------------------------------------------------------------------------------

DataManipulation.ipynb
    - Loads and cleans the raw dataset.
    - Handles feature engineering, datetime parsing, and outlier removal.
    - Generates Heatmap.png.
    - Outputs the final train/val/test split files used in all models.

LinearModeling.ipynb
    - Implements Multiple Linear Regression (MLR) and Single-Layer Perceptron (SLP).
    - Creates PerceptronLoss.png.
    - Serves as the baseline modeling benchmark.

NonLinearModeling.ipynb
    - Implements nonlinear MLP models.
    - Includes activation sweeps, depth experiments, dropout experiments,
      and early stopping tests.
    - Generates LossMLP.png.

FinalMLP.ipynb
    - Trains the final selected MLP architecture using Mini-Batch Gradient Descent
      and GPU acceleration (e.g., Google Colab).
    - Generates FinalMLP.png.
    - Produces the best-performing model in the entire project.

INSTRUCTIONS
--------------------------------------------------------------------------------
To reproduce results:
1. Run DataManipulation.ipynb to generate cleaned data and Heatmap.png.
2. Run LinearModeling.ipynb for MLR and SLP baselines.
3. Run NonLinearModeling.ipynb for MLP experiments.
4. Run FinalMLP.ipynb on a GPU-enabled environment for final MBGD training.
