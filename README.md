# Face Gender Classification with MobileNetV3-Small + SE Attention

This project aims to build a lightweight and accurate deep learning model for gender classification from facial images using the MobileNetV3-Small architecture enhanced with Squeeze-and-Excitation (SE) attention. The model is trained and evaluated on a dataset organized into gender-based subfolders ("male" and "female").

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

### Confusion Matrix:
Visualized using seaborn to show true positives, false positives.
![image](https://github.com/user-attachments/assets/ed220757-5b05-4bad-833f-1c31e7780d53)

### Training vs Validation plot (loss and accuracy):
Plot curves against Training and Validation output to visualize loss and accuracy.
![image](https://github.com/user-attachments/assets/74bd2a09-4aa7-466b-b2c7-72a35e43d096)

### Grad-CAM Visualization:
Grad-CAM heatmaps were used to visualize where the model focuses when predicting gender from a face. Results showed attention around eyes, nose, and jawline.
![image](https://github.com/user-attachments/assets/73337c76-afa6-48ad-926b-41072d20ea96)


---

##  Requirements

Install dependencies using:

```bash
pip install -r requirements.txt
```

---

 Training
 ** 3.1 Optimizer and Loss
 
* Optimizer: Adam
* Learning Rate: 0.0001
* Loss Function: CrossEntropyLoss

 ** 3.2 Metrics Tracked
 
* Training Loss and Validation Loss
* Accuracy
* Precision, Recall, and F1-score (both macro and weighted)

 ** 3.3 Training Summary
 
* Epochs: 50
* Batch Size: 16

 ** 3.4 Resource Usage
 
* CPU Memory Used
* Training Time: ~95.0 minutes (varies by hardware)
________________________________________

Train on your own dataset:

```bash
python train.py \
    --train_path /path/to/train \
    --val_path /path/to/val \
    --epochs 50 \
    --batch_size 16 \
    --save_model pretrained.pth
```

---

##  Testing:

A separate test.py script is provided that:
•	Accepts a test dataset path (same folder structure)
•	Loads the pretrained model
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
Task_A/
├── train/
│   ├── female/
│   └── male/
├── val/
    ├── female/
    └── male/
```
•	Total Classes: 2
•	Image Size: Resized to 224x224
•	Normalization: Standard ImageNet mean and std

---

##  Submission Checklist

*  Training and validation results ✅
*  Confusion matrix and Grad-CAM ✅
*  Test script ✅
*  Pretrained weights ✅
*  GitHub-ready project structure ✅

---

##  Author

\[Gargi Roy]

## 📜 License

MIT License

---

For questions, suggestions, or issues, please contact \[chattg10@gmail.com].
