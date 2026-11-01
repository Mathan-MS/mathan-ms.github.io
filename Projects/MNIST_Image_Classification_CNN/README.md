# MNIST Image Classification Using CNN

## Project Overview

This project develops and evaluates a convolutional neural network (CNN) to recognize handwritten digits from the MNIST dataset. The end-to-end workflow covers image preprocessing, CNN architecture design, model training, validation, test-set evaluation, error analysis, and exporting the trained model.

## Business Problem

Accurately recognizing handwritten digits can support document processing, form digitization, postal automation, and optical character recognition. This project aims to:

- Prepare grayscale handwritten-digit images for CNN training.
- Build and train a convolutional neural network for ten-class classification.
- Monitor training and validation accuracy and loss.
- Measure performance on a separate test dataset.
- Examine classification mistakes using a confusion matrix.
- Save the trained model and analysis outputs for reuse.

## Dataset

The project uses the **MNIST handwritten-digit dataset**, loaded directly through TensorFlow/Keras:

- **60,000** training images and **10,000** test images.
- **28 × 28** grayscale pixels per image.
- **10 classes**, representing digits 0 through 9.

The notebook reshapes the images to include one channel, scales pixel values from 0–255 to 0–1, and one-hot encodes the labels. Keras downloads and caches the dataset automatically when needed; no separate dataset files are required in the repository.

## Tools & Technologies

- Python
- Jupyter Notebook
- NumPy and Pandas
- Matplotlib
- Scikit-learn
- TensorFlow / Keras
- Convolutional Neural Networks (CNNs)

## Project Workflow

1. **Data Loading** — Load the MNIST training and test sets and verify their dimensions.
2. **Image Exploration** — Display sample handwritten digits to inspect the input data.
3. **Image Preprocessing** — Reshape images to `28 × 28 × 1`, normalize pixels, and one-hot encode labels.
4. **CNN Development** — Build a sequential model with 32- and 64-filter convolutional layers, max pooling, dropout, a 128-unit dense layer, and a ten-class softmax output.
5. **Model Training** — Train for five epochs using Adam, categorical cross-entropy, a batch size of 128, and a 10% validation split from the training set.
6. **Training Analysis** — Review epoch-by-epoch training and validation accuracy and loss.
7. **Test Evaluation** — Evaluate the final trained model on the 10,000-image held-out test set.
8. **Error Analysis** — Generate a numerical confusion matrix and visualization to identify digit confusions.
9. **Model Export** — Save the trained Keras model and supporting figures and CSV results.

## Model Evaluation

| Metric | Latest executed result |
|---|---:|
| Test accuracy | **99.00%** |
| Test loss | **0.0309** |
| Correct test predictions | **9,900 / 10,000** |
| Incorrect test predictions | **100 / 10,000** |
| Final training accuracy (epoch 5) | **98.41%** |
| Final validation accuracy (epoch 5) | **98.97%** |
| Final training loss (epoch 5) | **0.0528** |
| Final validation loss (epoch 5) | **0.0361** |

## Visualizations

The notebook generates four PNG files in `figures/`:

- `mnist_sample_training_images.png` — Sample handwritten-digit images.
- `training_validation_accuracy.png` — Training and validation accuracy across five epochs.
- `training_validation_loss.png` — Training and validation loss across five epochs.
- `mnist_confusion_matrix.png` — Test-set confusion matrix by digit class.

Additional saved outputs:

- `results/training_history.csv` — Epoch-level training and validation metrics.
- `results/model_metrics.csv` — Final test evaluation metrics.
- `models/mnist_cnn_model.keras` — Trained Keras model.

## Key Findings

- **Strong held-out performance:** The CNN correctly classified **9,900 of 10,000** test images, achieving **99.00% test accuracy** and **0.0309 test loss**.
- **Improved training performance:** Training accuracy rose from **91.45% in epoch 1** to **98.41% in epoch 5**, while training loss fell from **0.2812 to 0.0528**.
- **High validation accuracy:** Validation accuracy reached **99.00% at epoch 4** and ended at **98.97%** in epoch 5. Validation loss continued decreasing to **0.0361** in the final epoch.
- **Specific classification errors:** The confusion matrix shows occasional errors between handwritten digits with similar shapes, including **5 predicted as 3**, **7 predicted as 2**, and **8 predicted as 9**.
- **Reusable deliverables:** The workflow saves training plots, test metrics, a confusion matrix, and the trained CNN model for later inspection or reuse.

## Outcome

The project demonstrates a complete deep-learning classification workflow, from raw image preparation through evaluation and model export. The **99.00% test accuracy** indicates strong performance on the standard MNIST test set, while the confusion matrix highlights where targeted error analysis could improve the model. The saved artifacts make the work reproducible and suitable for further experimentation.

## Limitations

Performance on MNIST may not generalize to noisier scanned documents or unfamiliar handwriting. The notebook does not report per-class precision and recall, test robustness to image transformations, or compare alternative CNN architectures. The five-epoch run also does not establish an optimal stopping point.

## Installation / Running the Project

### Prerequisites

- Python version compatible with the installed TensorFlow release (Python 3.11 is a practical choice).
- Git.

### Step 1: Clone the Repository

```bash
git clone https://github.com/Mathan-MS/mathan-ms.github.io.git
cd mathan-ms.github.io/Projects/MNIST_Image_Classification_CNN
```

### Step 2: Install Project Dependencies

```bash
python -m pip install -r requirements.txt
```

### Step 3: Launch Jupyter Notebook

```bash
python -m notebook
```

### Step 4: Open and Run the Notebook

Open `notebooks/MNIST_Image_Classification_CNN.ipynb`, select the environment where the dependencies were installed, and choose **Kernel → Restart Kernel and Run All Cells**.

The notebook automatically retrieves MNIST through Keras when necessary and creates the `figures/`, `results/`, and `models/` directories for generated outputs. **Execution time varies depending on system hardware and available resources.**
