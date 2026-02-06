# 🌬️ Anomaly Detection in Wind Turbine Time Series Data

### 🎯 Project Overview

This project implements a multi-model comparative approach to detect operational anomalies in wind turbine sensors. By analyzing high-frequency time-series data, the pipeline identifies equipment malfunctions and irregular behavioral patterns using both traditional unsupervised machine learning and modern deep learning techniques.

**Performance Achievement:**
The models successfully isolated critical fault points, with Deep Learning models (LSTM/GRU) identifying the most extreme 1% of operational deviations.

---

### 🏗️ Technical Workflow

**1. Data Preprocessing & Cleaning**
The pipeline processes raw sensor data from wind turbines, which often contains missing values due to sensor downtime:

* **Temporal Indexing**: Automatically identifies and sets datetime columns as the index for time-series consistency.
* **Imputation Strategy**: Employs Forward Fill (`ffill`) and Backward Fill (`bfill`) to maintain temporal continuity without introducing artificial mean bias.
* **Feature Scaling**: Utilizes both `StandardScaler` (for ML models) and `MinMaxScaler` (for Deep Learning) to normalize sensor readings like wind speed and power output.

**2. Traditional Machine Learning (Baseline)**
Three robust unsupervised algorithms were implemented to capture a wide range of outliers:

* **Isolation Forest**: Efficiently partitions data to isolate anomalies (348 anomalies detected).
* **Local Outlier Factor (LOF)**: Measures local density deviations compared to neighbors (297 anomalies detected).
* **One-Class SVM**: Learns a decision boundary for "normal" operational states (335 anomalies detected).

**3. Deep Learning Architecture (Sequence Modeling)**
To capture long-term dependencies and complex temporal patterns, the project uses Recurrent Neural Networks (RNNs):

* **LSTM (Long Short-Term Memory)**: A 50-unit architecture designed to remember patterns over long sequences.
* **GRU (Gated Recurrent Unit)**: A 64-unit architecture that provides similar performance to LSTM with higher computational efficiency.
* **Thresholding**: Anomalies are identified by calculating the Mean Squared Error (MSE) between predicted and actual values, flagging the 99th percentile of reconstruction errors.

---

### 📊 Key Results

The study revealed a significant difference in sensitivity between traditional and deep learning approaches:

| Model | Number of Anomalies Detected | Characteristics |
| --- | --- | --- |
| **Isolation Forest** | 348 | Captures broad operational outliers |
| **One-Class SVM** | 335 | Robust against high-dimensional noise |
| **Local Outlier Factor** | 297 | Detects local density deviations |
| **LSTM** | 33 | Flags only extreme/rare events |
| **GRU** | 33 | Precise identification of critical faults |

---

### 🛠️ Tech Stack

* **Language**: Python
* **Core Libraries**: Pandas, NumPy, Scikit-Learn
* **Deep Learning**: TensorFlow/Keras (LSTM, GRU)
* **Visualization**: Matplotlib
* **Data Source**: Excel-based Time Series (X-Minutal)

---

### 🚀 How to Run

1. **Clone the Repo**:
```bash
git clone https://github.com/YourUsername/Wind-Turbine-Anomaly-Detection.git

```


2. **Install Dependencies**:
```bash
pip install pandas numpy scikit-learn matplotlib tensorflow openpyxl

```


3. **Run the Script**:
Place your `.xlsx` data in the specified directory and execute:
```bash
python "Anomaly Detection in Wind Turbine Time Series Data.py"

```



---

## Contact  
Balaji V | AI/ML Engineer | Tiruppur, Tamil Nadu, India  
📧 balajivasanthakumar2001@gmail.com | 🔗 [LinkedIn](https://linkedin.com/in/balaji-v-2001)
