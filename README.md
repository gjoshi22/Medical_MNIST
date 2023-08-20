# Medical Image Classification on Medmnist v2 Dataset

## Methodology

This project aims to enhance the classification task's generalization power for various medical images data from the Medmnist v2 dataset. The dataset comprises 7 different medical image datasets relating to various medical conditions. The Convolutional Neural Network (CNN) model using the Resnet-18 architecture, which has 18 layers, will be deployed to train these images and classify the medical conditions.

## Data Centric Approach

Rather than a model-centric approach, our project focuses on a data-centric method. This approach gives priority to data quality and ensures the model is fed consistent data, which can lead to better results in areas like faster reporting, informed decision-making, data reliability, and trend insights.

## Data Augmentation

To address challenges like limited training data or imbalanced classes, data augmentation is utilized. This technique transforms available image samples into new variations without changing their labels. This project primarily employs four augmentation techniques: horizontal flipping, adding gaussian noise, normalization, and a combination of all these methods.

#### Data Split:
The balanced dataset was divided using an 8:2 ratio for training and validation

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

#### Overview:
The VesselMNIST3D dataset is derived from the IntrA dataset, specifically tailored for intracranial aneurysm research. This dataset encompasses 103 3D models (meshes) of brain vessels, sourced from reconstructed MRA images. A distinct characteristic of this dataset is the evident class imbalance: the vessel class significantly outnumbers the aneurysm class, with a ratio nearing 8:1.

#### Data Augmentation and Balancing:
To rectify the class imbalance, the minority class (aneurysm) was subjected to a slew of data augmentation techniques:
- Horizontal flip
- Gaussian noise
- Normalization
- Elastic transform
- Random invert
- Grayscale
- Color jitter

Post-augmentation, random sampling was employed to achieve a balanced class distribution for training. A separate model was also trained on the original imbalanced dataset for comparison purposes.

#### Hyperparameter Tuning:
- **Learning Rates:** 0.1 & 0.001
- **Optimizers:** Adam and Proximal Epoch Stochastic Gradient (PESG) with momentum set at 0.9.
- **Batch Sizes:** 128 and 256
- **Constants:** 
  - Epoch decay: 0.003
  - Weight decay: 0.0001
  - Loss function: AUCMLoss()

#### Results:

**Imbalanced Dataset Model:** 
- Test AUC: 0.7757

**Balanced Dataset with Tuned Hyperparameters:** 
- Optimizer: PESG
- Learning Rate: 0.1
- Batch Size: 128
- Test AUC: 0.8085

**Conclusion:** The results indicate the superiority of the balanced dataset model over its imbalanced counterpart in terms of classification capability.



