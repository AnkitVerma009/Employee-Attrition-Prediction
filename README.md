# Employee-Attrition-Prediction
This project predicts employee attrition using a limited number of expert-provided labels. It simulates a real-world scenario where labeling is expensive and restricted. A Subject Matter Expert (SME) provides only 500 labels, and the resulting labeled dataset is used to train a machine learning model to predict which employees are likely to leave.

## Objective

To build a machine learning model that can predict employee attrition based on historical HR data, using only a limited number of labels provided by an SME system.

## Data

- Input Features: `employee_departure_dataset_X.csv`
- Labels (used internally by SME): `employee_departure_dataset_y.csv`
- Source:  
  `https://raw.githubusercontent.com/msaricaumbc/DS_data/master/ds602/final/employee_departure_dataset_X.csv`

## How SME Labeling Works

- The SME is a class that contains true labels internally.
- You can call `sme.ask(feature_dict)` to request the label for a given row.
- Each SME call costs one label out of a maximum of 500.
- If the SME is unsure (no match) or quota is exceeded, it raises an exception.
- Labeled rows are collected and used to train the model.

## Steps in the Notebook

1. Load the dataset.
2. Clean and preprocess data.
3. Use SME to obtain 500 labeled samples.
4. Split the labeled data into train/test sets.
5. Train a machine learning model.
6. Evaluate model performance.

## Technologies Used

- Python
- pandas
- scikit-learn

## How to Use

1. Clone the repository.
2. Open the notebook `Employee Attrition Prediction.ipynb`.
3. Run all cells to simulate the labeling and model training process.
4. You can modify the model or labeling strategy as needed.

## Notes

- The SME class enforces a hard limit of 500 queries.
- Labeling decisions depend on exact value matches, so missing data must be cleaned properly.
- You can experiment with active learning or clustering strategies to improve label efficiency.
