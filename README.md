# LSTM Time Series Forecasting: COVID-19 Daily New Cases in Egypt

## Overview
This project applies a **Long Short-Term Memory (LSTM)** neural network to forecast **daily new COVID-19 cases in Egypt** based on past case data.  
It uses time series modeling techniques to capture temporal dependencies and predict future case counts.


**Dataset**: `egypt_daily_covid.csv`

**Columns:**
- `date`: Date of record
- `country`: Egypt
- `daily_new_cases`: Number of newly reported cases  

The dataset is sorted chronologically and split into:
- **80% training set**
- **20% testing set**

---

## Steps and Workflow
### 1. **Data Preprocessing**
- Handle missing values using forward fill.  
- Scale values to [0, 1] using `MinMaxScaler`.  
- Transform data into supervised learning format — use the previous 5 entries to predict the next.

### 2. **Model Architecture**
- Sequential LSTM model with:
  - Input layer  
  - Two LSTM layers
  - Dense hidden layer  
  - Dense output layer  
- Compiled using the **Adam optimizer** and **Mean Squared Error (MSE)** loss.  
- Uses **EarlyStopping** callback to prevent overfitting.

### 3. **Training and Evaluation**
- Trained the model on the training set for 8 epochs and validates it on the test set.  
- Evaluates model performance using **MSE** and visualizes predicted vs. actual values.

### 4. **Results**
  - mae: 0.0372
  - mse: 0.0034
  - val_mse: 7.0946e-04
  - val_mae: 0.0224 
<img width="990" height="374" alt="image" src="https://github.com/user-attachments/assets/e1e23b13-64de-45c4-ac3f-39955e1c06e8" />
<img width="630" height="470" alt="image" src="https://github.com/user-attachments/assets/b6cd651f-0867-4428-bed6-0590d2d7f59f" />

