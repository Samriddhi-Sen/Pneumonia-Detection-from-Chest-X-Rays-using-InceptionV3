# Pneumonia-Detection-from-Chest-X-Rays-using-InceptionV3

This project uses the [MedMNIST](https://medmnist.com/) `PneumoniaMNIST` dataset to train and evaluate deep learning models for detecting pneumonia from chest X-ray images.
This project implements a deep learning model based on InceptionV3 architecture to detect pneumonia from chest X-ray images using the PneumoniaMNIST dataset. The model achieves 78.85% accuracy and demonstrates the potential of transfer learning for medical image classification tasks.

## Dataset

- **Source:** [MedMNIST](https://medmnist.com/)
- **Dataset:** PneumoniaMNIST
- Contains grayscale chest X-ray images classified into:
  - `0`: Normal
  - `1`: Pneumonia

## Model

- Pre-trained models from `torchvision.models` (e.g., ResNet18)
- Fine-tuned on PneumoniaMNIST
- Metrics evaluated: Accuracy, Precision, Recall, F1-Score, Confusion Matrix

## Dependencies

```bash
pip install medmnist torch torchvision matplotlib seaborn pandas numpy scikit-learn
```
# Hyperparameter Choices

This document outlines the hyperparameters used during the fine-tuning of the InceptionV3 model for pneumonia detection.

- **Learning Rate:** 0.001
*   Used with the Adam optimizer. This rate was chosen as a common effective starting point for Adam, balancing convergence speed and stability.

- **Batch Size:** 128
*   Selected for efficient processing on the GPU while providing a good gradient approximation.

- **Epochs:** 10
*   Determined to allow sufficient training for convergence without causing overfitting, especially given the dataset size and transfer learning approach.

## Running the Notebook

1. Clone this repository or download the notebook.
2. Run all cells in the notebook `PneumoniaMNIST_Samriddhi_Sen.ipynb`.
3. Visualizations, model training logs, and evaluation metrics will be displayed inline.

## Results

Evaluation includes:
- Classification metrics: Accuracy, Precision, Recall, F1
- Confusion Matrix
- Training and validation loss/accuracy curves

## Author

- **Samriddhi Sen**

