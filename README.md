# DDoS Attack Detection and Mitigation in SDN using Random Forest

This project implements a **Machine Learning-based framework for detecting and mitigating Distributed Denial of Service (DDoS) attacks in Software Defined Networks (SDN)** using the Random Forest classifier.

The system analyzes network traffic flow features and classifies them as **normal traffic or malicious DDoS traffic**, enabling real-time mitigation through SDN controllers.

---

# Overview

Distributed Denial of Service (DDoS) attacks are a major threat to modern networks. These attacks overwhelm servers with massive traffic, causing service disruption and financial losses.

Software Defined Networking (SDN) provides a flexible and programmable architecture where machine learning models can be integrated for **real-time network security monitoring and automated mitigation**.

This project combines:

- SDN architecture
- Random Forest Machine Learning
- Network flow feature analysis
- Feature engineering techniques

to detect and mitigate DDoS attacks effectively.

---

# System Architecture

The proposed system consists of the following components:

1. **Network Traffic Monitoring**
   - Collect flow statistics from SDN switches.

2. **Feature Extraction**
   - Extract traffic features such as packet count, byte count, duration, and flow statistics.

3. **Machine Learning Model**
   - Random Forest classifier trained on labeled traffic data.

4. **Attack Detection**
   - Model classifies traffic as normal or malicious.

5. **Mitigation**
   - SDN controller dynamically updates flow rules to block malicious traffic.

---

# Dataset

The dataset used is the **SDN DDoS dataset from Kaggle**, which contains multiple network traffic features used to train the model. :contentReference[oaicite:1]{index=1}

### Key Features

- Packet Count
- Byte Count
- Flow Duration
- Source IP
- Destination IP
- Packet Rate
- Port Number
- Protocol
- Transmission Rate
- Label (0 = Normal, 1 = DDoS)

Each row represents a network flow with traffic statistics used for classification.

---

# Feature Engineering

To improve model accuracy, feature engineering techniques were applied.

### Packet Byte Ratio (PBR)

A new feature was introduced:

PBR = Packet Count / Byte Count

This helps reduce correlation between packet count and byte count while preserving important information for classification. :contentReference[oaicite:2]{index=2}

---

# Machine Learning Model

The system uses a **Random Forest classifier** because:

- Works well with tabular data
- Handles nonlinear relationships
- Robust to noise
- Provides feature importance insights

### Hyperparameter tuning

Randomized Search Cross Validation was used to optimize:

- Number of estimators
- Tree depth
- Minimum samples per split
- Minimum samples per leaf

Cross-validation method used:

Repeated Stratified K-Fold

---

# Model Training Pipeline

1. Data preprocessing
2. Handling missing values
3. Exploratory Data Analysis
4. Correlation analysis
5. Feature engineering (PBR)
6. Feature scaling
7. Model training
8. Hyperparameter tuning
9. Model evaluation

---

# Results

The model achieved extremely high detection accuracy.

### Key metrics

- Training Accuracy: **~100%**
- Test Accuracy: **~99.9%**
- Precision: **>99%**
- Recall: **>99%**

The confusion matrix shows very low false positives and false negatives.

---

# Technologies Used

- Python
- Scikit-learn
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Mininet (SDN Simulation)
- Ryu Controller

---

