# Polarization of the Sky and Estimation of the Sun’s Position

**Auteur :** Fauzi AKBAR — Aix-Marseille University

**Class :** Asservissement visuelle - 3A ROB - ENSTA Bretagne

## 🗂️ Contents:
  - [Lecture Material](Asservissement_visuelle___3A_ROB___Fauzi_AKBAR.pdf) 
  - [📁 Google Drive Videos Folder](https://drive.google.com/drive/folders/1xJ4t_7Zl7KxzNugT1ELE4-c9jz1h76Xy?usp=drive_link)
  - Jupyter Notebook for TP (student): [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1nNxSAMeVHEZFbhEDSvsaSZcKfgpjZsZB?usp=sharing)
  - Jupyter Noterbook Correction: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1rXZy-T44XG3C8RXjnq2X6owIDiFDy1R6?usp=sharing)
  - [Quiz](Quiz_asservisement_visuelle.pdf)

# 🌤️ Polarization-Based Sun Position Estimation

This repository contains a Jupyter Notebook that demonstrates how to compute the sun’s position, visualize polarization patterns using Rayleigh scattering, transform coordinates, and evaluate a CNN model for sun prediction from sky images.

---

## 📘 Notebook Overview

### **1️⃣ Setup**
- Clone the repository to access all required datasets and libraries.
- Ensure all dependencies are installed before running the notebook.

---

### **2️⃣ Part I — Sun Position Calculation (Astropy)**
- Compute the **Sun’s azimuth and elevation** using:
  - The geographical location of **ENSTA Bretagne – Brest Campus** (latitude & longitude)
  - The current date and time
- Calculations are done using the **Astropy** astronomy library.

---

### **3️⃣ Part II — Polarization Simulation (OpenSky)**
- Visualize:
  - **Angle of Polarization (AoP)**
  - **Degree of Polarization (DoLP)**
- Based on the **Rayleigh Scattering Model** using **OpenSky**.
- Reference:  
  *Moutenet, A., Poughon, L., Toulon, B., Serres, J. R., & Viollet, S. (2024). Opensky: a modular and open-source simulator of sky polarization measurements. IEEE TIM.*

---

### **4️⃣ Part III — Using Dataset Images**

a. Select a random AoP image from the `soccer_field_images/` folder and retrieve the corresponding metadata  
   (latitude, longitude, date, time) from `soccer_field_image_info_158.csv`.

b. Compute the **Sun’s azimuth and elevation in the ENU frame** for the selected image.

c. Transform the Sun’s azimuth from **ENU coordinates to the camera frame** using rotation matrices, accounting for the robot’s yaw angle.

---

### **5️⃣ Part IV — CNN-Based Sun Position Prediction**
- Load the pretrained CNN model:
  [🎯 Pre-trained model](https://drive.google.com/file/d/1MsxV_oHQ0eyKgPztp8hqQwzxhYFK_t-y/view?usp=drive_link)
- Use it to **predict the Sun’s position** on a sky image.
- Compute and display the **prediction error** relative to the ground truth.

---

### **6️⃣ Part V — North Celestial Pole (NCP) Estimation**
- Estimate the location of the **North Celestial Pole** using DoLP patterns from the dataset.
- Based on the *SkyPole* method:  
  *Kronland-Martinet, T., Poughon, L., Pasquinelli, M., Duché, D., Serres, J. R., & Viollet, S. (2023). SkyPole—A method for locating the north celestial pole from skylight polarization patterns. PNAS.*

---

### **7️⃣ Part VI — Observer Orientation from Polarization**
- From the computed pole point:
  - Determine the observer’s **azimuth**
  - Determine the observer’s **latitude**
- Use the matrix `orientation_pixels_ENU` for coordinate transformation.
- Reference values:
  - Azimuth = **0° (North)**
  - Elevation = **observer’s latitude**

---

## 📁 Repository Structure
```
├── Data_30_07_2022 # DoLP Images and library for North Celestial Pole
├── opensky # Library for OpenSky simulator
├── soccer_field_images/ # AoP images from robot experiments
├── soccer_field_image_info_158.csv # Metadata for images
└── README.md # This file
```

---

## 🛠️ Requirements
- Python 3.8+
- Jupyter Notebook
- Dependencies:
  - numpy  
  - astropy  
  - matplotlib  
  - OpenSky  
  - PyTorch or TensorFlow (for CNN model)

---

## 🚀 How to Run

Open the notebook :

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1nNxSAMeVHEZFbhEDSvsaSZcKfgpjZsZB?usp=sharing)

Run all cells in sequence.

📚 References

- Moutenet et al., IEEE TIM, 2024 — OpenSky simulator

- Kronland-Martinet et al., PNAS, 2023 — SkyPole method
  
- Goldstein, D. H. (2010). Polarized Light, Third Edition. CRC Press.

- Courtier, G. (2016). Ground Vehicle Navigation Based on the Skylight Polarization.

- Pan, S. H., et al. (2020). Image-registration-based solar meridian detection for accurate and robust polarization navigation.

- Li, Q., et al. (2018). Skylight polarization patterns under urban obscurations and a navigation method adapted to urban environments.

- Kong, F., et al. (2021). Review on bio-inspired polarized skylight navigation.
