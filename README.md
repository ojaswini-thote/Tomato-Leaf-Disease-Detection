# 🍅 Tomato Leaf Disease Detection Using Deep Learning

## 📌 Project Overview

Tomato Leaf Disease Detection is a deep learning project that classifies tomato leaf images into different disease categories or identifies healthy leaves. The project uses **MobileNetV2**, a lightweight convolutional neural network (CNN) architecture with transfer learning, to recognize visual patterns associated with tomato leaf diseases.

The model is trained using TensorFlow and Keras and evaluated using accuracy, precision, recall, F1-score, and a confusion matrix.

## 🎯 Objectives

- Detect and classify diseases in tomato leaves using image classification.
- Apply transfer learning using the MobileNetV2 architecture.
- Improve model generalization and reduce overfitting.
- Evaluate classification performance using multiple metrics.
- Visualize training performance and class-wise results.

## 🦠 Disease Classes

The model is designed to classify images into the following 10 categories:

1. Bacterial Spot
2. Early Blight
3. Healthy
4. Late Blight
5. Leaf Mold
6. Mosaic Virus
7. Septoria Leaf Spot
8. Target Spot
9. Two-Spotted Spider Mite
10. Yellow Leaf Curl Virus

## 🛠️ Technologies Used

- **Python** — Programming language
- **TensorFlow and Keras** — Deep learning model development
- **MobileNetV2** — Transfer learning architecture
- **NumPy** — Numerical computations
- **Matplotlib** — Visualization of training and evaluation results
- **Scikit-learn** — Model evaluation metrics
- **Google Colab** — Model training using GPU acceleration

## 🧠 Model Architecture

The project uses MobileNetV2, a pretrained CNN architecture that extracts visual features from images.

The general workflow is:

1. **Input images:** Tomato leaf images are resized to the required input dimensions.
2. **Preprocessing:** Images are normalized before being passed to the model.
3. **Feature extraction:** MobileNetV2 extracts relevant image features.
4. **Classification:** The classification head predicts the corresponding disease category.
5. **Evaluation:** Predictions are compared with the true labels to calculate performance metrics.

Transfer learning helps leverage features learned from a large image dataset, reducing the need to train the entire network from scratch.

## 🔄 Project Workflow

1. Load the tomato leaf image dataset.
2. Divide the data into training and validation sets.
3. Preprocess and resize the images.
4. Apply data augmentation to the training images.
5. Calculate class weights to account for class imbalance.
6. Train the MobileNetV2-based model.
7. Apply Early Stopping and Model Checkpoint callbacks.
8. Evaluate the trained model.
9. Generate graphs and a confusion matrix.
10. Save the trained model for future predictions.

## 🛡️ Techniques Used to Reduce Overfitting

### 1. Data Augmentation

Image transformations such as rotation, zoom, and horizontal flipping can help the model generalize to variations in leaf images.

### 2. Early Stopping

Training monitors validation loss and stops when improvement stalls for the specified patience period. Restoring the best weights helps retain the best-performing training state.

### 3. Model Checkpoint

The best model can be saved based on validation loss using `ModelCheckpoint`.

### 4. Class Weighting

Class weights are supplied during training to help account for differences in the number of images across disease categories.

### 5. GPU Acceleration

Google Colab GPU acceleration speeds up model training compared with CPU-only execution.

## 📊 Model Evaluation

The model is evaluated using the following metrics:

| Metric | Description |
|---|---|
| Accuracy | Proportion of all predictions that are correct |
| Precision | Proportion of positive predictions for a class that are correct |
| Recall | Proportion of actual samples of a class that are correctly identified |
| F1-score | Harmonic mean of precision and recall |
| Confusion Matrix | Shows correct and incorrect predictions for each class |

The project also includes visualizations of training and validation accuracy, training and validation loss, overall performance metrics, and class-wise performance.

### Preliminary Results

During validation, the model achieved approximately **97.15% accuracy** in the reported evaluation.

This value should be treated as a validation result unless performance has also been measured on a separate, independent test set. Final reported metrics should be generated using correctly aligned predictions and labels.

## 💾 Model Saving

The trained model can be saved for later use:

```python
model.save(MODEL_PATH)
```

If `ModelCheckpoint` is configured with `save_best_only=True`, it can save the best model according to the monitored validation metric.

## 🚀 Getting Started

### 1. Open the Notebook

Open the project notebook in Google Colab.

### 2. Enable GPU

In Google Colab, select:

**Runtime → Change runtime type → T4 GPU** (or another available GPU).

### 3. Prepare the Dataset

Organize the dataset into class-specific folders. For example:

```text
dataset/
├── train/
│   ├── bacterial_spot/
│   ├── early_blight/
│   ├── healthy/
│   ├── late_blight/
│   ├── leaf_mold/
│   ├── mosaic_virus/
│   ├── septoria_leaf_spot/
│   ├── target_spot/
│   ├── twospotted_spider_mite/
│   └── yellow_leaf_curl_virus/
└── validation/
    ├── bacterial_spot/
    ├── early_blight/
    ├── healthy/
    └── ...
```

The folder names and structure must match the paths configured in the notebook. The example above illustrates the expected structure; use your actual dataset paths.

### 4. Install Dependencies

If required, install the libraries in a Colab cell:

```python
!pip install tensorflow scikit-learn matplotlib numpy
```

### 5. Run the Notebook

Execute the notebook cells in order to preprocess the dataset, train the model, evaluate its performance, and generate visualizations.

## 📈 Expected Outputs

- Trained MobileNetV2-based model
- Training and validation accuracy graph
- Training and validation loss graph
- Overall accuracy, precision, recall, and F1-score
- Class-wise evaluation results
- Confusion matrix
- Saved model file

## 🌱 Applications

- Preliminary identification of tomato leaf diseases
- Agricultural image classification
- Plant disease monitoring research
- Development of smart agriculture applications
- Decision-support tools for farmers and agricultural researchers

The model is intended as a research and decision-support tool. Its predictions should be verified before making crop-treatment decisions.

## 🔮 Future Enhancements

- Evaluate performance on an independent test dataset.
- Deploy the trained model through a web or mobile application.
- Add image upload and real-time prediction functionality.
- Improve robustness using images captured under real-world lighting and backgrounds.
- Explore model quantization for mobile and edge deployment.
- Expand the dataset to include additional plant species and disease categories.

## 👩‍💻 Author

**Ojaswini Thote**

Project: Tomato Leaf Disease Detection Using Deep Learning

## 📄 License

Add an appropriate license before distributing this project publicly.
