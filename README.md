# Farm AI Models 🌱

A collection of deep learning and machine learning notebooks for **plant disease classification** across eight crops: apple, banana, cotton, grapes, mango, rice, sugarcane, and wheat.

This repository contains the model-development notebooks for the Farm AI project. Each notebook explores an image-based classification workflow for identifying crop health conditions or disease categories from plant images.

## 🌾 Project Overview

Plant diseases can affect crop quality, productivity, and agricultural sustainability. Image classification models can help identify visible symptoms and support early investigation of possible plant diseases.

The goal of this project is to experiment with crop-specific models using image preprocessing, data augmentation, deep learning architectures, transfer learning, and model evaluation.

## 📂 Repository Contents

| Notebook | Crop | Approach |
|---|---|---|
| `apple-model.ipynb` | Apple 🍎 | Xception-based transfer learning |
| `banana-model.ipynb` | Banana 🍌 | Vision Transformer (ViT-B/16) |
| `cotton.ipynb` | Cotton | Custom CNN-based classification |
| `grapes-disease.ipynb` | Grapes 🍇 | CNN-based disease classification |
| `mango-model.ipynb` | Mango 🥭 | VGG16 transfer learning |
| `rice-diseases.ipynb` | Rice 🌾 | Deep learning image classification |
| `sugarcane-model.ipynb` | Sugarcane | ResNet50 transfer learning |
| `wheat-diseases.ipynb` | Wheat 🌿 | CNN-based image classification |

*The approaches listed above describe the architectures or workflows present in the notebooks. Exact performance depends on the dataset, training configuration, and evaluation split.*

## 🔬 Individual Projects

### 1. Apple Disease Classification

**Notebook:** `apple-model.ipynb`

- **Objective:** Classify apple leaf images into the categories represented in the training dataset.
- **Model:** Xception with pretrained weights.
- **Framework:** TensorFlow and Keras.
- **Workflow:** Load images from class-based folders, rescale and augment images, train a classification head with a pretrained image backbone, and evaluate predictions.
- **Training support:** Early stopping, model checkpointing, and learning-rate reduction callbacks.

**Why Xception?** Its depthwise separable convolutions can extract useful image features while reducing computation compared with standard convolutions in many settings.

### 2. Banana Disease Classification

**Notebook:** `banana-model.ipynb`

- **Objective:** Classify banana images into the dataset's disease or health categories.
- **Model:** Vision Transformer, ViT-B/16.
- **Framework:** PyTorch and Torchvision.
- **Workflow:** Prepare image paths and labels, apply image transformations, create dataset and data-loader objects, fine-tune a pretrained Vision Transformer, and evaluate classification predictions.

**Why a Vision Transformer?** It divides images into patches and uses attention to learn relationships between image regions, providing an alternative to conventional convolutional networks.

### 3. Cotton Disease Classification

**Notebook:** `cotton.ipynb`

- **Objective:** Classify cotton plant images across six dataset categories.
- **Model:** Convolutional Neural Network (CNN).
- **Framework:** TensorFlow and Keras.
- **Workflow:** Organize images by class, split the data for training and validation, augment training images, train the CNN, and inspect its classification performance.
- **Evaluation:** Confusion matrix and classification report.

**Why a CNN?** Convolutional layers learn visual patterns such as edges, textures, and leaf symptoms that can help distinguish image categories.

### 4. Grapes Disease Classification

**Notebook:** `grapes-disease.ipynb`

- **Objective:** Categorize grape-related plant images according to the labels in the dataset.
- **Model:** Custom CNN-based image classifier.
- **Framework:** TensorFlow and Keras, with OpenCV and NumPy for image processing.
- **Workflow:** Load and process images, encode class labels, train a CNN, use training callbacks, and compare predictions against the expected labels.
- **Evaluation:** Accuracy and classification-report metrics.

**Why a custom CNN?** A task-specific network offers a flexible starting point for learning disease-related visual features from the selected dataset.

### 5. Mango Disease Classification

**Notebook:** `mango-model.ipynb`

- **Objective:** Identify the categories represented in the mango image dataset.
- **Model:** VGG16 with pretrained ImageNet weights.
- **Framework:** TensorFlow and Keras.
- **Workflow:** Load and augment images, reuse pretrained visual features, add a classification head, train the model, and evaluate its predictions.
- **Evaluation:** Confusion matrix and classification report.

**Why VGG16?** Its pretrained convolutional layers provide reusable visual features that can be adapted to a crop-specific classification task.

### 6. Rice Disease Classification

**Notebook:** `rice-diseases.ipynb`

- **Objective:** Classify rice leaf images into the available disease categories.
- **Framework:** TensorFlow and Keras.
- **Workflow:** Read class folders, prepare training images, apply augmentation, train an image-classification network, and evaluate results.
- **Additional techniques:** Class-weight calculation, early stopping, and learning-rate reduction are included in the workflow.

**Why consider class weights?** When some disease categories have fewer training images than others, class weighting can help reduce the tendency to favor more frequent categories.

### 7. Sugarcane Disease Classification

**Notebook:** `sugarcane-model.ipynb`

