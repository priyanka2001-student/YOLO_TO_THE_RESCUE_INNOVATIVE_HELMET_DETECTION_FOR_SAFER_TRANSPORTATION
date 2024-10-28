# YOLO to the Rescue: Innovative Helmet Detection for Safer Transportation

## Overview

This project focuses on developing an innovative helmet detection system using YOLOv8s from Ultralytics to determine whether individuals are wearing helmets while driving. The aim is to enhance safety in transportation by improving compliance with safety regulations and promoting safer driving practices through real-time object detection and analysis.

## Table of Contents

- [Features](#features)
- [Installation](#installation)
- [Dataset](#dataset)
- [Usage](#usage)
- [Results](#results)

## Features

- **Helmet Detection**: Accurately identifies whether a person is wearing a helmet in real-time.
- **YOLOv8 Model**: Utilizes the latest advancements in the YOLO (You Only Look Once) framework for efficient object detection.
- **Real-Time Analysis**: Processes video streams or images to ensure compliance with safety regulations instantly.
- **Output Visualizations**: Generates output images with detected helmets for easy assessment.

## Installation

To set up the project, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/your_username/helmet-detection.git
   cd helmet-detection
   ```

2. Install the required packages:
   ```bash
   pip install ultralytics tqdm
   ```

3. Ensure you have access to the dataset and place it in the appropriate directory as described in the [Dataset](#dataset) section.

## Dataset

The dataset used for training and testing the helmet detection system can be found at the following link:

- [Helmet Detection Dataset](https://universe.roboflow.com/bike-helmets/bike-helmet-detection-2vdjo/dataset/2)

Please ensure to follow any licensing agreements associated with the dataset. The dataset should be structured as specified in the YOLO format.

## Usage

### Training the Model

To train the model, run the following command:

```bash
!yolo task=detect mode=train model=yolov8s.pt data=path/to/your/data.yaml epochs=50 imgsz=640 batch=8 project=training_results name=Helmet
```

### Making Predictions

To make predictions on test images, use:

```bash
!yolo task=detect mode=predict model=training_results/Helmet/weights/best.pt conf=0.35 source=path/to/your/test_images
```

### Output

The predicted images will be saved in the `runs/output/predict` directory, which can be copied to your desired output folder:

```bash
!cp -r /content/runs/detect/predict /path/to/your/output_directory
```

## Results

Results from the training process, including loss graphs and evaluation metrics, can be found in the `training_results` directory. Example output images with detected helmets will be saved in the output directory specified during prediction.

### Result Graphs

![results](https://github.com/user-attachments/assets/0abd55ae-5f95-4ebc-9909-cacebf6816c2)

### Output Predicted Images

Sample output images can be viewed here:

![BikesHelmets345_png_jpg rf 7244b5bec05caa08259ca066911c43e9](https://github.com/user-attachments/assets/be6d5a87-d2da-49db-b802-53af0d2ac265)

![BikesHelmets176_png_jpg rf 80db740fa43cad753ab10b2c62fa7bc6](https://github.com/user-attachments/assets/e1613df8-b3c3-4710-a6a6-c24dc3b6ed9c)

