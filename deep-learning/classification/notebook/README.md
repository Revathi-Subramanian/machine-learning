Architectural Structure Classification

### Objective
To build a highly accurate image classification model capable of automatically identifying 10 different architectural components of historical sites (e.g., dome, bell tower, apse).

### Methodology: Deep Learning & Transfer Learning

| Feature | Details |
| :--- | :--- |
| **Model** | Benchmarked two Transfer Learning models: **EfficientNetB0** and **ResNet50**. |
| **Architecture** | Used pre-trained ImageNet weights, freezing base layers, and adding a custom dense layer (1200 neurons) and a dropout layer (0.2). |
| **Data Cleaning** | Implemented a robust data pipeline to **detect and repair corrupt images** using a sequence of checks via **OpenCV** and **PIL (Pillow)**. |
| **Performance** | **EfficientNetB0** was selected as the final model, achieving a superior **92.02% Accuracy** on the test dataset. |

### Libraries Used
* Numpy, Matplotlib, Seaborn
* TensorFlow / Keras
* OpenCV (`cv2`)
* PIL (Pillow)
### Models
* EfficientNetB0, ResNet50
