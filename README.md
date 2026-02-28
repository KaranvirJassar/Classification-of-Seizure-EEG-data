---

# 🧠 EEG Seizure Detection using CNN and CWT

This project implements an automated seizure detection system using EEG (Electroencephalogram) signals. A 1D Convolutional Neural Network (CNN) is trained to classify EEG segments into seizure and non-seizure classes. Continuous Wavelet Transform (CWT) is also applied for time-frequency analysis and scalogram visualization.

---

## 📂 Dataset

**Dataset Used:** Epileptic Seizure Recognition Dataset

* 178 EEG features per sample
* 1 label column (`y`)
* 5 original classes
* Balanced distribution
* Total samples: ~6300
* Dataset shape: `(6326, 180)`

### Class Meaning

| Label | Description        |
| ----- | ------------------ |
| 1     | Seizure            |
| 2     | Tumor region       |
| 3     | Healthy brain area |
| 4     | Eyes closed        |
| 5     | Eyes open          |

For seizure detection, the labels were converted to binary:

* `1` → Seizure
* `0` → Non-seizure (2,3,4,5)

---

## ⚙️ Methodology

### 1️⃣ Data Preprocessing

* Removed unnecessary column (`Unnamed`)
* Converted multi-class problem into binary classification
* Applied SMOTEENN for class balancing
* Standardized features using `StandardScaler`
* Split into Train / Validation / Test sets

---

### 2️⃣ Model Architecture (1D CNN)

The CNN architecture consists of:

* Conv1D (32 filters, kernel size = 3, ReLU)
* MaxPooling1D
* Conv1D (64 filters, ReLU)
* Conv1D (32 filters, ReLU)
* MaxPooling1D
* Dropout (0.25)
* Flatten
* Dense (32 units, ReLU)
* Dense (16 units, ReLU)
* Dropout (0.5)
* Output Layer (Sigmoid)

**Loss Function:** Binary Crossentropy
**Optimizer:** Adam
**Regularization:** Dropout + Early Stopping

---

## 📊 Results

* Training Accuracy: ~99%
* Validation Accuracy: ~97–98%
* Stable convergence
* No major overfitting observed

---

## 📈 Time-Frequency Analysis (CWT)

Continuous Wavelet Transform (CWT) was applied to generate scalograms for EEG signal visualization.

This provides:

* Time-frequency representation
* Better understanding of seizure patterns
* Visual comparison between seizure and normal EEG signals

---

## 🛠 Technologies Used

* Python
* TensorFlow / Keras
* Scikit-learn
* NumPy
* Pandas
* Matplotlib
* Seaborn
* PyWavelets

---

## 🚀 How to Run

1. Clone the repository:

```bash
git clone https://github.com/KaranvirJassar/Classification-of-Seizure-EEG-data.git
```

2. Open the notebook in Google Colab

3. Upload the dataset file:

```
Epileptic Seizure Recognition.csv
```

4. Run all cells

---

## 🎯 Future Improvements

* Train 2D CNN on CWT scalograms
* Implement CNN + LSTM hybrid model
* Perform K-fold cross-validation
* Deploy as a web application

---

## 👤 Author

Karanvir Singh Jassar
Machine Learning & Signal Processing Enthusiast

---

I’ll adjust formatting accordingly.
