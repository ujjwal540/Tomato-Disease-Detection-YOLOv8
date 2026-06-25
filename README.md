# 🍅 Tomato Disease Detection using YOLOv8

## 📌 Project Overview

This project uses YOLOv8 Object Detection to detect and classify tomato leaf diseases using deep learning techniques. The model identifies infected regions using Bounding Box Detection and predicts disease classes automatically. The project was developed and trained in Google Colab using the Ultralytics YOLOv8 framework.

---

# 🚀 Technologies Used

* Python
* YOLOv8
* PyTorch
* OpenCV
* Google Colab
* ONNX
* Matplotlib
* Pandas

---

# 📂 Dataset Structure

dataset/

├── train/

│ ├── images/

│ └── labels/

├── valid/

│ ├── images/

│ └── labels/

├── test/

│ ├── images/

│ └── labels/

└── data.yaml

The dataset contains:

* image files (.jpg)
* annotation label files (.txt)
* YOLO configuration file (data.yaml)

---

# 🧠 How YOLOv8 Works

YOLO (You Only Look Once) is a real-time object detection algorithm.

Workflow:

Input Image
↓
CNN Feature Extraction
↓
Object Detection
↓
Bounding Box Prediction
↓
Disease Classification
↓
Final Prediction Output

The model:

* detects disease regions
* localizes infected areas
* predicts disease classes
* outputs confidence scores

This project uses:
✅ Bounding Box Annotation

NOT:

* Segmentation masks
* Polygon annotations

Each image contains:

* class label
* bounding box coordinates

---

# 📌 Classes Detected

* Bacterial Spot
* Early_Blight
* Healthy
* Late_blight
* Leaf Mold
* Target_Spot
* black spot

---

# 📊 Epoch Experiment Analysis

To understand how training epochs affect model performance, multiple experiments were conducted using different epoch values.

The model was trained with:

* 20 epochs
* 50 epochs
* 70 epochs

The purpose of these experiments was to analyze whether increasing epochs always improves accuracy.

---

# 📈 Epoch Comparison Results

| Epochs | Precision | Recall | mAP50 | mAP50-95 | Observation          |
| ------ | --------- | ------ | ----- | -------- | -------------------- |
| 20     | 72.4%     | 66.8%  | 65.7% | 43.2%    | Model still learning |
| 50     | 76.4%     | 72.5%  | 76.6% | 47.6%    | Best Performance ✅   |
| 70     | 72.4%     | 66.8%  | 65.7% | 43.2%    | Overfitting ⚠️       |

---

# ⚠️ Understanding Overfitting

After 50 epochs, the model started suffering from overfitting.

Overfitting occurs when:

* the model memorizes training images
* instead of learning generalized disease patterns

Effects:

* validation accuracy decreases
* predictions become unstable
* poor performance on unseen images

This experiment demonstrates an important deep learning concept:

# Increasing epochs does NOT always increase accuracy.

Proper balance between:

* learning
* generalization
* training duration

is very important in deep learning systems.

---

# 📌 Why 50 Epochs Performed Best

At 50 epochs:

* the model learned disease patterns effectively
* validation accuracy improved
* object localization became more accurate
* classification stabilized

Result:
✅ Highest mAP50 Accuracy (76.6%)

Therefore:

* the 50-epoch model was selected as the final model

---

# 📊 Final Model Performance

| Metric    | Value |
| --------- | ----- |
| Precision | 76.4% |
| Recall    | 72.5% |
| mAP50     | 76.6% |
| mAP50-95  | 47.6% |

---

# 📌 Understanding Metrics

### Precision

Measures how many predicted detections are correct.

### Recall

Measures how many actual disease objects were detected.

### mAP50

Main object detection accuracy metric.

### mAP50-95

Stricter localization accuracy metric.

---

# 📉 Training Graph Analysis

![Training Graph](images/training_graph.png)


The graph visualizes:

* train loss
* validation loss
* mAP50 improvement

The training graph showed:

* training loss continuously decreased
* mAP50 improved until 50 epochs
* excessive training caused validation performance drop

This clearly indicates overfitting after longer training duration.

The experiment demonstrated that:

* higher epochs do not guarantee better accuracy
* dataset quality and model generalization are equally important

---

# 📌 Dataset Challenges

The project faced several dataset-related challenges:

* small dataset size
* class imbalance
* visually similar diseases
* limited annotations for weak classes

Example:

| Class        | Instances |
| ------------ | --------- |
| Early_Blight | 96        |
| Leaf Mold    | 7         |

This imbalance affected model performance for minority classes.

Lower accuracy was observed in:

* Leaf Mold
* Target Spot
* black spot

Reasons:

* fewer training images
* similar visual disease patterns
* limited dataset diversity

---

# 📌 Model Export

The trained model was exported to:

✅ PyTorch (.pt)
✅ ONNX (.onnx)

ONNX allows deployment on:

* web applications
* mobile applications
* edge AI devices
* OpenCV pipelines

---

# 📸 Project Outputs

This repository includes:

* trained YOLOv8 model
* ONNX export
* prediction images
* confusion matrix
* training graphs
* notebook implementation

---

# 📸 Sample Predictions

## 📸 Sample Predictions

<p align="center">
  <img src="images/val_batch0_pred.jpg" width="900"/>
</p>

Example:

* disease detection
* bounding box localization
* confidence score visualization

---

# 📊 Confusion Matrix

![Confusion Matrix](images/confusion_matrix_resized.png)

The confusion matrix visualizes:

* correct classifications
* class confusion
* weak performing classes

---

# 🌍 Real-World Applications

This project can be used in:

* smart agriculture
* automated crop monitoring
* drone-based disease detection
* farmer assistance systems
* precision farming

Real-world example:

Just like medical AI detects tumors in X-ray images using object detection, this project detects tomato leaf diseases using YOLOv8.

The model:

* identifies infected regions
* localizes disease areas
* predicts disease type automatically

---

# 📌 Future Improvements

Possible future enhancements:

* larger dataset
* better annotations
* segmentation-based detection
* YOLOv8s or YOLOv8m models
* real-time webcam detection
* mobile application deployment

---

# ✅ Conclusion

This project successfully implemented YOLOv8-based tomato disease detection using object detection techniques.

The final model achieved:
✅ 76.6% mAP50 Accuracy

The project demonstrates:

* object detection
* CNN-based feature learning
* bounding box annotation
* model evaluation
* overfitting analysis
* ONNX deployment

This project serves as a practical implementation of deep learning in agriculture and computer vision.

## Model Performance

- mAP50: 0.76
- mAP50-95: 0.47

