﻿# Data-Science

# Data-Science Projects

## Table of Contents

1. [Wine Quality Prediction Project](#wine-quality-prediction-project)
2. [羅馬數字 Kaggle 競賽](#羅馬數字kaggle競賽)
3. [PDS Assignment 1](#pds_assignment1)
4. [PDS Assignment 2](#pds_assignment2)
5. [PDS Assignment 3](#pds_assignment3)
6. [PDS Assignment 4](#pds_assignment4)


# Wine Quality Prediction Project

This project focuses on predicting the quality of wine based on various physicochemical features and a target variable, `quality`, from a UCI dataset. The dataset includes 11 physicochemical tests and a target variable, `quality`, which is an integer score ranging from 3 to 9.

## Project Overview

The project includes the following steps:
1. **Data Preprocessing**: Cleaning, encoding categorical variables, and standardizing numerical features.
2. **Feature Engineering**: Creating interaction terms and selecting relevant features using Featurewiz and Boruta.
3. **Exploratory Data Analysis (EDA)**: Visualizing relationships between features and the target variable.
4. **Model Training and Evaluation**: Training models using selected features and comparing performance metrics.
5. **Feature Importance Analysis**: Analyzing feature importance using Random Forest and SHAP.

---

## Dataset Details

- **Source**: UCI Machine Learning Repository
- **Features**:
  1. `fixed_acidity`: Fixed acids present in the wine.
  2. `volatile_acidity`: Volatile acids affecting aroma.
  3. `citric_acid`: Citric acid contributing to freshness.
  4. `residual_sugar`: Sugar left after fermentation.
  5. `chlorides`: Salt content.
  6. `free_sulfur_dioxide`: Protects wine from oxidation.
  7. `total_sulfur_dioxide`: Free + bound sulfur dioxide.
  8. `density`: Wine density linked to sugar and alcohol.
  9. `pH`: Acidity level.
  10. `sulphates`: Sulfur compounds enhancing flavor.
  11. `alcohol`: Alcohol content.
  12. `quality`: Target variable (wine quality score).

---

## Steps and Implementation

### 1. Data Preprocessing
- Encoded the `color` feature:
  - `red` as 0, `white` as 1.
- Standardized numeric features using `StandardScaler`.
- Addressed class imbalance using SMOTE (Synthetic Minority Oversampling Technique).

### 2. Feature Engineering
- Added interaction terms:
  - `fixed_acidity * volatile_acidity`
  - `residual_sugar * alcohol`
- Used `Featurewiz` and `Boruta` for feature selection, identifying:
  - Selected features: `alcohol`, `acidity_interaction`, `sugar_alcohol_interaction`, `density`, `pH`, `sulphates`

### 3. Exploratory Data Analysis (EDA)
- **Boxplots**: Analyzed distributions of features across `quality` levels.
- **Correlation Heatmap**: Visualized relationships between features and the target variable.
- **Feature Importance**:
  - Random Forest-based feature importance.
  - SHAP plots for feature explanations.

### 4. Model Training and Evaluation
- **Models Used**:
  - Random Forest Classifier
  - Gradient Boosting Classifier
  - Support Vector Machine (SVM)
- **Feature Selection Evaluation**:
  - Compared performance of models trained on selected features vs. all features.
  - Best results achieved using SMOTE with selected features:
    - Test accuracy: **67.3%**

### 5. Feature Importance Analysis
- Used SHAP for interpretability:
  - Summary plots to visualize feature contributions.
  - Dependence plots for individual features.
  - Waterfall plots for single-instance explanations.

---

## Results
- **Performance Metrics**:
  - Best Model: Random Forest Classifier
  - Test Set Accuracy: **67.3%** (using SMOTE and selected features)
  - Confusion Matrix and Classification Report were used for detailed evaluation.

---

## Tools and Libraries
- **Data Manipulation**: `pandas`, `numpy`
- **Visualization**: `matplotlib`, `seaborn`
- **Feature Engineering**: `Featurewiz`, `BorutaPy`
- **Modeling**: `scikit-learn`
- **Explainability**: `SHAP`

---

## How to Run the Project

1. **Clone the Repository**:
   ```bash
   git clone <repository-link>
   cd wine-quality-prediction
   ```

2. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Jupyter Notebooks**:
   - Explore EDA and Feature Engineering in `04_Clean_feature_engineering.ipynb`.
   - Perform Feature Selection in `05_Feature_selection_extraction.ipynb`.
   - Train and Evaluate Models in `07_Deploy.ipynb`.

4. **Dataset**:
   Place the `winequality.csv` dataset in the project directory.

---

## Future Improvements
- Fine-tune hyperparameters for Gradient Boosting and SVM.
- Experiment with deep learning models for quality prediction.
- Integrate advanced feature engineering techniques.

---

## Acknowledgments
- UCI Machine Learning Repository for providing the dataset.
- Open-source libraries and frameworks for enabling efficient development.

# 羅馬數字Kaggle競賽

## 簡介
此項目在於利用 Cleanlab 和 TensorFlow 進行圖像分類任務，并結合 Cleanvision 和 Albumentations 進行資料質量檢測與圖像增強。項目目的是提高資料質量和模型模範能力，最終完成模型訓練和結果分析。

---

## 安裝需求
執行此 Notebook 所需的 Python 套件：

- `cleanlab`
- `cleanvision`
- `scikeras`
- `keras-cv`
- `albumentations`

可使用下列指令安裝：
```bash
pip install cleanlab cleanvision scikeras keras-cv albumentations
```

---

## 項目結構
- **資料讀取與增強**: 使用 TensorFlow 和 Albumentations 處理圖像資料，包括文件讀取和增強操作。
- **資料質量檢測**: 利用 Cleanlab 分析標籤異常，並驗證資料的純淨性。
- **模型訓練**: 結合 TensorFlow 和 Scikeras 進行分類模型訓練。
- **圖像視覺化**: 提供自訂函式展示圖像資料和預測結果。

---

## 使用方法
1. 將資料夾結構整理如下：
   ```
   /content/
   ├── training_data/
   └── label_book/
   ```
2. 執行 Notebook 內所有 Cells。
3. 使用 `plot_examples` 函式可視化訓練結果和資料設定。

---

## 主要功能
- **標籤問題檢測**: 使用 Cleanlab 寻找資料標籤的異常。
- **圖像增強**: 通過 Albumentations 提升模型的泛化能力。
- **資料視覺化**: 對圖像和預測結果進行自訂展示，有助評估模型性能。

---

## 結果與展望
完成後的 Notebook 可用於評估標籤質量及模型訓練效果，後續可結合更多模型與資料集進行深入檢測和實驗。

---

## 操作流程固定例子
以下為實驗流程中的一個圍觀：

### 1. 安裝套件
執行以下指令依起依賴：
```bash
pip install cleanlab cleanvision scikeras keras-cv albumentations
```

### 2. 資料載入與初始化
```python
import tensorflow as tf
from tensorflow import keras
import cleanlab
from cleanvision.imagelab import Imagelab
from tensorflow.keras.utils import image_dataset_from_directory

# 定義資料目錄
training_data = "/content/training_data"
label_book = "/content/label_book"

# 載入資料
train_dataset = image_dataset_from_directory(training_data)
```

### 3. 圖像增強
```python
import albumentations as A

augmentations = A.Compose([
    A.HorizontalFlip(p=0.5),
    A.RandomBrightnessContrast(p=0.2),
    A.ShiftScaleRotate(p=0.3)
])
```

### 4. 標籤檢測
```python
from cleanlab.filter import find_label_issues
issues = find_label_issues(labels=y_train, probabilities=model_probs)
```

### 5. 視覺化函式
```python
import matplotlib.pyplot as plt

def plot_examples(id_iter, nrows=1, ncols=1):
    for count, id in enumerate(id_iter):
        plt.subplot(nrows, ncols, count + 1)
        plt.imshow(images[id].reshape(32, 32, 3), cmap="gray")
        plt.title(f"id: {id}")
        plt.axis("off")

    plt.tight_layout(h_pad=3.0)
```

---

# PDS_Assignment1

## 簡介

此項目針對 Melbourne 房地產資料進行分析，包括資料清理、分割和模型訓練，以預測房地產價格。Notebook 通過使用 PyCaret、Cleanlab 和 Scikit-learn 進行資料處理和模型構建，提高分析效率和模型泛化能力。

---

## 安裝需求

執行此 Notebook 所需的 Python 套件：

- `pycaret[full]`
- `cleanlab`
- `snorkel`
- `pandas`
- `numpy`
- `scikit-learn`

使用下列指令安裝所需套件：
```bash
pip install --pre pycaret[full] cleanlab snorkel
```

---

## 項目結構

- **資料清理**:
  - 讀取 Melbourne 房地產資料集，刪除與分析無關的欄位（如 `Date` 和 `Address`）。
  - 處理欄位的空值，使數據純淨化。

- **資料分割**:
  - 使用 Scikit-learn 將數據分割為 95%訓練集和 5%測試集。

- **模型訓練**:
  - 使用 PyCaret 的自動化模範構建模範，選取最佳模型進行固定化。

---

## 使用方法

### 1. 準備數據

確保檔案 `melb_data.csv` 位於項目執行目錄中，並且格式無誤。

### 2. 執行 Notebook

打開 Jupyter Notebook 并執行每個 Cell：

#### 資料清理
```python
import pandas as pd

df = pd.read_csv("melb_data.csv")
df = df.drop(['Date', 'Address'], axis=1)
```

#### 資料分割
```python
from sklearn.model_selection import train_test_split

X = df.drop('Price', axis=1)
y = df['Price']

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.05, random_state=2024)

print(f"Training set size: {len(X_train)}")
print(f"Testing set size: {len(X_test)}")
```

#### 模型構建
```python
from pycaret.regression import *

reg = setup(data=df, target='Price')
best_model = compare_models()
```

---

## 主要功能

- **數據清理**:
  刪除無關欄位，處理空值以確保數據純淨。
- **數據分割**:
  以自定義比例分割為訓練集和測試集，確保模型泛化能力。
- **模型訓練**:
  利用 PyCaret 選取最佳固定化模型，對房地產價格進行固定化預測。

---

## 結果與展望

此項目完成了 Melbourne 房地產數據的分析與預測模型構建，提高分析效率和模型泛化能力。後續可採用進階特徵工程和視覺化分析，以提升模型表現。

---

## 附註

資料來源為 Melbourne 房地產資料集，需確保 Python 版本在 3.9 以上，以免出現套件依起問題。


# PDS_Assignment2

## 簡介

此項目針對 Melbourne 房地產資料進行分析，主要探討空值處理方法對回歸模型表現的影響。通過使用多種採構技術和隨機梯梯回歸器（Random Forest Regressor），比較不同方法在預測清準度上的表現。

---

## 安裝需求

執行此 Notebook 所需的 Python 套件：
- `pandas`
- `scikit-learn`

使用下列指令安裝所需套件：
```bash
pip install pandas scikit-learn
```

---

## 項目結構

- **數據讀取與分割**:
  - 讀取 `melb_data.csv` 數據集，刪除與預測無關的欄位（如 `Date`、`Address`），將數據分為訓練集和測試集。

- **空值處理**:
  - **方法 1**: 刪除含有空值的欄位。
  - **方法 2**: 使用中位數填補空值。
  - **方法 3**: 使用 KNN 採構進行空值填補。

- **模型訓練與衡量**:
  - 使用隨機梯梯回歸器（Random Forest Regressor）進行模型訓練。
  - 以 `MAPE`（平均絕對百分比誤差）作為模型效能的衡量指標。

---

## 使用方法

### 1. 準備數據
確保檔案 `melb_data.csv` 位於項目執行目錄中。

### 2. 數據讀取與分割
```python
import pandas as pd
from sklearn.model_selection import train_test_split

# 讀取數據並分割
df = pd.read_csv('melb_data.csv')
y = df.Price
data = df.drop(['Price', 'Date', 'Address'], axis=1)

X_train, X_valid, y_train, y_valid = train_test_split(data, y, train_size=0.8, test_size=0.2, random_state=2024)
```

### 3. 空值處理
#### 方法 1: 刪除含空值欄位
```python
X_train_num_drop = X_train.dropna(axis=1)
X_valid_num_drop = X_valid[X_train_num_drop.columns]
```

#### 方法 2: 中位數填補
```python
from sklearn.impute import SimpleImputer

imputer_median = SimpleImputer(strategy='median')
X_train_num_median = pd.DataFrame(imputer_median.fit_transform(X_train), columns=X_train.columns)
X_valid_num_median = pd.DataFrame(imputer_median.transform(X_valid), columns=X_valid.columns)
```

#### 方法 3: KNN 採構填補
```python
from sklearn.experimental import enable_iterative_imputer
from sklearn.impute import IterativeImputer
from sklearn.neighbors import KNeighborsRegressor

imputer_knn = IterativeImputer(estimator=KNeighborsRegressor(n_neighbors=15), random_state=2024)
X_train_num_knn = pd.DataFrame(imputer_knn.fit_transform(X_train), columns=X_train.columns)
X_valid_num_knn = pd.DataFrame(imputer_knn.transform(X_valid), columns=X_valid.columns)
```

### 4. 模型訓練和測試
```python
from sklearn.ensemble import RandomForestRegressor
from sklearn.metrics import mean_absolute_percentage_error

def scoring_mape(X_train, X_valid, y_train, y_valid):
    model = RandomForestRegressor(n_estimators=10, random_state=2024)
    model.fit(X_train, y_train)
    preds = model.predict(X_valid)
    return mean_absolute_percentage_error(y_valid, preds)

mape_drop = scoring_mape(X_train_num_drop, X_valid_num_drop, y_train, y_valid)
mape_median = scoring_mape(X_train_num_median, X_valid_num_median, y_train, y_valid)
mape_knn = scoring_mape(X_train_num_knn, X_valid_num_knn, y_train, y_valid)

print(f"MAPE (Remove Columns): {mape_drop}")
print(f"MAPE (Median Imputation): {mape_median}")
print(f"MAPE (KNN Imputation): {mape_knn}")
```

---

## 主要功能

- **空值處理**: 提供多種方法處理空值，包括刪除欄位、中位數填補和 KNN 採構。
- **模型訓練與效能衡量**: 使用 Random Forest Regressor 進行固定化模型，并使用 MAPE 衡量預測清準度。
- **數據分割和特徵處理**: 自動匹配數值和類別特徵，簡化數據預處理流程。

---


# PDS_Assignment3

## 簡介

此專案專注於分析金融交易數據，通過數據處理、特徵工程與多種機器學習模型進行分類，並對模型性能進行全面評估。最終目標為準確預測交易類型，從而提供數據驅動的商業決策支持。

---

## 安裝需求

執行此 Notebook 所需的 Python 套件：

- `pandas`
- `numpy`
- `scikit-learn`
- `matplotlib`

使用以下命令安裝所需套件：

```bash
pip install pandas numpy scikit-learn matplotlib
```

---

## 專案結構

### 1. 資料讀取與處理

- 從 `transaction_data.csv` 文件讀取數據，並完成缺失值處理與類別型變數編碼。
- 探索性數據分析 (EDA)：通過統計描述和可視化方法理解數據分佈與特性。

### 2. 特徵工程

- 創建新特徵以捕捉數據中更多潛在模式，例如交易金額標準化值。
- 使用特徵選擇技術優化模型訓練過程中的重要特徵。

### 3. 模型訓練與評估

- 使用以下分類模型進行訓練：
  - Logistic Regression
  - Random Forest
  - Gradient Boosting
- 使用性能指標（準確率、精確度、召回率和 F1 分數）比較模型表現。
- 可視化混淆矩陣與 ROC 曲線，分析模型的分類能力。

---

## 使用方法

### 1. 準備數據

將 `transaction_data.csv` 文件放置於專案根目錄下。

### 2. 運行 Notebook

逐步執行 Notebook 的每個 Cell，完成數據處理、特徵工程與模型訓練。

#### 數據讀取與預處理

```python
import pandas as pd

# 讀取數據
df = pd.read_csv('transaction_data.csv')

# 處理缺失值
df.fillna(df.mean(), inplace=True)

# 類別型變數編碼
df = pd.get_dummies(df, columns=['category'], drop_first=True)
```

#### 特徵選擇與建模

```python
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import classification_report, confusion_matrix

# 分割數據集
X = df.drop('target', axis=1)
y = df['target']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# 訓練模型
clf = RandomForestClassifier(random_state=42)
clf.fit(X_train, y_train)

# 模型評估
y_pred = clf.predict(X_test)
print(classification_report(y_test, y_pred))
print(confusion_matrix(y_test, y_pred))
```

---

## 主要功能

- **數據清理與處理**：填補缺失值、進行類別型變數的獨熱編碼。
- **探索性數據分析**：分析數據分佈和相關性，提供關鍵的數據洞察。
- **特徵工程**：創建新特徵並進行特徵選擇，提升模型性能。
- **分類模型訓練與比較**：利用多種機器學習模型進行分類任務，找出最佳模型。
- **性能評估**：使用多種指標（如 F1 分數）和圖表（如混淆矩陣）全面分析模型表現。

---

## 結果與展望

本專案成功實現交易數據分類，並通過多模型比較選擇最佳分類器。結果顯示，基於 Random Forest 的模型具有優越的分類能力。未來可加入更多進階特徵工程方法及深度學習技術，進一步提升模型的泛化性能。

---

## 附註

- 本專案需要 Python 3.9 或更高版本。
- 如果數據集結構發生變化，需根據需求調整特徵工程與模型構建邏輯。
- 測試集和訓練集的分割比例可根據具體應用場景調整。

# PDS_Assignment4

## 簡介

此專案專注於基於深度學習的圖像分類任務，運用 TensorFlow 和 Keras 對多類別圖像數據進行建模與預測。通過構建卷積神經網絡（CNN），完成對數據集的訓練、驗證與測試。

---

## 安裝需求

執行此 Notebook 所需的 Python 套件：

- `numpy`
- `tensorflow`
- `gdown`

使用以下命令安裝所需套件：

```bash
pip install numpy tensorflow gdown
```

---

## 專案結構

### 1. 資料下載與準備

- 從 Google Drive 下載壓縮檔案 `cnn_data.zip` 並解壓縮，生成訓練、驗證和測試數據集。
- 使用 TensorFlow 的 `image_dataset_from_directory` 方法構建數據集對象，並設定圖像大小與批次大小。

### 2. 模型構建與訓練

- 使用 Keras 構建卷積神經網絡（CNN），設計包含多層卷積、池化與全連接層的架構。
- 編譯模型時選擇適當的損失函數與優化器（例如 Adam）。
- 設置訓練過程中的早停策略與學習率調整機制。

### 3. 性能評估與測試

- 通過繪製學習曲線觀察模型的收斂情況。
- 使用混淆矩陣與分類報告對測試集上的模型性能進行全面評估。
- 保存最佳模型以供後續使用。

---

## 使用方法

### 1. 準備數據

下載並解壓數據集：
```bash
!gdown --fuzzy https://drive.google.com/file/d/1DvyriY4ehA56Bj3asAbCz_syYZvTkumW/view?usp=sharing
!unzip cnn_data.zip
```

確保數據目錄結構如下：
```
cnn_data/
├── train_images/
├── val_images/
└── test_images/
```

### 2. 數據加載與處理

使用以下代碼加載數據集：

```python
import numpy as np
import tensorflow as tf
from tensorflow.keras.utils import image_dataset_from_directory

seed = 2024
training_images = 'train_images/'
vali_images = 'val_images/'
test_images = 'test_images/'

train_dataset = image_dataset_from_directory(
    training_images,
    image_size=(64, 64),
    shuffle=True,
    batch_size=32,
    seed=seed)

validation_dataset = image_dataset_from_directory(
    vali_images,
    image_size=(64, 64),
    shuffle=False,
    batch_size=32)

test_dataset = image_dataset_from_directory(
    test_images,
    image_size=(64, 64),
    shuffle=False,
    batch_size=32)
```

### 3. 模型構建與訓練

```python
from tensorflow.keras import Sequential
from tensorflow.keras.layers import Conv2D, MaxPooling2D, Flatten, Dense, Dropout

model = Sequential([
    Conv2D(32, (3, 3), activation='relu', input_shape=(64, 64, 3)),
    MaxPooling2D((2, 2)),
    Conv2D(64, (3, 3), activation='relu'),
    MaxPooling2D((2, 2)),
    Flatten(),
    Dense(128, activation='relu'),
    Dropout(0.5),
    Dense(10, activation='softmax')
])

model.compile(optimizer='adam',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])

history = model.fit(train_dataset,
                    validation_data=validation_dataset,
                    epochs=10)
```

### 4. 模型測試與保存

```python
loss, accuracy = model.evaluate(test_dataset)
print(f"Test Loss: {loss}, Test Accuracy: {accuracy}")

model.save('best_cnn_model.h5')
```

---

## 主要功能

- **數據集構建**：基於目錄結構自動加載多類別圖像數據。
- **CNN 模型設計**：自定義卷積層與全連接層，靈活調整架構參數。
- **模型訓練與調參**：支持學習率調整與早停機制，確保模型有效收斂。
- **性能評估與可視化**：生成學習曲線與分類報告，輔助結果分析。
- **模型保存與部署**：保存最佳模型以供未來推理使用。

---

## 結果與展望

此專案成功訓練了一個基於 CNN 的多類別圖像分類模型，並實現了對測試集的準確預測。未來可嘗試更深層的模型架構，或引入數據增強技術以進一步提升性能。

---

## 附註

- 本專案基於 TensorFlow 2.x 開發，請確保 Python 版本為 3.9 或更高。
- 請確認數據集的目錄結構正確，避免運行錯誤。



