# Task-2

## Overview

This task focuses on classifying 36(0-9 & a-z) ASL gestures using a YOLO-based image classification model, YOLO26n. The objective is to accurately recognize hand signs from images while maintaining robustness to variations in lighting, orientation, and image quality. 


##Why YOLO26?<br>
Best performance for CPU/Edge inference.
https://docs.ultralytics.com/compare/yolo26-vs-yolo11#progloss-and-stal


## How to Run

### Install Dependencies

```bash
pip install ultralytics
```

### Run Inference

```bash
yolo classify predict \
    model=runs/classify/train/weights/best (1).pt \
    source=test_image.jpg
```

---

## Evaluation Metrics

The following metrics should be considered when evaluating the model:

### Accuracy

Measures the percentage of correctly classified images.

```text
Accuracy = Correct Predictions / Total Predictions
```

### Precision 

Measures how many predicted instances of a class are actually correct.

### Recall

Measures how many actual instances of a class are successfully identified.

### F1-Score ( more important than accuracy here)

Harmonic mean of Precision and Recall.

### Confusion Matrix

Provides class-wise performance and helps identify commonly misclassified signs.

---

## Results Interpretation

A good model should exhibit:

* High validation accuracy while training, signs balanced training and no overfitting.
* Balanced precision and recall across all classes
* Minimal confusion between visually similar gestures
* Consistent performance on unseen test images

---

## Conclusion

A YOLO-based classification pipeline combined with data augmentation provides an efficient solution for sign language recognition. The augmentation strategy improves robustness, while YOLO enables fast and accurate classification suitable for real-world deployment.
