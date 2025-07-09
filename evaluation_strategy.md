# Evaluation Strategy

This section details the evaluation strategy employed for the pneumonia detection model, including the chosen metrics, handling of class imbalance, and measures taken to prevent overfitting.

## a. Chosen Metrics and Justification

I chose the following metrics to evaluate the model's performance on the test set:

* **Accuracy:** Measures the overall proportion of correctly classified cases. It provides a general sense of the model's performance but can be misleading in imbalanced datasets.
* **Recall (Sensitivity):** Measures the proportion of actual positive cases (Pneumonia) that were correctly identified. In a clinical context, high recall is crucial to minimize false negatives and ensure patients with pneumonia receive treatment.
* **Precision (Positive Predictive Value):** Measures the proportion of predicted positive cases (Pneumonia) that were actually positive. High precision helps reduce false positives, avoiding unnecessary interventions or anxiety for patients.

I also reported the **F1-score** (harmonic mean of Precision and Recall) and the **Confusion Matrix** for a more comprehensive understanding of the model's performance across classes. Recall was considered particularly important given the clinical need to identify as many true pneumonia cases as possible.

## b. Class Imbalance Detection and Mitigation

**Detection:**  
Class imbalance in the training dataset was detected by calculating and printing the value counts and percentages of each class. The analysis revealed that the training set is imbalanced, with Class 1 (Pneumonia) representing approximately 74.21% of the data and Class 0 (Normal) representing approximately 25.79%.

**Mitigation:**  
In the current implementation, specific mitigation techniques for class imbalance, such as oversampling the minority class or undersampling the majority class, were not explicitly implemented. However, this imbalance was noted as a factor that could influence model performance, particularly on the minority class, and is identified as an area for future work to potentially improve the model's performance and fairness across classes.

## c. Measures Taken to Prevent Overfitting

Several measures were taken to prevent the model from overfitting to the training data:

* **Transfer Learning:** Using a pre-trained InceptionV3 model leverages features learned from a vast dataset (ImageNet), providing a strong foundation and reducing the need to study all features from scratch on the smaller PneumoniaMNIST dataset.
* **Freezing Layers:** The majority of the pre-trained InceptionV3 layers were frozen, allowing only the final classification layer(s) to be trained on the PneumoniaMNIST data. This significantly limits the number of trainable parameters, reducing the model's capacity to memorize the training data.
* **Data Augmentation:** Applied data augmentation techniques to the training set, including Random Horizontal Flip and Random Rotation (up to 15 degrees). These transformations create variations of the training images, exposing the model to a wider range of data and improving its generalization ability to unseen examples.
* **Limited Epochs:** The model was trained for a relatively small number of epochs (10). Training was stopped before the model gave me clear signs of overfitting on the training data (e.g., training loss continuing to decrease while validation loss increased).
