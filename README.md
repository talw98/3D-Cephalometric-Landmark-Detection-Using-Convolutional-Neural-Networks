# **3D Cephalometric Landmark Detection Using Convolutional Neural Networks**

## **Overview**
This project applies Artificial Intelligence (AI) and Computer Vision techniques to medical imaging, specifically cephalograms, to develop a 3D Convolutional Neural Network (CNN) for automated cephalometric landmark detection. Inspired by the research paper *"Influence of growth structures and fixed appliances on automated cephalometric landmark recognition with a customized convolutional neural network"* by Popova et al. ([BMC Oral Health, 2023](https://bmcoralhealth.biomedcentral.com/articles/10.1186/s12903-023-02984-2)), the work extends their 2D methodology to 3D cephalometric imaging. This project leverages data sourced from LMU Munich and synthetic augmentation techniques to address computational limitations while enhancing landmark detection accuracy.

The primary objective is to predict 3D coordinates of cephalometric landmarks accurately, enabling advanced diagnostic capabilities for craniofacial imaging and orthodontic treatment planning.

---

## **Dataset**
### **Source**
- **Cases:**
  - **Case RS:** Cephalometric data in DICOM format obtained from LMU Munich, representing complex anatomical structures.
  - **Case WM:** Additional cephalometric data in DICOM format with unique structural and voxel intensity characteristics.

### **Data Characteristics**
- **Original Format:** DICOM.
- **Processed Format:** Converted to NIFTI (.nii) format for compatibility with 3D visualization and model input pipelines.
- **Landmark Coordinates:**
  - A set of predefined cephalometric landmarks plotted in 3D space, provided in an Excel dataset ([Points and Definitions.xlsx](./Points%20and%20definitions.xlsx)).
  - Landmarks extracted and normalized using affine transformations to standardize voxel-to-world mappings.

### **Visualization Techniques**
- **Volumetric Slicing:**
  - Applied slicing across axial, sagittal, and coronal planes for visualizing craniofacial structures.
- **Landmark Plotting:**
  - Normalized landmark coordinates visualized to validate preprocessing.
  - Affine matrices used to overlay landmarks on original cephalometric volumes.

---

## **Methodology**
### **1. Data Preparation**
- **Preprocessing Steps:**
  - Conversion of DICOM data to NIFTI format using Nibabel.
  - Application of affine matrices to compute precise 3D spatial coordinates for landmarks.
  - Normalized intensity values for uniform input representation.
- **Synthetic Data Generation:**
  - Generated synthetic cephalograms by applying voxel perturbations, affine transformations, and noise augmentation to enhance model generalizability.

### **2. Visualization**
- Visualized 3D data with overlaid landmarks using Matplotlib and Seaborn.
- Verified the accuracy of normalized and transformed coordinates by comparing plots against original cephalometric images.

### **3. Model Development**
- **Architecture:**
  - A 3D CNN adapted from the 2D model proposed by Popova et al., incorporating additional layers for volumetric data processing.
  - Designed for precise regression of X, Y, Z coordinates for each cephalometric landmark.
- **Optimization:**
  - Loss function: Mean Squared Error (MSE) for coordinate regression.
  - Optimizer: Adam with a learning rate of 0.001.
- **Training Parameters:**
  - Batch size: 32.
  - Early stopping enabled to mitigate overfitting.
  - Validation split: 20%.

### **4. Metrics**
- Training Loss: **0.035**
- Validation Loss: **0.041**
- Metrics visualized using loss curves, demonstrating robust convergence.

---

## **Landmark Definitions**
The dataset includes the following cephalometric landmarks:
- **Key Points:** Subspinale (A-point), Anterior Nasal Spine (ANS), Pogonion (Pog), and others.
- **Coordinate Format:** Each landmark is defined by its X, Y, Z coordinates in a normalized 3D space.
- **Dataset File:** [Points and Definitions.xlsx](./Points%20and%20definitions.xlsx).

---

## **Results**
- **Model Performance:**
  - Demonstrated effective 3D landmark detection on synthetic data.
  - Accurately visualized predicted landmarks overlaid on cephalometric images.
- **Significance:**
  - The model's ability to work with 3D data enhances spatial diagnostic capabilities, bridging gaps in traditional 2D methods.

---

## **Tools & Libraries**
- **Programming Language:** Python.
- **Libraries:**
  - TensorFlow, Keras: Neural network implementation and optimization. (originally used in the research paper
  - Nibabel: DICOM to NIFTI conversion and affine transformations.
  - NumPy: Data manipulation.
  - Matplotlib, Seaborn: Visualization of 3D data and training metrics.

---

## **Significance**
This project pioneers the extension of 2D CNN methods for cephalometric landmark detection to 3D volumetric data, contributing to the automation of craniofacial diagnostic workflows. By addressing computational constraints through synthetic data augmentation, it provides a scalable and precise approach to orthodontic diagnostics.

---

## **References**
- Popova, T., et al. (2023). *Influence of growth structures and fixed appliances on automated cephalometric landmark recognition with a customized convolutional neural network*. BMC Oral Health, 23:274. [Read here](https://bmcoralhealth.biomedcentral.com/articles/10.1186/s12903-023-02984-2).

