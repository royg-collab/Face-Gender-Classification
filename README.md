# Face Gender Classification with MobileNetV3-Small + SE Attention

A lightweight, accurate deep learning model for gender classification using facial images. This project combines **MobileNetV3-Small** with **Squeeze-and-Excitation (SE) Attention** to enhance feature extraction while maintaining efficiency.

---

##  Features

* ✅ MobileNetV3-Small backbone (pretrained on ImageNet)
* ✅ SE Attention module for adaptive feature selection
* ✅ Grad-CAM visualization support
* ✅ Confusion matrix + classification report
* ✅ Lightweight and fast training

---

##  Folder Structure

```
 Face-Gender-Classification
├── model.py           # MobileNetV3 + SE Attention definition
├── train.py           # Training script
├── test.py            # Evaluation script accepting test folder path
├── utils.py           # Utility functions (Plots, Grad-CAM, etc.)
├── pretrained.pth     # Saved model weights
├── requirements.txt   # All dependencies
└── README.md          # This file
```

---

##  Results

### Validation Classification Report:

```
              precision    recall  f1-score   support

      female       0.89      0.68      0.77        79
        male       0.93      0.98      0.95       343

    accuracy                           0.92       422
   macro avg       0.91      0.83      0.86       422
weighted avg       0.92      0.92      0.92       422
```

### Accuracy:

*  92% overall accuracy on validation set

---

##  Requirements

Install dependencies using:

```bash
pip install -r requirements.txt
```

---

##  Training

Train on your own dataset:

```bash
python train.py \
    --train_path /path/to/train \
    --val_path /path/to/val \
    --epochs 10 \
    --batch_size 16 \
    --save_model pretrained.pth
```

---

##  Testing

Evaluate the model on new test data:

```bash
python test.py \
    --model_path pretrained.pth \
    --test_path /path/to/test
```

It will output:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion matrix

---

##  Grad-CAM Visualizations

The project includes tools to generate Grad-CAM attention maps for model interpretability.

---

##  Dataset Format

Must follow ImageFolder structure:

```
Dataset/
├── class_0/  # e.g., female
│   └── img1.jpg
├── class_1/  # e.g., male
│   └── img2.jpg
```

---

##  Submission Checklist

* [x] Training and validation results ✅
* [x] Confusion matrix and Grad-CAM ✅
* [x] Test script ✅
* [x] Pretrained weights ✅
* [x] GitHub-ready project structure ✅

---

##  Author

\[Gargi Roy]

## 📜 License

MIT License

---

For questions, suggestions, or issues, please contact \[Your Email / GitHub Issue Tracker].
