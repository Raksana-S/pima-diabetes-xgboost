# Pima Hindistanlıları üzrə Diabet Proqnozlaşdırılması

Bu layihədə xəstələrin tibbi göstəricilərinə əsasən onların diabet xəstəliyinə tutulub-tutulmayacağı **XGBoost Classifier** modeli ilə proqnozlaşdırılır. Modelin parametrləri **Grid Search** və **Randomized Search** üsulları ilə optimallaşdırılır və nəticələr müqayisə edilir.

## Dataset

[Pima Indians Diabetes Dataset](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database) — 768 sətir, 9 sütun.

| Sütun | Təsvir |
|---|---|
| Pregnancies | Hamiləliklərin sayı |
| Glucose | Qlükoza səviyyəsi |
| BloodPressure | Qan təzyiqi |
| SkinThickness | Dəri qalınlığı |
| Insulin | İnsulin səviyyəsi |
| BMI | Bədən kütlə indeksi |
| DiabetesPedigreeFunction | İrsi diabet göstəricisi |
| Age | Yaş |
| Outcome | Hədəf dəyişən (1 — diabet var, 0 — yoxdur) |

## İşin mərhələləri

1. Datasetin yüklənməsi və ilkin araşdırılması
2. Kənar dəyərlərin boxplot ilə yoxlanılması
3. Tibbi baxımdan mümkün olmayan sıfır dəyərlərin median ilə əvəz edilməsi
4. Korrelyasiya matrisinin qurulması
5. Datasetin təlim (80%) və test (20%) hissələrinə bölünməsi
6. İlkin XGBoost modelinin qurulması
7. Grid Search ilə parametrlərin optimallaşdırılması
8. Randomized Search ilə parametrlərin optimallaşdırılması
9. Modellərin accuracy, classification report və confusion matrix ilə qiymətləndirilməsi

## Nəticələr

| Model | Test Accuracy |
|---|---|
| İlkin XGBoost | **0.773** |
| Grid Search | 0.727 |
| Randomized Search | 0.753 |

Test datasında ən yüksək nəticəni ilkin XGBoost modeli göstərdi. Parametrlərin optimallaşdırılması bu layihədə test accuracy nəticəsini yüksəltmədi.

## Faylların strukturu

```
pima-diabetes-xgboost/
├── pima_diabetes_xgboost.ipynb   # Əsas notebook
├── diabetes.csv                  # Dataset
└── README.md
```

## İstifadə olunan kitabxanalar

```
pandas
numpy
matplotlib
seaborn
scikit-learn
xgboost
```

## İşə salmaq

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost
jupyter notebook pima_diabetes_xgboost.ipynb
```
