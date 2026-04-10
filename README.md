# 🚀 Hybrid Intrusion Detection System (Autoencoder + Transformer)

## 📌 Overview
This project presents a **Hybrid Network Intrusion Detection System (NIDS)** that combines **unsupervised anomaly detection** using an Autoencoder with **supervised classification** using a Transformer-based neural network.

The system detects **malicious network traffic (attacks)** by leveraging:
- Reconstruction-based anomaly detection
- Deep learning-based classification

This hybrid approach improves detection performance and reduces false positives.

---

## 🧠 Key Features
- Hybrid model: Autoencoder + Transformer
- Detects unknown and known attacks
- Handles class imbalance
- Prevents data leakage
- GPU support using PyTorch
- Performance visualization

---

## 🛠️ Technologies & Frameworks Used

### 🔹 Programming Language
- Python

### 🔹 Libraries & Frameworks
- PyTorch (Deep Learning)
- NumPy (Numerical Computing)
- Pandas (Data Processing)
- Scikit-learn (Preprocessing & Evaluation)
- Matplotlib (Visualization)

---

## ⚙️ Algorithms & Techniques Used

### 1. Autoencoder (Unsupervised Learning)
- Learns patterns of **benign traffic**
- Detects anomalies using **reconstruction error**
- Uses **95th percentile threshold** for anomaly detection

### 2. Transformer Encoder (Supervised Learning)
- Uses **self-attention mechanism**
- Captures feature relationships
- Performs binary classification (Benign vs Attack)

### 3. Hybrid Decision Strategy
Final prediction is made using:
Final Prediction = AE Prediction OR Transformer Prediction


### 4. Data Preprocessing
- Power Transformation (to normalize distribution)
- Min-Max Scaling
- Missing value handling
- Infinite value removal

### 5. Class Imbalance Handling
- Weighted CrossEntropy Loss

---

## 📂 Project Workflow

Data Upload → Preprocessing → Train/Test Split →
Autoencoder Training → Threshold Calculation →
Transformer Training → Hybrid Evaluation → Metrics Visualization


---

## 📊 Module-wise Explanation

### 🔹 1. Data Loading Module
- Upload dataset using Google Colab
- Load CSV using Pandas
- Clean column names

---

### 🔹 2. Label Processing Module
- Convert multi-class labels into binary:
  - BENIGN → 0
  - ATTACK → 1

---

### 🔹 3. Feature Engineering Module
- Select only numerical features
- Handle:
  - Missing values
  - Infinite values

---

### 🔹 4. Data Splitting Module
- Use `train_test_split`
- Apply stratified sampling
- Prevent data leakage

---

### 🔹 5. Data Preprocessing Module
- **PowerTransformer**
  - Converts data to Gaussian-like distribution
- **MinMaxScaler**
  - Scales features to range [0,1]

---

### 🔹 6. DataLoader Module
- Convert data into PyTorch tensors
- Create batches for training

---

### 🔹 7. Autoencoder Module

#### 📌 Architecture
- Encoder: Input → 64 → 16
- Decoder: 16 → 64 → Output

#### 📌 Working
- Trained only on **benign data**
- Learns normal patterns
- Computes reconstruction error

---

### 🔹 8. Threshold Selection Module
- Calculate reconstruction error
- Use **95th percentile** as threshold
- Higher error → anomaly

---

### 🔹 9. Transformer Classifier Module

#### 📌 Architecture
- Linear embedding layer
- Transformer Encoder (self-attention)
- Fully connected classifier

#### 📌 Working
- Predict attack probability
- Uses softmax activation

---

### 🔹 10. Training Module

#### Autoencoder Training
- Loss Function: Mean Squared Error (MSE)
- Optimizer: Adam

#### Classifier Training
- Loss Function: Weighted CrossEntropy
- Handles class imbalance

---

### 🔹 11. Hybrid Decision Module
Combines both models:

- Autoencoder detects anomalies
- Transformer predicts attack probability

#### Final Rule:

Attack if:
(AE reconstruction error > threshold) OR (Transformer predicts attack)


---

### 🔹 12. Evaluation Module

#### Metrics Used:
- Accuracy
- Precision
- Recall (TPR)
- False Alarm Rate (FAR)
- True Negative Rate (TNR)

#### Confusion Matrix:
- TN (True Negative)
- FP (False Positive)
- FN (False Negative)
- TP (True Positive)

---

### 🔹 13. Visualization Module
- Bar chart showing:
  - Accuracy
  - Precision
  - Recall
  - FAR
  - TNR

---

## 📈 Results Interpretation
- High Recall → Better attack detection
- Low FAR → Fewer false alarms
- Balanced Precision & Recall → Reliable system

---

## ▶️ How to Run

1. Open Google Colab
2. Upload dataset (CSV file)
3. Run all cells
4. View output metrics and graph

---

## 📌 Future Improvements
- Use deeper Transformer models
- Hyperparameter tuning
- Real-time intrusion detection system
- Deployment using Flask / FastAPI
- Use larger datasets like CICIDS2017

---

## 📚 Dataset
- CICIDS2017
- NSL-KDD
- Other network intrusion datasets

---

## 👨‍💻 Author
**Iram Siddiquee**  
M.Tech in Artificial Intelligence & Machine Learning  
BIT Mesra  

---

## 📜 License
This project is for academic and research purposes only.
