# COVID-19 Chest X-ray Image Classification using Convolutional Neural Networks (CNN)

## 📌 Project Overview

This project presents a **Deep Learning-based image classification system** for detecting **COVID-19 infection from chest X-ray images** using **Convolutional Neural Networks (CNNs)**. The primary objective is to build an automated binary image classifier that distinguishes between **COVID-19** and **Normal** chest X-ray images, providing a fast and reliable computer-aided diagnostic approach.

The project begins with **data exploration and preprocessing**, where chest X-ray images are loaded, resized to **128 × 128 pixels**, normalized by scaling pixel values to the range **0–1**, and divided into **training, validation, and testing datasets**. This preprocessing ensures that the image data is suitable for CNN training while maintaining consistent input dimensions.

Instead of building a single CNN model, the project follows an **experimental approach** by developing and comparing **two different CNN architectures** to study the effect of architectural modifications on classification performance.

The **first CNN model** consists of three convolutional blocks followed by fully connected layers. Although this model achieved **100% training accuracy and recall**, the validation performance indicated **overfitting**, showing that the model had memorized the training data rather than learning features that generalize well.

To overcome this limitation, a **second CNN model** was designed by introducing **Batch Normalization** and **Dropout** layers while simplifying the network architecture. These improvements helped reduce overfitting and produced a better balance between training and validation performance.

Both models are evaluated using **Accuracy, Precision, Recall, F1-Score, and Confusion Matrix**. Since failing to detect an infected patient is a critical concern in medical diagnosis, **Recall is considered an important evaluation metric** throughout the project.

After comparing the experimental results, **CNN Model 2** is selected as the final model because it demonstrates better generalization and achieves **97.37% test accuracy** while maintaining a high COVID-19 recall.

---

## 🎯 Objectives

* Develop a Convolutional Neural Network (CNN) for COVID-19 chest X-ray image classification.
* Perform exploratory analysis of the chest X-ray dataset.
* Preprocess and normalize medical images for deep learning.
* Build and compare multiple CNN architectures.
* Analyze the impact of architectural modifications on model performance.
* Evaluate the models using Accuracy, Precision, Recall, F1-Score, and Confusion Matrix.
* Reduce overfitting through Batch Normalization and Dropout.
* Select the best-performing CNN model for COVID-19 detection.

---

## 📂 Dataset

The project uses a **binary chest X-ray image dataset** containing two classes:

* **COVID-19**
* **Normal**
The data file names are:
- CovidImages.npy
- CovidLabels.csv

### Dataset Summary

* **Total Images:** 251
* **Image Size:** 128 × 128 pixels
* **Training Images:** 175
* **Validation Images:** 38
* **Testing Images:** 38

All images are converted into NumPy arrays before being used for model training.

---

## 🔍 Exploratory Data Analysis

The notebook includes exploratory analysis to understand the characteristics of the dataset before model development.

The analysis includes:

* Dataset overview
* Image dimension analysis
* Class distribution
* Sample chest X-ray visualization
* Training, validation, and testing dataset inspection

The dataset is then prepared for deep learning through image normalization and dataset splitting.

---

## 🧹 Data Preprocessing

The following preprocessing steps are performed:

* Resize all chest X-ray images to **128 × 128 pixels**
* Convert images into NumPy arrays
* Normalize pixel values by dividing by **255**
* Encode binary class labels
* Split the dataset into:

  * **175 Training Images**
  * **38 Validation Images**
  * **38 Test Images**

Normalization improves training stability by ensuring that all pixel values lie between **0 and 1**.

---

## 🧠 CNN Model Development

The project develops and compares two CNN architectures.

## CNN Model 1

The first CNN architecture consists of:

* Three Convolutional Layers
* Max Pooling Layers
* Fully Connected Dense Layers
* ReLU Activation
* Softmax Output Layer

### Observation

* Achieved **100% training accuracy and recall**
* Validation performance was comparatively lower
* Demonstrated signs of **overfitting**, indicating that the model memorized the training data rather than learning generalized features.

---

## CNN Model 2

To improve generalization, the second architecture introduces:

* Batch Normalization
* Dropout Layers
* Simplified CNN architecture
* Adam Optimizer with a learning rate of **0.0001**

### Observation

Compared with Model 1, this model:

* Reduced overfitting
* Improved validation performance
* Achieved better generalization
* Produced more reliable predictions on unseen chest X-ray images

---

## 📊 Model Evaluation

The CNN models are evaluated using:

* **Accuracy**
* **Precision**
* **Recall**
* **F1-Score**
* **Confusion Matrix**

### Importance of Recall

In medical image classification, **False Negatives** are critical because an infected patient may be incorrectly classified as healthy.

Therefore, the project emphasizes **Recall**, ensuring that as many COVID-19 cases as possible are correctly identified.

---

## Final Model Selection

After comparing both CNN architectures, **CNN Model 2** is selected as the final model.

### Reasons for Selecting Model 2

* Better generalization performance
* Reduced overfitting
* Improved validation performance
* More reliable classification on unseen images
* **97.37% Test Accuracy**
* High recall for COVID-19 detection

---

## Prediction

The final CNN model predicts whether a chest X-ray image belongs to:

* **COVID-19**
* **Normal**

The notebook demonstrates prediction on unseen chest X-ray images by displaying the image alongside its predicted class.

---

## 📈 Key Findings

The experimental study highlights the following observations:

* A deeper CNN architecture alone does not guarantee better performance.
* Perfect training accuracy can indicate **overfitting** rather than superior generalization.
* Batch Normalization improves training stability and convergence.
* Dropout effectively reduces overfitting by preventing excessive dependence on specific neurons.
* Combining Batch Normalization and Dropout leads to a more robust and generalized CNN model.
* CNN Model 2 achieves a better balance between training and validation performance compared to Model 1.

---

## 🛠️ Technologies Used

* Python
* TensorFlow
* Keras
* NumPy
* Pandas
* OpenCV
* Matplotlib
* Seaborn
* Scikit-learn
* Google Colab

---

## 📌 Conclusion

This project demonstrates the application of **Convolutional Neural Networks (CNNs)** for automated COVID-19 detection from chest X-ray images. Through a comparative study of two CNN architectures, the project analyzes how architectural improvements such as **Batch Normalization** and **Dropout** influence model performance and generalization.

The experimental results show that **CNN Model 2** successfully overcomes the overfitting observed in the initial model and achieves **97.37% test accuracy**, making it a reliable model for binary chest X-ray image classification. This workflow demonstrates the importance of model evaluation, architecture refinement, and regularization techniques in developing effective deep learning solutions for medical image analysis.
