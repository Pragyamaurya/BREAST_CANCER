# BREAST_CANCER

# Breast Cancer Wisconsin (Original) Data Set

This repository contains the Breast Cancer Wisconsin (Original) Data Set. This dataset is often used for binary classification tasks in machine learning and data analysis, especially to predict whether a tumor is benign or malignant based on features extracted from cell images.

## 📊 Dataset Information

- **Instances**: 699 (with some missing values)
- **Attributes**: 11 (10 features + 1 target class)
- **Missing Values**: Yes (represented by '?')
- **Format**: CSV, no header row

### 🔢 Attribute Information

| Index | Feature                         | Description                             |
|-------|----------------------------------|-----------------------------------------|
| 1     | Sample code number              | ID number                                |
| 2     | Clump Thickness                 | 1 - 10                                   |
| 3     | Uniformity of Cell Size        | 1 - 10                                   |
| 4     | Uniformity of Cell Shape       | 1 - 10                                   |
| 5     | Marginal Adhesion              | 1 - 10                                   |
| 6     | Single Epithelial Cell Size    | 1 - 10                                   |
| 7     | Bare Nuclei                    | 1 - 10 (can be missing: '?')            |
| 8     | Bland Chromatin                | 1 - 10                                   |
| 9     | Normal Nucleoli                | 1 - 10                                   |
| 10    | Mitoses                        | 1 - 10                                   |
| 11    | Class                          | 2 = Benign, 4 = Malignant                |

## 📁 File Description

- `breast-cancer-wisconsin.data` — the raw data file without headers.

## 🚀 Usage

You can use this dataset for:
- Binary classification
- Exploratory Data Analysis
- Testing machine learning models

### Example in Python (Pandas)
```python
import pandas as pd

column_names = [
    "ID", "Clump_Thickness", "Uniform_Cell_Size", "Uniform_Cell_Shape",
    "Marginal_Adhesion", "Single_Epithelial_Cell_Size", "Bare_Nuclei",
    "Bland_Chromatin", "Normal_Nucleoli", "Mitoses", "Class"
]

df = pd.read_csv("breast-cancer-wisconsin.data", names=column_names)

# Replace missing values
df.replace("?", pd.NA, inplace=True)

# Drop ID column for ML tasks
df.drop("ID", axis=1, inplace=True)

# Convert to numeric
df = df.apply(pd.to_numeric)

print(df.head())
📚 Source
UCI Machine Learning Repository

