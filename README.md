# 📈 Stock Price Prediction

This project focuses on predicting stock prices using deep learning techniques, particularly a neural network model trained on historical stock data. The dataset includes daily stock values such as Open, High, Low, Close, Volume, and Adjusted Close prices over multiple years.

## 📊 Data

The dataset contains **1,825 entries** spanning several years, with the following key columns:

- `Date`
- `High`
- `Low`
- `Open`
- `Close`
- `Volume`
- `Adj Close`

### Key Data Insights

- **No missing values** detected across all columns.
- **Descriptive statistics**:
  - **High**: Mean = 2660.72, Std = 409.68, Min = 1847.00, Max = 3645.99
  - **Low**: Mean = 2632.82, Min = 1810.10, Max = 3600.16
  - **Volume**: Ranges from ~1.3B to 9B with a mean around 3.87B
- **Stationarity Check**:
  - Augmented Dickey-Fuller test: **Statistic = 2.07, p-value = 0.038** → Suggests the series may be stationary
  - KPSS test: **Statistic = 1.43, p-value = 0.231** → Supports weak stationarity

## 🧠 Model

The model is a deep neural network trained using a sequence of epochs with decreasing loss values.

### Training Log (Loss)

| Epoch | Loss     |
|-------|----------|
| 1     | 0.0098   |
| 2     | 0.0015   |
| 3     | 0.0017   |
| 4     | 0.0012   |
| 5     | 0.0011   |
| 6     | 0.0012   |
| 7     | 0.0013   |
| 8     | 0.0012   |
| 9     | 0.00098  |
| 10    | 0.00097  |

> Training over 10 epochs shows consistent improvement and loss reduction.

### Evaluation Metrics

| Set   | RMSE       | MAE         |
|--------|------------|-------------|
| Train  | 49.43      | 40.80       |
| Test   | 97.28      | 80.37       |

> The test RMSE and MAE are higher than training, indicating potential **overfitting** or **data variability**.

### Predictions

- Model evaluated on new data across multiple batches (sample output logs).
- Inference speed is efficient, averaging **30ms per prediction**.

## 📁 Notebooks

- [`Stock_Price_Prediction.ipynb`](./Stock_Price_Prediction.ipynb): Full implementation of data processing, modeling, training, and evaluation pipeline.

## 📦 Requirements

Install dependencies with:

```bash
pip install -r requirements.txt
