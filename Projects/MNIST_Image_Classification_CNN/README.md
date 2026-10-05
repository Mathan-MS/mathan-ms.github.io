# MNIST Image Classification Using CNN

## Project Overview

This project builds a convolutional neural network (CNN) to classify handwritten digits from the MNIST dataset.

The workflow includes image preprocessing, CNN model construction, model training, training-history analysis, test evaluation, confusion-matrix analysis, and model saving.

## Business Problem

Handwritten-digit recognition has applications in document processing, form digitization, postal automation, and optical character recognition.

This project is aimed at accomplishing the following goals:

- Prepare handwritten-digit images for deep-learning classification.
- Build a convolutional neural network.
- Train the model on MNIST images.
- Evaluate the model on unseen test images.
- Analyze classification errors with a confusion matrix.

## Dataset

The project uses the MNIST handwritten-digit dataset available through TensorFlow/Keras.

The dataset contains:

- 60,000 training images
- 10,000 test images
- 28 × 28 grayscale images
- 10 digit classes from 0 through 9

The dataset is downloaded automatically through Keras.

## Tools & Technologies

- Python
- Jupyter Notebook
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- TensorFlow
- Keras
- Convolutional Neural Networks

## Project Workflow

The project follows these main steps:

1. **Data Loading**
   - Loaded the MNIST training and test datasets.

2. **Image Preprocessing**
   - Reshaped the images for CNN input.
   - Normalized pixel values.
   - One-hot encoded target labels.

3. **Model Development**
   - Built a CNN with convolutional, pooling, dropout, dense, and softmax layers.

4. **Model Training**
   - Trained the CNN for five epochs.

5. **Training Evaluation**
   - Reviewed training and validation accuracy and loss.

6. **Test Evaluation**
   - Evaluated performance on unseen test images.

7. **Error Analysis**
   - Generated a confusion matrix to review classification errors.

8. **Model Saving**
   - Saved the trained Keras model for reuse.

## Model Evaluation

The model was evaluated using:

- Training Accuracy
- Validation Accuracy
- Training Loss
- Validation Loss
- Test Accuracy
- Test Loss
- Confusion Matrix

## Key Findings

The CNN correctly classifies the majority of handwritten digits.

Most values in the confusion matrix appear along the diagonal, while the remaining errors generally occur between digits with similar handwritten shapes.

## Outcome

This project demonstrates an end-to-end deep-learning workflow for handwritten-digit classification.

The final output includes a trained CNN model, evaluation metrics, training-history visualizations, and a confusion matrix.

## Installation / Running the Project

1. Clone the repository:

```bash
git clone <repo_url>
cd <repository_name>
```

2. Install the required packages:

```bash
pip install -r requirements.txt
```

3. Launch Jupyter Notebook:

```bash
jupyter notebook
```

4. Open and run:

`notebooks/MNIST_CNN_Image_Classification.ipynb`