- **Objective:** Classify sugarcane images into five categories: Healthy, Mosaic, RedRot, Rust, and Yellow.
- **Model:** ResNet50 with pretrained ImageNet weights.
- **Framework:** PyTorch and Torchvision.
- **Workflow:** Transform input images, prepare data loaders, adapt the pretrained model's output layer, train on the selected dataset, and generate a classification report.
- **Hardware support:** The notebook selects CUDA when available and otherwise uses the CPU.

**Why ResNet50?** Residual connections help train deeper networks and allow pretrained image features to be adapted to the target task.

### 8. Wheat Disease Classification

**Notebook:** `wheat-diseases.ipynb`

- **Objective:** Classify wheat plant images into the categories available in the dataset.
- **Framework:** Keras and TensorFlow.
- **Workflow:** Prepare training, validation, and test image generators, train a CNN-based classifier, generate predictions, and evaluate the test set.
- **Evaluation:** Confusion matrix and classification report.

**Why evaluate on separate data?** A held-out test set provides a more meaningful estimate of performance on unseen images than training accuracy alone.

## ⚙️ Common Machine Learning Workflow

The notebooks follow variations of this workflow:

1. **Data collection:** Use the image dataset configured in each notebook.
2. **Data exploration:** Inspect image folders, labels, and available categories.
3. **Preprocessing:** Resize or transform images and normalize pixel values where required.
4. **Data augmentation:** Apply suitable transformations to training images to increase input diversity.
5. **Model development:** Train a custom CNN or adapt a pretrained architecture.
6. **Model training:** Optimize model parameters using the selected loss function and optimizer.
7. **Evaluation:** Use metrics such as accuracy, precision, recall, F1-score, and confusion matrices where implemented.
8. **Analysis:** Examine classification errors and consider improvements to the data, model, or training setup.

## 🧰 Technologies Used

- **Python** — primary programming language
- **Jupyter Notebook** — interactive experimentation and documentation
- **TensorFlow / Keras** — deep learning and image classification
- **PyTorch / Torchvision** — Vision Transformer and ResNet-based workflows
- **NumPy and Pandas** — numerical and tabular data operations
- **Matplotlib and Seaborn** — visualizations
- **OpenCV and Pillow** — image processing and loading
- **Scikit-learn** — data splitting and model evaluation utilities

Not every library is used in every notebook.

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/sparshpatidar2005/FARMAI_MODELS.git
cd FARMAI_MODELS
```

### 2. Create a virtual environment

**Windows PowerShell:**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks activation, you can use the Python executable inside `.venv` directly or follow your local Python environment's activation guidance.

### 3. Install the required libraries

For notebooks using TensorFlow:

```bash
pip install tensorflow numpy pandas matplotlib seaborn scikit-learn opencv-python pillow jupyter
```

For notebooks using PyTorch and Torchvision, install compatible versions for your operating system and hardware by following the official PyTorch installation guide:

https://pytorch.org/get-started/locally/

Some notebooks may require additional packages. Check the imports at the beginning of the notebook before running it.

### 4. Open Jupyter Notebook

```bash
jupyter notebook
```

Open the notebook you want to explore and run its cells in order.

## 🗂️ Dataset Requirements

The notebooks use datasets configured in their code, including paths associated with Kaggle environments. These paths may not exist on another computer.

Before training:

1. Obtain the corresponding dataset and check its usage license.
2. Update the dataset path in the notebook to point to your local files.
3. Preserve the expected directory and class-label structure.
4. Check that the training, validation, and test data are separated appropriately.

**Dataset files and trained model weights are not guaranteed to be included in this repository.** Refer to each notebook for its specific data requirements.

## 📊 Results and Evaluation

Each notebook contains its own training and evaluation workflow. Results can vary with dataset versions, class distribution, preprocessing, random seeds, hardware, and training parameters.

For a fair comparison between approaches, use the same dataset split and evaluation protocol wherever possible. Consider per-class precision, recall, F1-score, confusion matrices, and class imbalance rather than relying only on accuracy.

No single overall accuracy is claimed for the entire repository because these are separate crop-specific classification experiments.

## 🔭 Future Improvements

- Build a unified interface to select a crop and classify an uploaded image.
- Standardize preprocessing and evaluation across all eight models.
- Save and version trained weights for reproducible inference.
- Add per-class metrics and error-analysis visualizations.
- Evaluate generalization on images collected outside the training datasets.
- Integrate model inference into the wider Farm AI application.
- Explore model optimization for mobile or edge deployment.

## ⚠️ Limitations and Responsible Use

These notebooks are experimental machine learning projects, not a substitute for professional agricultural diagnosis. Image predictions may be incorrect when images are blurry, lighting differs from training data, symptoms overlap, or a plant condition is not represented in the dataset.

Validate models on representative field images before considering real-world use. Do not make pesticide or treatment decisions based solely on a model prediction.

## 📄 License

No license is specified by this README. Add a license only after confirming that you have permission to publish the code and that the dataset and other included materials allow the intended use.

---

**Farm AI Models** — crop-specific image classification experiments for exploring AI-assisted plant health analysis.
