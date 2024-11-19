# **3D Cephalometric Landmark Detection Using Convolutional Neural Networks**

## **Overview**
This project explores the application of Artificial Intelligence (AI) and Computer Vision to medical imaging, specifically cephalograms, by developing a 3D Convolutional Neural Network (CNN) for automated cephalometric landmark detection. It draws direct inspiration from the research by Popova et al., *"Influence of growth structures and fixed appliances on automated cephalometric landmark recognition with a customized convolutional neural network"* ([BMC Oral Health, 2023](https://bmcoralhealth.biomedcentral.com/articles/10.1186/s12903-023-02984-2)). While the original work focused on 2D cephalograms, this project innovatively extends their methodology to 3D cephalometric imaging, making use of real-world data obtained from LMU Munich.

The goal is to leverage AI to predict 3D landmark coordinates for cephalometric diagnostics, enabling more precise and comprehensive craniofacial analysis. To address computational constraints of handling large datasets, synthetic data generation was implemented to ensure scalability.

---

## **Dataset**
### **Source**
- **Cases:**
  - **Case RS:** High-resolution cephalometric data in DICOM format, sourced from LMU Munich, featuring complex craniofacial anatomical structures.
  - **Case WM:** Additional cephalometric data from LMU Munich, offering structural diversity in voxel intensity and craniofacial geometry.

### **Data Characteristics**
- **Original Format:** DICOM.
- **Processed Format:** Converted to NIFTI (.nii) format for compatibility with neural network pipelines and volumetric analysis.
- **Landmark Coordinates:**
  - A comprehensive set of 3D landmark coordinates was provided in the dataset, covering crucial anatomical points.
  - Landmarks were extracted and normalized using affine transformations to standardize spatial coordinates.

### **Data Accessibility**
The full dataset, including imaging data and metadata for both cases, is available for download:
[**Download Dataset from Google Drive**](https://drive.google.com/file/d/1nzL5kq3zJOWxI4H77nyz3gzKbe4AXWXw/view?usp=sharing)

- **Metadata & Landmark Definitions:** The dataset includes a detailed spreadsheet ([Points and Definitions.xlsx](./Points%20and%20definitions.xlsx)) containing all landmarks and their coordinate mappings.

### **Visualization Techniques**
- **Volumetric Slicing:**
  - Used axial, sagittal, and coronal plane slices to examine craniofacial structures.
  - Enabled clear visualization of cephalometric structures for both raw and normalized data.
- **Landmark Plotting:**
  - Affine-transformed 3D landmark coordinates were plotted to validate preprocessing.
  - Visualization ensured consistency between original cephalograms and processed data.

---

## **Methodology**
### **1. Data Preparation**
- **Preprocessing Steps:**
  - Converted DICOM files to NIFTI format using Nibabel for efficient handling of volumetric data.
  - Applied affine matrices to map voxel indices to world coordinates, ensuring spatial consistency.
  - Normalized voxel intensities and coordinates for uniform representation in the neural network pipeline.
- **Synthetic Data Generation:**
  - Augmented dataset by introducing voxel-level transformations, noise injection, and affine perturbations, creating diverse training samples to address data scarcity.

### **2. Model Development**
- **Architecture:**
  - Built upon the 2D CNN framework from LMU Munich’s work, adapting it for 3D imaging.
  - Designed a volumetric CNN with layers tailored to handle 3D spatial inputs, enhancing predictive accuracy for 3D landmark detection.
- **Optimization:**
  - Loss Function: Mean Squared Error (MSE) for precise coordinate regression.
  - Optimizer: Adam with a learning rate of 0.001.
  - Validation Split: 20%, with early stopping to avoid overfitting.

### **3. Visualization**
- Plotted normalized landmarks on 3D volumes to verify preprocessing and prediction accuracy.
- Displayed loss curves for training and validation to evaluate convergence.

---

## **Results**
- **Performance Metrics:**
  - Training Loss: **0.035**
  - Validation Loss: **0.041**
- **Key Outcomes:**
  - Successfully extended 2D CNN methodologies to 3D cephalometric imaging.
  - Accurate 3D landmark predictions demonstrated the model's robustness on both real and synthetic datasets.

---

## **Tools & Libraries**
- **Programming Language:** Python.
- **Libraries:**
  - TensorFlow, Keras: Implementation of 3D CNN.
  - Nibabel: Conversion of DICOM to NIFTI and affine transformations.
  - NumPy: Data preprocessing and normalization.
  - Matplotlib, Seaborn: Visualization of volumetric slices, landmarks, and loss metrics.

---

## **Significance**
This project extends LMU Munich’s research by applying 3D CNNs to cephalometric landmark detection, addressing gaps in traditional 2D methods. The use of synthetic data and affine transformations ensures scalability for large datasets, demonstrating a significant step forward in craniofacial diagnostics and orthodontic planning.

---

## **References**
- Popova, T., et al. (2023). *Influence of growth structures and fixed appliances on automated cephalometric landmark recognition with a customized convolutional neural network*. BMC Oral Health, 23:274. [Read here](https://bmcoralhealth.biomedcentral.com/articles/10.1186/s12903-023-02984-2).

---



