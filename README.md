# 🩸 Non-Invasive Anemia Detection Using Deep Learning on Ocular Images

## 📌 Overview
Anemia is a widespread global health condition that affects millions of people, particularly children and pregnant women. Conventional diagnosis relies on invasive blood tests, which are costly, time-consuming, and difficult to scale in low-resource settings.<br><br>

This project presents a **non-invasive deep learning–based approach for anemia screening using images of the human eye**. By analyzing ocular images, the system aims to provide an accessible and low-cost alternative to traditional diagnostic methods.

---

## 🎯 Objectives
- Develop deep learning models for **non-invasive anemia detection**  
- Compare multiple **pretrained CNN architectures**  
- Evaluate **ensemble learning** to improve clinical reliability  
- Address **class imbalance** commonly found in medical datasets  
- Prioritize **high recall for anemic cases** to minimize false negatives  

---

## 🧠 Models Implemented

### Individual Models
- **VGG16**
- **DenseNet121**
- **InceptionV3**

<br>

### Ensemble Models
- **VGG16 + DenseNet121 + InceptionV3**
- **DenseNet121 + InceptionV3**

Ensemble predictions are generated using **probability averaging**, allowing the system to leverage complementary feature representations learned by different architectures.

---

## 📊 Dataset
- **Input:** Ocular (eye / conjunctiva) images  
- **Classes:**  
  - Anemic  
  - Non-Anemic  

<br>

**Class Distribution:** ~3:1 (Non-Anemic : Anemic)  

**Key Challenge:** Severe class imbalance  

The dataset reflects **real-world screening scenarios**, making **recall-oriented evaluation essential**.

---

## ⚙️ Preprocessing
The following preprocessing steps were applied before training:

- Image resizing to **model-specific input dimensions**
- **Pixel normalization**
- **Data augmentation**
  - Rotation
  - Horizontal flipping
  - Zoom
- **Stratified train–validation–test split**

These steps help improve generalization and reduce overfitting.

---

## 📈 Evaluation Metrics

The models were evaluated using the following metrics:

- **Accuracy**
- **Precision**
- **Recall**
- **F1-Score**
- **Mean Squared Error (MSE)**
- **Standard Deviation across validation folds**

<br>

⚠️ **Recall for the anemic class was treated as the most critical metric**, since missing an anemic patient can have serious clinical consequences.

---

## 🧪 Results Summary

### Individual Models

**InceptionV3** achieved the best standalone performance:

- ~71% Accuracy  
- Lowest MSE  
- Most stable results across folds  

<br>

**VGG16** and **DenseNet121** showed **limited recall for anemic cases**, highlighting the impact of class imbalance.

---

### Ensemble Models

#### ⭐ VGG16 + DenseNet121 + InceptionV3 (Best Model)
- **84% Accuracy**
- **0.75 Recall for Anemic Class**
- Best **F1-Scores** across both classes

<br>

#### DenseNet121 + InceptionV3
- **81% Accuracy**
- Lower computational cost  
- Reduced recall for anemic class compared to the three-model ensemble  

---

## 🔑 Key Insight
Ensemble learning **significantly improves diagnostic reliability** and mitigates weaknesses of individual models.<br><br>
This makes ensemble models **more suitable for medical screening applications**, where reliability and safety are crucial.

---

## 🏥 Medical Relevance
- **False negatives** (missing anemic patients) are more dangerous than false positives  
- **High recall for anemic cases** is essential for safe screening  
- **Ensemble models provide better clinical reliability** compared to individual CNN models  

---

## 🛠️ Tools & Technologies

**Language**
- Python

<br>

**Frameworks**
- TensorFlow
- Keras

<br>

**Libraries**
- NumPy
- OpenCV
- Scikit-learn
- Matplotlib

<br>

**Hardware**
- GPU recommended for faster training

---

## 🚀 How to Run

### 1️⃣ Clone the Repository
```bash
git clone <repository-url>
cd anemia-detection
```

### 2️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

### 3️⃣ Train the Model
```bash
python train.py
```

### 4️⃣ Evaluate the Model
```bash
python evaluate.py
```

---

## 📌 Future Improvements
- Incorporating **larger and more diverse datasets**
- Applying **advanced imbalance handling techniques (e.g., SMOTE, focal loss)**
- Deploying the model in **mobile or web-based screening tools**
- Clinical validation with **real-world healthcare datasets**

---

## 📜 License
This project is intended for **research and educational purposes**.  
Please ensure proper validation before clinical deployment.

---

## 👩‍💻 Author
**Tanishka Gupta**  
Data Science & AI Enthusiast

---

⭐ If you find this project useful, consider **starring the repository**!
