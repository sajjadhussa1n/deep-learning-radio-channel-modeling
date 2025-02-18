# Deep Learning for Radio Channel Modeling

This repository demonstrates the use of deep learning models (CNN, U-Net, GAN) for radio channel modeling, focusing on UAV-assisted 5G and mmWave networks. The aim is to provide learners and researchers with state-of-the-art implementations and tutorials for predicting path loss, visualizing radio environments, and generating synthetic channel data.

**Note:** This is a **work in progress** and will be updated regularly with new models, datasets, and tutorials. Stay tuned for more!
## Features
- **Data Preprocessing**: Tools for cleaning, augmenting, and visualizing radio channel data.
- **Multiple Models**: Implementations of CNN, U-Net, and GAN models for different radio network tasks.
- **Interactive Notebooks**: Jupyter notebooks to walk through training, visualization, and fine-tuning models.
- **Results**: Visual outputs such as heatmaps, signal strength plots, and predictions over terrain.

## Getting Started
1. Clone the repository:
   ```bash
   git clone https://github.com/sajjadhussa1n/deep-learning-radio-channel-modeling.git
   cd deep-learning-radio-channel-modeling

# 📡 UNet Model for Pathloss Prediction in Urban Environments (Version 0)

Welcome to my exciting journey of building a **UNet model** for **pathloss prediction** in urban environments! This repository documents my first attempt at leveraging the power of deep learning to predict radio wave propagation using the geometric, geographic, and geospatial features of city landscapes. 🏙️📶

## 🌟 Overview

In this project, I aim to develop a **UNet-based model** to predict **pathloss**—the reduction in signal strength as it propagates through an urban environment. Using advanced **ray-tracing simulations** from my previous research ([reference here](#)), I generated a rich dataset in three diverse environments:

- **Munich-01** 📍
- **Munich-02** 📍
- **London** 🇬🇧

### 📊 Dataset Generation

I generated the dataset by simulating radio wave propagation under the following conditions:

- **Carrier Frequency**: 28 GHz (mmWave radio networks ✨)
- **Transmitter**: UAV-based dipole antenna at heights of **25m**, **35m**, and **45m** 📡
- **Receivers**: Grid of receivers at **1.5m** height, spread across the simulation environment 🎯

I considered various ray contributions to capture realistic pathloss values:

- **Line-of-Sight (LOS) Ray** 🔦
- **1st Order Wall Reflections** 🪞
- **Diffuse Scattering from Walls**  ([reference here](#))
- **Ground Reflections** 
- **Empirical Model**: For receivers missing the above rays, we used the **3GPP model** to fill in the gaps 📏
- **Building Penetration Loss**: Factored in outdoor-to-indoor penetration for a comprehensive pathloss map 🏢

### 📐 Receiver Grid Sizes

Each environment has a different receiver grid (yes, I realized later that using a uniform grid would have made life easier! 😅):

- **Munich-01**: 205 x 300
- **Munich-02**: 190 x 300
- **London**: 190 x 320

### 📏 Geometrical Parameters

In addition to pathloss, I also computed **13 geometrical parameters** for each receiver in the grid. These features were previously used in other ML models from my research ([paper here](#)).

✨ Note: The datasets will be shared publicly after the paper is published. Stay tuned—good things are on their way! 🚀📷

## 🚀 Why UNet for Pathloss Prediction?

The UNet architecture, originally designed for biomedical image segmentation, is a perfect fit for spatial prediction problems like this one! With its **encoder-decoder** structure and **skip connections**, it can capture both global and local features—exactly what we need to model complex urban propagation environments. 📚

## UNet architecture Used in V0:


