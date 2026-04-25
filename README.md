# ⚡ Energy Consumption Forecasting — Model Comparison 📈

## 🌟 Overview
Welcome to the Energy Consumption Forecasting project! This repository contains an end-to-end Jupyter Notebook (`Energy-Consumption-Forecasting.ipynb`) that predicts hourly energy consumption using historical AEP (American Electric Power) data. It implements, trains, and evaluates four different deep learning architectures to compare their performance in time-series forecasting. 

## 📊 Dataset Details
* **📥 Source**: `robikscube/hourly-energy-consumption` dataset fetched directly via the `kagglehub` library.
* **🎯 Target Variable**: `AEP_MW` (American Electric Power consumption in Megawatts).
* **⚙️ Feature Engineering**: Incorporates cyclical temporal features (sine/cosine transformations of hour, day of week, and month) alongside the target variable to help the models understand daily, weekly, and seasonal patterns.
* **⏱️ Sequence Length**: 168 hours (1 week of historical data used to predict the exact next hour).

## 🧠 Models Implemented
The following models were built using **PyTorch**, all processing sequences of length 168 with 7 input features to output a single scalar prediction:

1. 🔄 **RNN Model**: A bidirectional Recurrent Neural Network.
2. 💾 **LSTM Model**: A bidirectional Long Short-Term Memory network.
3. 🚪 **GRU Model**: A bidirectional Gated Recurrent Unit network.
4. 🤖 **Transformer Model**: A Transformer Encoder network leveraging Positional Encoding.

*Note: All models utilize a Huber Loss criterion, the Adam optimizer with a `ReduceLROnPlateau` learning rate scheduler, and Early Stopping to prevent over-fitting!*

## 🏆 Experimental Results
The models were evaluated using Root Mean Squared Error (RMSE) and Mean Absolute Error (MAE). Here is how they stacked up against the test set:

| Model         | RMSE       | MAE        |
|---------------|------------|------------|
| 🥇 **RNN** | 208.4643   | 156.3191   |
| 🥈 **LSTM** | 221.7890   | 172.7746   |
| 🥉 **GRU** | 227.5806   | 175.4811   |
| 🏅 **Transformer** | 237.3446 | 179.7230   |

*(💡 The exact evaluation numbers might slightly vary due to hardware configurations and random initialization upon re-running the notebook).*

## 🛠️ Dependencies
The notebook installs and uses the following libraries. No manual setup required!
* `torch` 🔥
* `pandas` 🐼
* `numpy` 🔢
* `scikit-learn` 🔬
* `matplotlib` 📉
* `kagglehub` 🌐

## 🚀 Execution Guide
This notebook is designed to run seamlessly in **Google Colab**! 
1. Open the notebook in Colab.
2. Ensure GPU acceleration is turned on (T4 recommended for faster training).
3. Hit **Run All**. 

The script will automatically download the dataset, preprocess the data, train the four models consecutively, print the comparison metrics, and finally save a plot titled `electricity_forecast_results.png` which visually compares the predictions against the actual consumption! 🎉

---

## 👨‍💻 Author
**Name**: Raj Fatehveer Singh Brar<br>
**Roll Number**: 102317090<br>
**Email ID**: rbrar_be23@thapar.edu<br>
**University**: Thapar Institute of Engineering and Technology
