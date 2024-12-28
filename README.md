# Data Preprocessing and Feature Engineering in Machine Learning

## Objective
This repository contains an implementation of various data preprocessing, feature engineering, and feature selection techniques on the "Adult" dataset. The objective is to predict whether an individual's income exceeds $50K per year based on census data. The project demonstrates essential techniques for preparing data for machine learning models, ensuring their efficiency and accuracy.

---

## Dataset
The "Adult" dataset, widely used for classification tasks, consists of census data with various features such as age, work class, education, marital status, occupation, and more. The target variable is a binary classification task: income (<=50K or >50K).

---

## Tasks
### 1. Data Exploration and Preprocessing
- **Data Loading**: Loaded the dataset and conducted a detailed exploration including summary statistics, data types, and missing values.
- **Handling Missing Values**: Addressed missing values using best practices such as imputation and removal.
- **Scaling**: Applied the following scaling techniques to numerical features:
  - **Standard Scaling**: Standardized data to have a mean of 0 and a standard deviation of 1. Suitable for algorithms sensitive to feature magnitude like logistic regression and SVMs.
  - **Min-Max Scaling**: Transformed data to a specific range (e.g., [0, 1]). Preferred for neural networks and gradient-based algorithms.

---

### 2. Encoding Techniques
- **One-Hot Encoding**: Applied to categorical variables with fewer than 5 categories.
  - **Pros**: Removes ordinal relationships; suitable for tree-based models.
  - **Cons**: Increases dimensionality for features with high cardinality.
- **Label Encoding**: Applied to categorical variables with more than 5 categories.
  - **Pros**: Efficient storage and processing.
  - **Cons**: Can introduce unintended ordinal relationships, affecting linear models.

---

### 3. Feature Engineering
- **New Features**:
  1. Created a "working_hours_per_week_ratio" feature by dividing working hours by the maximum observed.
  2. Generated an "age_bucket" feature by binning the age into intervals.
- **Transformations**:
  - Applied log transformation to the "capital-gain" feature to handle skewness.

---

### 4. Feature Selection
- **Isolation Forest**:
  - Used to identify and remove outliers.
  - **Impact**: Outliers can distort models like linear regression, leading to poor generalization.
- **Predictive Power Score (PPS)**:
  - Measured the predictive strength of features against the target and other variables.
  - **Comparison**: PPS provides non-linear relationships compared to traditional correlation matrices which show only linear relationships.

---

## Usage
### Prerequisites
Ensure you have Python installed along with the following libraries:
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn
- pyPPS

Install dependencies with:
```bash
pip install -r requirements.txt
```

### Steps to Run
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/your-repo-name.git
   ```
2. Navigate to the project directory:
   ```bash
   cd your-repo-name
   ```
3. Run the notebook or Python script containing the implementation.

---

## Results and Discussion
- Scaling, encoding, and feature engineering significantly improved data quality and model interpretability.
- The Isolation Forest removed key outliers, enhancing the robustness of downstream models.
- PPS analysis revealed meaningful feature relationships not captured by linear correlation.

---

