# **Beer Rating Prediction**  
*Predicting beer ratings based on reviews, attributes, and user information.*

---

## **Table of Contents**  
1. [**Problem Statement**](#problem-statement)  
2. [**Dataset**](#dataset)  
3. [**Approach**](#approach)  
4. [**Feature Engineering**](#feature-engineering)  
5. [**Model Training**](#model-training)  
6. [**Results**](#results)  
7. [**How to Use**](#how-to-use)  
8. [**Future Improvements**](#future-improvements)  

---

## **Problem Statement**  
**Goal**: Predict the **overall beer rating (`review/overall`)** from a dataset of beer reviews and attributes using machine learning techniques. The task is treated as a **regression problem**.

---

## **Dataset**  
The dataset includes:  

- **Textual Data**: `review/text`  
- **Categorical Data**: `beer/name`, `beer/style`, `user/gender`  
- **Numeric Data**: `beer/ABV`, `review/appearance`, `review/aroma`, `review/palate`, `review/taste`, `user/ageInSeconds`, `review/timeUnix`  

---

## **Approach**  

### **1. Data Cleaning**  
- Handled missing values for textual, numeric, and categorical features.  
- Normalized timestamps (`review/timeUnix`) to align them with other numeric features.  

### **2. Feature Engineering**  
- **Text Features**: Processed `review/text` using **TF-IDF Vectorization**.  
- **Categorical Features**:  
  - Encoded `beer/name`, `beer/style`, and `user/gender` using **One-Hot Encoding**.  
- **Numeric Features**: Standardized features like `beer/ABV`, `review/appearance`, etc., to ensure uniform scaling.  

### **3. Model Training**  
- Used **Random Forest Regressor** for prediction.  
- Evaluated using **Mean Squared Error (MSE)** and **R² Score**.

---

## **Feature Engineering**  

### **Text Processing**  
- **TF-IDF Vectorization**: Extracted the 100 most important terms from `review/text` to generate numeric features.  

### **Categorical Encoding**  
- **One-Hot Encoding**: Applied to high-cardinality categorical features (`beer/name`, `beer/style`).  

### **Numeric Features**  
- **Standardization**: Used to normalize `beer/ABV`, `review/appearance`, etc.  
- **Normalized Timestamps**: Converted `review/timeUnix` into a numeric feature for temporal analysis.  

---

## **Model Training**  

- **Algorithm**: Random Forest Regressor  
- **Train-Test Split**: 80-20 split for training and testing.  
- **Hyperparameters**:  
  - **Number of Trees (`n_estimators`)**: 50  
  - **Random State**: 42  

---

## **Results**  

- **Mean Squared Error (MSE)**: *Calculated during testing.*  
- **R² Score**: *Calculated during testing.*  

### **Feature Importance**  
- Top contributors include:  
  - **`beer/ABV`**  
  - **`review/aroma`**  
  - Key terms from **`review/text`**.  
