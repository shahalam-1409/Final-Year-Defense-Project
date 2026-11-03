# Final-Year-Defense-Project
# 🌾 RiceDT — Lightweight CNN-Based Rice Leaf Disease Detection

### Lightweight CNN Model for Real-Time Rice Leaf Disease Detection on Mobile Devices

RiceDT is a deep learning-based rice leaf disease detection system developed as a **Final Year Design Project (FYDP)** at Daffodil International University.

The project focuses on developing a lightweight Convolutional Neural Network (CNN) for classifying rice leaf diseases and deploying the trained model on Android mobile devices using TensorFlow Lite and Flutter.

The proposed system combines image preprocessing, deep learning, model evaluation, explainable AI, and mobile deployment to support efficient rice leaf disease identification.

---

## 📌 Project Overview

Rice is one of the most important agricultural crops in Bangladesh. However, various diseases affect rice production and can cause significant economic losses. Early identification of these diseases can help farmers take appropriate preventive measures.

RiceDT aims to provide a lightweight and mobile-based solution that can identify rice leaf diseases directly from images.

**Key objectives:**

- Develop a lightweight CNN architecture for rice leaf disease classification.
- Apply image preprocessing and enhancement techniques to improve input image quality.
- Evaluate the proposed model against established lightweight CNN architectures.
- Analyze model performance and computational complexity.
- Apply explainable AI techniques to understand model predictions.
- Convert the trained model into TensorFlow Lite format.
- Integrate the model into a Flutter-based mobile application.

---

## ✨ Key Features

- 🌱 Classification of five rice leaf categories.
- 🧠 Custom lightweight CNN architecture.
- 🖼️ Image preprocessing and enhancement.
- 📊 Model evaluation and performance comparison.
- 🔍 Explainable AI using Grad-CAM and Grad-CAM++.
- ⚡ TensorFlow Lite model integration.
- 📱 Flutter-based mobile application.
- 📷 Rice leaf image input through camera or gallery.
- 📲 On-device disease prediction.

---

## 🌿 Supported Disease Classes

The system supports five categories:

| Class | Description |
|---|---|
| Bacterial Blight | Bacterial infection affecting rice leaves |
| Blast | Fungal disease affecting rice plants |
| Brown Spot | Fungal disease characterized by brown spots |
| Healthy | Healthy rice leaves |
| Tungro | Viral disease affecting rice plants |

---

## 📂 Dataset Information

The final dataset contains **4,212 images** distributed across five classes.

| Disease Class | Training | Validation | Testing | Total |
|---|---:|---:|---:|---:|
| Bacterial Blight | 656 | 82 | 83 | 821 |
| Blast | 621 | 77 | 79 | 777 |
| Brown Spot | 536 | 67 | 69 | 672 |
| Healthy | 774 | 96 | 98 | 968 |
| Tungro | 779 | 97 | 98 | 974 |
| **Total** | **3,366** | **419** | **427** | **4,212** |

### Dataset Sources

The dataset was prepared using publicly available rice disease image sources:

1. P. K. Sethy, *Rice Leaf Disease Image Samples*, Mendeley Data, vol. 2, July 2024.  
   DOI: https://doi.org/10.17632/fwcj7stb8r.2

2. M. M. Hasan, *Rice Leaf Disease DataSet*, Kaggle, 2023.

**Note:** The complete dataset is not included in this repository. Users should obtain the datasets from their original sources and follow their respective usage licenses.

---

## 🖼️ Image Preprocessing

Image preprocessing is applied to improve image quality and prepare the input images for model training and classification.

The project explores the following preprocessing techniques:

- Image resizing
- White balance correction
- Contrast Limited Adaptive Histogram Equalization (CLAHE)
- Bilateral filtering
- Unsharp masking
- HSV color enhancement
- Data augmentation

### Preprocessing Workflow

The documented final preprocessing pipeline is:

```text
Original Rice Leaf Image
          |
          v
    Center Crop (90%)
          |
          v
    Resize (256 × 256)
          |
          v
         CLAHE
          |
          v
     White Balance
          |
          v
  Bilateral Filtering
          |
          v
   HSV Enhancement
          |
          v
    Resize (224 × 224)
          |
          v
    Tensor Conversion
          |
          v
 ImageNet Normalization
          |
          v
      CNN Model
```

Data augmentation is applied to training images to improve model generalization. Validation and testing images are not augmented.

---

## 🧠 Deep Learning Models

The project investigates multiple lightweight CNN architectures to evaluate their suitability for rice leaf disease classification and mobile deployment.

### Models Evaluated

| Model | Description |
|---|---|
| MobileNetV2 | Lightweight CNN architecture |
| MobileNetV3-Small | Compact mobile-oriented CNN |
| MobileNetV3-Large | Mobile-oriented CNN architecture |
| EfficientNet-B0 | Efficient convolutional neural network |
| GhostNet | Lightweight CNN architecture |
| RiceDT | Proposed Custom Lightweight CNN |

### Proposed RiceDT Architecture

The proposed RiceDT model incorporates lightweight architectural components designed to reduce computational requirements.

