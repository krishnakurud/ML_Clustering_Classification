# Food Nutrition: Classification & Clustering

Machine-learning project on a food nutrition dataset (205 foods; calories, protein, carbs, fat, iron, vitamin C).

## What it does
- **Classification** – predicts a broad food group (Fruits, Vegetables & legumes, Beverages, Baked goods & sweets, Other) from nutrient values using Logistic Regression and Random Forest.
- **Clustering** – groups foods by nutrient profile with K-Means and Hierarchical (Ward) clustering; k is chosen with the elbow method and silhouette score; results are visualised with PCA.

## Project structure
```
├── Food_Nutrition_Dataset.csv
├── food_nutrition_ml.py
├── requirements.txt
└── outputs/          # figures and result tables (generated)
```

## How to run
```bash
pip install -r requirements.txt
python food_nutrition_ml.py
```

## Key results
| Model | CV macro-F1 | Test accuracy | Test macro-F1 |
|---|---|---|---|
| Logistic Regression | 0.61 | 0.48 | 0.45 |
| Random Forest | 0.64 | 0.64 | 0.56 |

K-Means (k=3) separates foods into a low-calorie group (fresh fruit, juices, veg), a high-carb/fat group (baked goods, chips, dried fruit), and a high-protein/iron group (mixed dishes, breads).

## Notes
- The raw `category` column has 61 classes for 205 rows, so categories were merged into 5 broad groups.
- Imputation and scaling run inside a scikit-learn `Pipeline` to avoid data leakage.
- With only 205 samples, results are indicative rather than definitive.
