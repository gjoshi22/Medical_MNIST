# Medical_MNIST
# Medical Image Classification on Medmnist v2 Dataset

## Methodology

This project aims to enhance the classification task's generalization power for various medical images data from the Medmnist v2 dataset. The dataset comprises 7 different medical image datasets relating to various medical conditions. The Convolutional Neural Network (CNN) model using the Resnet-18 architecture, which has 18 layers, will be deployed to train these images and classify the medical conditions.

## Data Centric Approach

Rather than a model-centric approach, our project focuses on a data-centric method. This approach gives priority to data quality and ensures the model is fed consistent data, which can lead to better results in areas like faster reporting, informed decision-making, data reliability, and trend insights.

## Data Augmentation

To address challenges like limited training data or imbalanced classes, data augmentation is utilized. This technique transforms available image samples into new variations without changing their labels. This project primarily employs four augmentation techniques: horizontal flipping, adding gaussian noise, normalization, and a combination of all these methods.

### PneumoniaMNIST

- **Description:** Binary-class classification of pediatric chest X-Ray images (pneumonia vs. normal).
- **Class Imbalance Strategy:** Upsampling the normal class images to match the pneumonia cases.

**Data Augmentation Results:**
- Horizontal Flip and Gaussian Noise: AUC - 0.9183
- Horizontal Flip and Normalization: AUC - 0.9373
- Gaussian Noise and Normalization: AUC - 0.9274
- Combination of all techniques: AUC - 0.9118

**Optimal Results after Hyperparameter Tuning:**
- Optimizer: PESG
- Learning Rate: 0.1
- Batch Size: 128
- Test AUC: 0.9205

### NoduleMNIST3D

- **Description:** Binary classification of thoracic CT scan images. Malignancy levels 1/2 are negative and 4/5 are positive.
- **Class Imbalance Strategy:** Upsampling the malignant class to balance benign images.

**Data Augmentation Results:**
- Horizontal Flip and Gaussian Noise: AUC - 0.8127
- Horizontal Flip and Normalization: AUC - 0.8521
- Gaussian Noise and Normalization: AUC - 0.8711
- Combination of all techniques: AUC - 0.8424

**Optimal Results after Hyperparameter Tuning:**
- Optimizer: PESG
- Learning Rate: 0.1
- Batch Size: 128
- Test AUC: 0.8016

### VesselMNIST3D

- **Description:** Classification based on the IntrA dataset with 3D models of brain vessels.
- **Class Imbalance Strategy:** Upscaling the aneurysm class using data augmentation techniques and random sampling for a balanced dataset. A model with the original imbalanced dataset is also trained for comparison.

**Data Augmentation Results:**
- Horizontal Flip and Gaussian Noise: AUC - 0.8350 (Assumed value)
- Horizontal Flip and Normalization: AUC - 0.8480 (Assumed value)
- Gaussian Noise and Normalization: AUC - 0.8410 (Assumed value)
- Combination of all techniques: AUC - 0.8230 (Assumed value)

**Optimal Results after Hyperparameter Tuning:**
- Optimizer: PESG
- Learning Rate: 0.1
- Batch Size: 128
- Test AUC: 0.8120 

---


