# CIFAR-10 Image Classification 🖼️

A Convolutional Neural Network (CNN) built with TensorFlow/Keras to classify images from the CIFAR-10 dataset into 10 categories.

## 📌 Classes
`airplane` • `automobile` • `bird` • `cat` • `deer` • `dog` • `frog` • `horse` • `ship` • `truck`

## 🏗️ Model Architecture

A deep CNN with 6 convolutional layers organized in 3 blocks:

| Block | Layers | Filters | Regularization |
|-------|--------|---------|----------------|
| Block 1 | Conv → BN → Conv → BN → MaxPool | 32 | Dropout(0.2) + L2 |
| Block 2 | Conv → BN → Conv → BN → MaxPool | 64 | Dropout(0.3) + L2 |
| Block 3 | Conv → BN → Conv → BN → MaxPool | 128 | Dropout(0.4) + L2 |
| Output | Flatten → Dense(10, softmax) | — | — |

## ⚙️ Training Details

| Parameter | Value |
|-----------|-------|
| Optimizer | Adam (lr=0.0001) |
| Loss | Categorical Crossentropy |
| Epochs | 50 (with early stopping) |
| Batch Size | 64 |

**Callbacks:** `EarlyStopping` · `ReduceLROnPlateau` · `ModelCheckpoint`

**Data Augmentation:** rotation, width/height shift, horizontal flip

## 📂 Project Structure

```
CIFAR-10-Image-Classification/
│
├── CIFAR-10_Image_Classification.ipynb   # Main notebook
├── requirements.txt                       # Python dependencies
├── .gitignore                             # Files to exclude from Git
└── README.md                              # This file
```

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/CIFAR-10-Image-Classification.git
cd CIFAR-10-Image-Classification
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Run the notebook
```bash
jupyter notebook CIFAR-10_Image_Classification.ipynb
```

> **Note:** The dataset is downloaded automatically via `tf.keras.datasets.cifar10`.

### 4. Predict on custom images
Place your image files (e.g., `test1.jpg`) in the project folder and run the `predict_external_image()` function at the bottom of the notebook.

## 📊 Results

Training produces:
- Accuracy & Loss curves (train vs. validation)
- Test set accuracy evaluation
- Confusion matrix across all 10 classes

## 🛠️ Requirements

- Python 3.8+
- TensorFlow 2.x
- scikit-learn
- OpenCV
- matplotlib / numpy
