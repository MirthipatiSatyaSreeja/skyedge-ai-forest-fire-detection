# SkyEdge AI – Forest Fire Detection

## 1. Project Overview

SkyEdge AI is a deep learning-based forest fire detection system designed to classify forest images into three categories:

* No Fire
* Fire
* Start Fire

The project uses image preprocessing and InceptionV3 transfer learning to analyze forest images and identify the presence or early stage of fire.

The main objective of the project is to demonstrate how computer vision and deep learning can be used for forest fire detection.

## 2. Project Objective

The objective of SkyEdge AI is to develop an image-based forest fire detection system that can automatically classify an input image based on its fire condition.

The system processes an image, prepares it for the deep learning model, and predicts one of the three classes:

| Label | Class      |
| ----: | ---------- |
|     0 | No Fire    |
|     1 | Fire       |
|     2 | Start Fire |

## 3. Technologies Used

* Python
* TensorFlow
* Keras
* InceptionV3
* OpenCV
* NumPy
* Scikit-learn
* Scikit-image
* Matplotlib
* Jupyter Notebook / Google Colab

## 4. Model Used

The project uses InceptionV3 with pretrained ImageNet weights.

The pretrained convolutional layers are used as the base feature extractor, and additional fully connected layers are added for the three-class forest fire classification task.

The model structure consists of:

```text
Input Image
     |
     v
InceptionV3
     |
     v
Global Max Pooling
     |
     v
Dense Layer - 2048 neurons
     |
     v
Dense Layer - 1024 neurons
     |
     v
Output Layer - 3 classes
     |
     v
Fire Condition Prediction
```

## 5. Image Preprocessing

The input images are read using OpenCV and resized to:

```text
224 × 224 × 3
```

Image resizing is performed before the images are provided to the InceptionV3 model.

The processed images are stored as NumPy arrays for model training and testing.

## 6. Dataset Processing

The project reads images from the Forest Fire Dataset.

The dataset folders are used to assign class labels:

```text
fire       → Fire
start_fire → Start Fire
other      → No Fire
```

The image data and corresponding labels are then converted into NumPy arrays.

## 7. Dataset Splitting

The processed dataset is divided into training, validation, and testing data.

The training data is used to train the model.

The validation data is used to monitor model performance during training.

The test data is used to evaluate the final model performance.

## 8. Model Training

The InceptionV3 base model is used with its pretrained layers frozen.

Additional dense layers are added for the forest fire classification task.

The model is trained using:

```text
Optimizer: Adam
Loss Function: Categorical Crossentropy
Output Activation: Softmax
Evaluation Metric: Accuracy
```

## 9. Prediction

After training, the model is used to predict the class of test images.

The output corresponds to one of the three fire conditions:

```text
No Fire
Fire
Start Fire
```

The notebook also contains a function for testing an individual image.

## 10. Model Evaluation

The model performance is evaluated using:

* Test accuracy
* Classification report
* Confusion matrix
* Training and validation accuracy

These evaluation methods help to understand how accurately the model distinguishes between the three classes.

## 11. Project Workflow

```text
Forest Fire Dataset
        |
        v
Image Loading
        |
        v
Image Preprocessing
        |
        v
Resize to 224 × 224 × 3
        |
        v
Label Encoding
        |
        v
Train / Validation / Test Split
        |
        v
InceptionV3 Transfer Learning
        |
        v
Model Training
        |
        v
Model Evaluation
        |
        v
Fire Condition Prediction
```

## 12. Repository Structure

```text
skyedge-ai-forest-fire-detection/
│
├── SkyEdge_AI_Forest_Fire_Detection.ipynb
│
└── README.md
```

## 13. How to Run

### Step 1: Clone the repository

Clone this repository to your computer.

### Step 2: Open the notebook

Open:

```text
SkyEdge_AI_Forest_Fire_Detection.ipynb
```

using Jupyter Notebook, JupyterLab, or Google Colab.

### Step 3: Add the dataset

Place the Forest Fire Dataset in the appropriate project location.

The dataset should contain the class folders used by the notebook.

### Step 4: Install the required libraries

The project uses Python libraries including:

```text
tensorflow
opencv-python
numpy
scikit-learn
scikit-image
matplotlib
tqdm
```

### Step 5: Run the notebook

Run the notebook cells in order to:

1. Load the dataset
2. Preprocess the images
3. Encode the labels
4. Split the dataset
5. Build the InceptionV3 model
6. Train the model
7. Evaluate the model
8. Generate predictions

## 14. Results

The notebook generates model evaluation results including:

* Training accuracy
* Validation accuracy
* Test accuracy
* Classification report
* Confusion matrix

The exact numerical results should be taken from the final model execution.

## 15. Future Improvements

Possible future improvements include:

* Real-time forest fire detection
* Video-based fire detection
* Drone-based image acquisition
* Edge AI deployment
* Model optimization for embedded hardware
* Real-time alerts
* Additional fire and smoke classes
* Deployment on edge computing devices
