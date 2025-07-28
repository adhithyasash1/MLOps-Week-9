# 🌍 iris fairness analysis

this project introduces a synthetic “location” attribute into the classic iris dataset, uses it as a sensitive feature in a fairlearn explainer, and then shows how to interpret shap full-dataset summary plots for the virginica class.

---

## 🎯 assignment objective

- **add a `location` column** (values 0 or 1 at random) to each iris record  
- **train and evaluate** a classifier on this augmented data  
- **use fairlearn** to explain disparity across `location` groups  
- **generate shap summary plots** for the virginica class and explain in simple terms what they tell us

---

## 📂 directory structure

```
iris-fairness-analysis/
└── data/
└── iris.csv
└── fairness.ipynb
└── README.md
```

---

## 📄 file descriptions

- **data/iris.csv**  
  the raw iris dataset (150 samples × 5 columns). each row has sepal & petal measurements plus species. this file is used as the input to the notebook.

- **fairness.ipynb**  
  a self-contained jupyter notebook that:
  1. reads `data/iris.csv` and **inserts** a random `location` (0 or 1) column  
  2. **splits** the data into train/test sets, preserving species and location distributions  
  3. trains a simple classifier (e.g., decision tree) and records standard metrics  
  4. uses **fairlearn.explain** to compute group-wise performance for `location` = 0 vs. 1  
  5. computes **SHAP** values on the test set, produces a full-dataset summary plot for the “virginica” class, and includes plain-english annotations  
  6. prints a clear, human-readable explanation of what the shap plot for virginica tells you

- **README.md**  
  this file. explains the project objective and the role of each included file.

---

## 🚀 getting started

1. clone the repo  
2. install dependencies (e.g., `pip install scikit-learn pandas shap fairlearn jupyterlab`)  
3. launch the notebook:  
   ```bash
   cd iris-fairness-analysis/
   jupyter lab fairness.ipynb
4. follow the notebook cells to see how location is added, fairness metrics are computed, and shap plots are generated and interpreted.


🔍 shap summary plot interpretation (virginica)

in the notebook you’ll see a summary plot where each dot:

sits on the x-axis at the shap value (how strongly that feature pushes toward or away from predicting virginica)
is colored by the original feature value (low → blue, high → red)
is grouped by feature on the y-axis (features sorted by average importance)
you’ll learn in simple words that petal length and width drive virginica predictions (red = long/wide → pushes toward virginica; blue = short/narrow → pushes away), while sepal measurements have minimal effect.

## author

R Sashi Adhithya (21F3000611)
github: @adhithyasash1
