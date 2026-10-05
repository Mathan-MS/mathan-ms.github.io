# MNIST Image Classification Using CNN

## Project Overview

This project builds a convolutional neural network (CNN) to classify handwritten digits from the MNIST dataset.

The workflow includes image preprocessing, CNN model construction, model training, training-history analysis, test evaluation, confusion-matrix analysis, and model saving.

## Business / Research Problem

Handwritten-digit recognition is a classic image-classification problem with applications in document processing, form digitization, postal automation, and optical character recognition.

This project explores whether a convolutional neural network can accurately classify handwritten digits from 0 through 9 using pixel-level image information.

## Dataset

The project uses the MNIST handwritten-digit dataset available through TensorFlow/Keras.

The dataset contains:

- 60,000 training images
- 10,000 test images
- 28 × 28 grayscale images
- 10 digit classes from 0 through 9

Because the dataset is downloaded automatically through Keras, a separate `data/` folder is not required for this project.

## Methods

The project follows these main steps:

1. Load the MNIST dataset
2. Preview sample training images
3. Reshape and normalize image data
4. One-hot encode target labels
5. Build a convolutional neural network
6. Train the model for five epochs
7. Review training and validation performance
8. Evaluate the model on the test dataset
9. Generate a confusion matrix
10. Save evaluation results and the trained model

## CNN Architecture

The model includes:

- Conv2D layer with 32 filters
- Conv2D layer with 64 filters
- MaxPooling2D layer
- Dropout regularization
- Flatten layer
- Dense layer with 128 units
- Dropout regularization
- Softmax output layer with 10 classes

The model uses the Adam optimizer and categorical cross-entropy loss.

## Tools and Technologies

- Python
- Jupyter Notebook
- NumPy
- pandas
- Matplotlib
- scikit-learn
- TensorFlow
- Keras
- Convolutional Neural Networks

## Project Outputs

### Figures

`figures/`

- `mnist_sample_training_images.png`
- `training_validation_accuracy.png`
- `training_validation_loss.png`
- `mnist_confusion_matrix.png`

### Results

`results/`

- `training_history.csv`
- `model_metrics.csv`

### Model

`models/`

- `mnist_cnn_model.keras`

## Repository Structure

```text
MNIST_CNN_Image_Classification/
│
├── README.md
│
├── figures/
│   ├── mnist_sample_training_images.png
│   ├── training_validation_accuracy.png
│   ├── training_validation_loss.png
│   └── mnist_confusion_matrix.png
│
├── results/
│   ├── training_history.csv
│   └── model_metrics.csv
│
├── models/
│   └── mnist_cnn_model.keras
│
└── notebooks/
    └── MNIST_CNN_Image_Classification.ipynb
```

## How to Run the Project

1. Clone the repository.

2. Install the required Python packages:

```bash
pip install numpy pandas matplotlib scikit-learn tensorflow
```

3. Open:

```text
notebooks/MNIST_CNN_Image_Classification.ipynb
```

4. Run the notebook cells in order.

The MNIST dataset is downloaded automatically through TensorFlow/Keras.

The notebook automatically creates the `figures/`, `results/`, and `models/` folders if they do not already exist.

## Key Skills Demonstrated

- Deep learning
- Convolutional neural networks
- Image preprocessing
- Image classification
- TensorFlow and Keras
- Model training and validation
- Confusion-matrix analysis
- Model evaluation
- Training-history visualization
- Model persistence

## Outcome

The project demonstrates an end-to-end CNN image-classification workflow for handwritten-digit recognition. Model performance is evaluated on unseen test images and supported by training-history plots, test metrics, and a confusion matrix.

## Limitations

MNIST is a well-structured benchmark dataset with centered grayscale digits, so performance on MNIST may not represent performance on real-world handwritten images with varying backgrounds, lighting, orientation, or image quality.

## Future Improvements

Potential enhancements include:

- Data augmentation
- Additional convolutional layers
- Hyperparameter tuning
- Early stopping
- Learning-rate scheduling
- Testing the trained model on custom handwritten digits
- Deploying the model through a simple web interface
