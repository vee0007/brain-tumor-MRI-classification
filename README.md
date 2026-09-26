# Brain Tumor MRI Classification Using Machine Learning

A classical machine learning project for classifying brain MRI images into four categories: **Glioma, Meningioma, Pituitary, and No Tumor**.

## Project Overview

The project uses image preprocessing and handcrafted image features, followed by an Extra Trees classifier.

**Workflow:** MRI Image → Preprocessing → Feature Extraction → Feature Selection → Extra Trees → Prediction

## Dataset

**Brain Tumor MRI Dataset** from Kaggle:

https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset

- Training images: 5,600
- Test images: 1,600
- Classes: Glioma, Meningioma, No Tumor, Pituitary

## Preprocessing

- Grayscale conversion
- Resize to 128 × 128
- Gaussian blur
- Normalization

## Feature Extraction

### GLCM
Contrast, dissimilarity, homogeneity, energy, correlation.

### Intensity
Mean, standard deviation, variance, minimum, maximum, median.

### HOG
Histogram of Oriented Gradients for edge and shape information.

The combined feature vector contains **1,775 features**.

## Feature Selection

Extra Trees feature importance was used to select the most useful features.

| Features | Accuracy |
|---:|---:|
| 250 | 91.79% |
| **500** | **92.59%** |
| 750 | 92.05% |
| 1000 | 92.14% |

The top **500 features** were selected.

## Model

**Extra Trees Classifier** was used as the final model.

RandomizedSearchCV was used for hyperparameter tuning.

- Validation accuracy: **93.30%**
- Official test accuracy: **87.00%**

## Final Test Results

| Class | Precision | Recall | F1-Score |
|---|---:|---:|---:|
| Glioma | 0.93 | 0.66 | 0.77 |
| Meningioma | 0.82 | 0.85 | 0.84 |
| No Tumor | 0.84 | 1.00 | 0.91 |
| Pituitary | 0.91 | 0.97 | 0.94 |
| **Overall** | **0.88** | **0.87** | **0.87** |

### Final Accuracy: 87%

## Single Image Prediction

The trained model can accept a single uploaded MRI image and predict its class.

1. Upload an MRI image.
2. Apply the same preprocessing.
3. Extract GLCM + intensity + HOG features.
4. Select the top 500 features.
5. Predict using the trained Extra Trees model.
6. Display the predicted class and probabilities.

## Technologies Used

Python, Google Colab, OpenCV, NumPy, Pandas, Scikit-learn, Matplotlib, and scikit-image.

## Project Structure

```text
brain-tumor-mri-classification/
├── Brain_Tumor_MRI_Classification.ipynb
├── README.md
├── Brain_Tumor_MRI_Classification_Report.pdf
└── results/
    └── confusion_matrix.png
```

## How to Run

1. Open the notebook in Google Colab.
2. Download/use the dataset from Kaggle.
3. Run the notebook cells in order.
4. Train the model.
5. Evaluate it on the official test set.
6. Use the single-image prediction section to test a new MRI image.

## Limitations

This is an educational machine learning project. It is not a medical diagnostic system and should not be used for clinical decisions.

## Author

**Rohit Verma**  
B.Tech Computer Science & Engineering