**Main architectural components:**

- Depthwise-Separable Convolution
- Squeeze-and-Excitation Attention
- Residual Skip Connections
- HardSwish Activation
- Global Average Pooling

The model uses a 224 × 224 input size and supports five output classes.

---

## 📊 Model Evaluation

The project includes a comprehensive evaluation process to analyze classification performance and computational efficiency.

### Classification Metrics

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix
- Training and Validation Loss
- Training and Validation Accuracy

### Computational Analysis

The notebook also includes model complexity and performance analysis:

- Total Parameters
- Trainable Parameters
- Model Size
- FLOPs / MACs
- Inference Time
- Computational Efficiency

### Cross-Validation

The project includes a **5-Fold Stratified Cross-Validation** procedure for the proposed RiceDT model.

The existing test set is kept separate from the cross-validation process.

*Detailed experimental results and benchmark values should be taken from the final executed notebook and project report.*

---

## 🔍 Explainable AI (XAI)

To improve the interpretability of deep learning predictions, the project explores explainable AI techniques.

### Grad-CAM

Gradient-weighted Class Activation Mapping (Grad-CAM) helps visualize important image regions that influence a model's prediction.

### Grad-CAM++

Grad-CAM++ provides an enhanced class activation mapping approach for understanding the visual regions associated with model predictions.

These techniques help investigate whether the model focuses on relevant rice leaf regions during classification.

---

## 📱 Mobile Application

RiceDT includes a Flutter-based mobile application that integrates the trained TensorFlow Lite model.

### Application Features

- Capture images using the mobile camera.
- Select images from the device gallery.
- Perform rice leaf disease classification.
- Run model inference directly on the mobile device.
- Display the predicted disease category.

### Mobile Application Workflow

```text
       Open RiceDT App
              |
              v
       Select Image Source
              |
        +-----+-----+
        |           |
      Camera      Gallery
        |           |
        +-----+-----+
              |
              v
       Image Processing
              |
              v
       TensorFlow Lite
              |
              v
       Disease Prediction
              |
              v
       Display Result
```

### Integrated Model Files

The mobile application includes the following TensorFlow Lite models:

- `ricedt_float32.tflite`
- `mobilenetv3_se_float32.tflite`

The model labels are stored in:

`assets/labels/label.txt`

---

## 🛠️ Technologies Used

| Category | Technologies |
|---|---|
| Programming Language | Python, Dart |
| Deep Learning | PyTorch |
| Mobile Framework | Flutter |
| Model Deployment | TensorFlow Lite |
| Image Processing | OpenCV, PIL |
| Data Analysis | NumPy, Pandas |
| Visualization | Matplotlib, Seaborn |
| Explainable AI | Grad-CAM, Grad-CAM++ |
| Development Environment | Google Colab, Android Studio |

---

## 📁 Repository Structure

```text
RiceDT-FYDP/
│
├── Notebook/
│   └── Final Notebook.ipynb
│
├── Mobile_App/
│   └── rice_dt/
│       ├── android/
│       ├── ios/
│       ├── lib/
│       ├── assets/
│       │   ├── icons/
│       │   ├── labels/
│       │   └── models/
│       │       ├── ric edt_float32.tflite
│       │       └── mobilenetv3_se_float32.tflite
│       ├── pubspec.yaml
│       └── README.md
│
├── Project_Report/
│   └── Report.pdf
│
└── README.md
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/RiceDT.git
```

### 2. Navigate to the Project

```bash
cd RiceDT
```

### 3. Open the Notebook

Open the following file using Jupyter Notebook or Google Colab:

```text
Notebook/Final Notebook.ipynb
```

Configure the dataset directory according to your environment before running the notebook.

### 4. Run the Flutter Application

Navigate to the Flutter project directory:

```bash
cd Mobile_App/rice_dt
```

Install the required dependencies:

```bash
flutter pub get
```

Check the Flutter environment:

```bash
flutter doctor
```

Connect an Android device or start an emulator, then run:

```bash
flutter run
```

---

## 📄 Project Documentation

The complete project documentation is available in:

`Project_Report/Report.pdf`

The research notebook is available in:

`Notebook/Final Notebook.ipynb`

---

## 🎯 Project Goal

The ultimate goal of RiceDT is to explore an efficient and practical deep learning approach for rice leaf disease classification by combining lightweight CNN architecture, explainable AI, and mobile-based deployment.

The project focuses on bringing deep learning-based agricultural disease identification closer to practical mobile applications.

---

## 👨‍💻 Project Information

**Project Name:** RiceDT

**Project Title:** Lightweight CNN Model for Real-Time Rice Leaf Disease Detection on Mobile Devices

**Project Type:** Final Year Design Project (FYDP)

**Department:** Computer Science and Engineering (CSE)

**University:** Daffodil International University (DIU)

---

## 📜 License

No open-source license has been specified yet. Please contact the project authors for permission before reusing or redistributing the project materials.

---

## ⭐ Support

If you find this project interesting, consider giving the repository a star ⭐ on GitHub.

Thank you for visiting RiceDT!

