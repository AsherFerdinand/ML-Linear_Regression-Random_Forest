# 🧪 Delaney's Solubility Prediction Using ML

<p align="center">
  <strong>My First Machine Learning Project 🚀</strong>
</p>

<p align="center">
  Predicting molecular solubility using Linear Regression and Random Forest Regression.
</p>

---

## 👋 About the Project

Welcome to my first Machine Learning project!

In this project, I explore **Delaney's solubility dataset** to predict the aqueous solubility of chemical compounds using molecular descriptors and supervised machine learning.

The main objective is to investigate how molecular properties relate to solubility and compare the predictive performance of two regression algorithms:

- 📈 **Linear Regression**
- 🌳 **Random Forest Regression**

This project covers the complete machine learning workflow, from loading and preparing data to training models, evaluating performance, visualizing predictions, and predicting the solubility of a new molecule.

## 🎯 Project Objectives

- 📂 Load and explore the solubility dataset.
- 🧹 Prepare the data for machine learning.
- 🔀 Split the dataset into training and testing sets.
- 🤖 Train Linear Regression and Random Forest models.
- 📊 Evaluate model performance using MSE and R².
- 🔍 Compare the predictive performance of both models.
- 🧪 Predict the solubility of a new chemical compound.

## 📊 Dataset

The project uses the Delaney solubility dataset, which contains experimental solubility values and molecular descriptors.

**Dataset source:** [Data Professor — Delaney Solubility Dataset](https://github.com/dataprofessor/data/blob/master/delaney_solubility_with_descriptors.csv)

### Features and Target Variable

| Variable | Description |
|---|---|
| `MolLogP` | Calculated logarithm of the octanol-water partition coefficient, related to molecular lipophilicity |
| `MolWt` | Molecular weight of the compound |
| `NumRotatableBonds` | Number of rotatable bonds in the molecule |
| `AromaticProportion` | Proportion of aromatic atoms in the molecule |
| `logS` | Logarithmic aqueous solubility; the target variable |

The four molecular descriptors are used as input features (**X**), while `logS` is the target (**y**) that the models learn to predict.

## 🛠️ Technologies Used

- 🐍 Python
- 🐼 Pandas — data loading and manipulation
- 🔢 NumPy — numerical computations
- 📉 Matplotlib — data visualization
- 🤖 Scikit-learn — machine learning and model evaluation
- 📓 Jupyter Notebook — interactive development and experimentation

## ⚙️ Project Workflow

### 1. Load the Data 📂

Load the dataset directly from GitHub using Pandas.

### 2. Prepare the Data 🧹

Separate the molecular descriptors from the target variable, `logS`.

### 3. Split the Data 🔀

Use `train_test_split` to allocate 80% of the data for training and 20% for testing, with `random_state=100` for reproducibility.

### 4. Train the Models 🤖

**Linear Regression:** Establishes a linear relationship between molecular descriptors and solubility.

**Random Forest Regression:** Uses an ensemble of decision trees to model potentially nonlinear relationships.

The Random Forest model uses `max_depth=2` and `random_state=100`.

### 5. Evaluate Performance 📏

Evaluate both models on the training and testing sets using:

- **Mean Squared Error (MSE):** Measures the average squared prediction error. Lower values are better.
- **R² Score:** Measures the proportion of variance in the target explained by the model. Values closer to 1 generally indicate a better fit.

### 6. Visualize Predictions 📈

Create a scatter plot comparing experimental solubility values with model predictions to examine how closely the predictions follow the observed values.

### 7. Predict a New Molecule 🧪

Use the trained Linear Regression model to estimate the solubility of a new molecule from its four molecular descriptors.

## 📊 Model Performance

The following results were obtained in the experiment.

| Model | Training MSE | Training R² | Test MSE | Test R² |
|---|---:|---:|---:|---:|
| 📈 Linear Regression | 1.0075 | 0.7645 | 1.0207 | **0.7892** |
| 🌳 Random Forest | 1.0282 | 0.7597 | 1.4077 | 0.7092 |

### 🏆 Key Findings

- 📈 **Linear Regression performed better on the test set**, achieving an R² score of approximately 0.7892.
- 🎯 The Linear Regression model obtained a lower test MSE of approximately 1.0207 compared with 1.4077 for Random Forest.
- 🌳 The Random Forest model, configured with a maximum tree depth of 2, performed less effectively on unseen data in this experiment.
- 🔬 The results demonstrate that a relatively simple linear model can be a useful baseline for predicting molecular solubility.

*Note: These results apply to the selected train-test split and model configurations. Further validation and hyperparameter tuning would be needed to draw broader conclusions.*

## 🧪 New Molecule Prediction

The trained Linear Regression model was used to predict the solubility of a hypothetical molecule with the following descriptors:

| Descriptor | Value |
|---|---:|
| `MolLogP` | 1.2 |
| `MolWt` | 180.16 |
| `NumRotatableBonds` | 2 |
| `AromaticProportion` | 0.40 |

### Prediction Results

- **Predicted logS:** -2.0086
- **Predicted molar solubility:** approximately 0.00980 mol/L

The conversion from log solubility to molar solubility is:

\[
S = 10^{\log S}
\]

For the predicted value:

\[
S = 10^{-2.0086} \approx 0.00980\ \text{mol/L}
\]

⚠️ This is a model-generated estimate for the specified descriptors, not an experimentally verified solubility measurement. It assumes that `logS` represents a base-10 logarithm of solubility in mol/L, consistent with the conversion used in the notebook.

## 🚀 Getting Started

### Prerequisites

Install Python and the required libraries.

```bash
pip install pandas numpy matplotlib scikit-learn jupyter
```

### Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

Replace the placeholder repository URL with your actual GitHub repository.

### Launch Jupyter Notebook

```bash
jupyter notebook
```

Open the project notebook and run the cells sequentially.

The dataset is loaded directly from its public GitHub URL, so a separate local dataset download is not required.

## 📁 Suggested Repository Structure

```text
delaney-solubility-ml/
│
├── README.md
├── delaney_solubility_prediction.ipynb
└── requirements.txt
```

The notebook filename above is a suggestion; use your actual filename in the repository.

## 🔮 Future Improvements

- 🌲 Optimize Random Forest hyperparameters using `GridSearchCV` or `RandomizedSearchCV`.
- 🔁 Apply cross-validation for more robust performance estimates.
- 🧠 Experiment with additional regression algorithms, such as Ridge, Lasso, Gradient Boosting, and Support Vector Regression.
- 📉 Add residual plots and predicted-versus-experimental plots for both models.
- 🧬 Explore additional molecular descriptors or fingerprints.
- 📊 Investigate feature importance and model interpretability.
- ⚗️ Compare predictions against experimentally measured solubility for new compounds.

## 💡 What I Learned

Through this project, I gained practical experience with:

- Loading and preparing real-world scientific data.
- Separating input features from a target variable.
- Training supervised regression models with Scikit-learn.
- Evaluating models using MSE and R².
- Comparing model performance on unseen data.
- Visualizing predictions and applying a trained model to a new example.

## 🤝 Contributions

Suggestions, feedback, and improvements are welcome!

If you find this project useful:

- ⭐ Star the repository.
- 🍴 Fork it to experiment with other models.
- 💬 Open an issue or share suggestions for improvement.

## 📜 Acknowledgements

Special thanks to [Data Professor](https://github.com/dataprofessor) for providing the dataset and educational resources that helped inspire this project.

---

<p align="center">
  Made with 🧪, 🐍, and 🤖
</p>

<p align="center">
  <strong>Learning Machine Learning, One Project at a Time! 🚀</strong>
</p>
