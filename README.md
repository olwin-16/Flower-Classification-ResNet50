# **Flower Image Classification Using ResNet50**

<br>
<div align="center">
  <img width="500" alt="image" src="https://github.com/user-attachments/assets/080a9780-4419-44ff-afc0-7333e5ff43c5" />
</div>
<br>

## **Overview**

This project implements a deep learning classifier for the **Oxford Flowers-102** dataset using a **ResNet50** model pre-trained on **ImageNet**. By leveraging transfer learning and regularization, the goal is to accurately distinguish between 102 diverse flower categories in a robust and computationally efficient manner.

## **Dataset**

- **Classes**: 102 flower species
- **Images per class**: 40–258
- **Components**: Flower images, segmentations, chi2 distances, labels, predefined splits

## **Workflow**

1. **Download and Prepare Data**
- Downloaded the Oxford Flowers-102 dataset and corresponding image labels.
- Mapped filenames to labels, ensured proper indexing and structure.

2. **Data Preprocessing & Augmentation**
   
- Split data: 80% training, 20% validation.
- Applied image augmentation (rotation, shear, zoom, brightness, flip) for training set.

3. **Model Architecture**
   
- Used ResNet50 (pre-trained on ImageNet) as the base.
- Added custom layers:
  
  - GlobalAveragePooling2D
  - Dense (1024 Neurons, ReLU)
  - BatchNormalization
  - Dropout (0.5)
  - Output Dense layer (Softmax, 102 classes)
  - Freezed half of the base model layers for transfer learning.

4. **Training**
   
- Optimizer: Adam, learning rate scheduler reduces LR on plateau.
- Categorical crossentropy loss, accuracy metric.
- Trained for 40 epochs with data generators.

5. **Evaluation & Saving**
   
- Achieved test set accuracy: **~0.83**
- Saved the trained model: **flowers102_model.keras**

## **Visual Results**

- **Training and Validation Accuracy**
<br>
<img width="748" height="574" alt="image" src="https://github.com/user-attachments/assets/f9828ed2-bd1e-4b58-8964-a2670f6face5" />
<br>
- **Training and Validation Loss**
<br>
<img width="762" height="628" alt="image" src="https://github.com/user-attachments/assets/ce9080ba-d74a-4413-b195-5a0feb49c2b3" />
<br>
## **Getting Started**

Follow these steps to clone the repository, set up, and run the project:

1. **Clone the Repository**
   
```bash

git clone https://github.com/olwin-16/Flower-Classification-ResNet50.git

```

3. **Navigate into the Project Directory**
   
```bash

cd Flower-Classification-ResNet50

```

4. **Install Required Dependencies**
   
```bash

pip install -r requirements.txt

```

5. **Run the Training Script**
   
```bash

python train_flower_classifier.py

```
## References

[Oxford Flowers-102 Dataset](https://www.robots.ox.ac.uk/~vgg/data/flowers/102/)

[ResNet50: Deep Residual Learning](https://arxiv.org/abs/1512.03385)

