# ML New

An end-to-end machine learning project for predicting student performance, with a focus on regression modeling for the target variable `math_score`.

## Overview

This project builds a complete machine learning pipeline using the Student Performance dataset. It covers:

- Data ingestion
- Data preprocessing and feature engineering
- Model training and comparison
- Model evaluation
- Prediction workflow for new inputs

The implementation uses Python and popular ML libraries such as `pandas`, `numpy`, `scikit-learn`, `xgboost`, and `catboost`.

## Project Goal

Predict a student's math score based on features such as:

- gender
- race/ethnicity
- parental level of education
- lunch type
- test preparation course
- reading score
- writing score

## Project Structure

```text
ML_new/
├── src/
│   ├── components/
│   │   ├── data_ingestion.py
│   │   ├── data_transformation.py
│   │   └── model_trainer.py
│   ├── pipeline/
│   │   ├── train_pipeline.py
│   │   └── predict_pipeline.py
│   ├── exception.py
│   ├── logger.py
│   ├── utils.py
│   └── __init__.py
├── logs/
├── requirements.txt
├── setup.py
├── README.md
└── .gitignore
```

## Tech Stack

- Python 3
- pandas
- numpy
- scikit-learn
- xgboost
- catboost
- seaborn
- matplotlib

## Installation

1. Clone the repository.
2. Create and activate a virtual environment:

```bash
python -m venv venv
source venv/bin/activate   # Linux/macOS
venv\Scripts\activate     # Windows
```

3. Install dependencies:

```bash
pip install -r requirements.txt
```

## Dataset

The project expects a student performance dataset. The training script reads the dataset from the following path:

```text
notebook/data/stud.csv
```

Make sure the dataset is available before running the training pipeline.

## Training the Model

Run the training pipeline:

```bash
python src/pipeline/train_pipeline.py
```

This script performs:

- dataset loading
- train/test split
- preprocessing with one-hot encoding and scaling
- model benchmarking across multiple regressors
- best model selection using R² score
- saving the trained model and preprocessor object in the `artifacts` folder

## Prediction Workflow

Prediction logic is implemented in `src/pipeline/predict_pipeline.py`.

You can create a `CustomData` object with student attributes and then use `PredictPipeline` to generate a prediction.

## Model Evaluation

The training pipeline evaluates several regression models, including:

- Random Forest Regressor
- Decision Tree Regressor
- Gradient Boosting Regressor
- Linear Regression
- XGBRegressor
- CatBoost Regressor
- AdaBoost Regressor

The best model is selected based on the highest R² score.

## Notes

- The project uses a modular ML pipeline structure suitable for extension.
- Artifacts such as the trained model and preprocessor are stored under `artifacts/`.
- Logs are written under the `logs/` directory.

## License

This project is intended for educational and learning purposes.
