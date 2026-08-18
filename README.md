# 🛣️ Lane Segmentation with Deep Learning

A deep learning project for **road lane segmentation** using image segmentation techniques.

The project works with road images and their corresponding binary masks, where the target is to distinguish **lane lines** from the **background**. The dataset contains **4,759 valid image-mask pairs**.

<img width="1763" height="511" alt="image" src="https://github.com/user-attachments/assets/b99c87e7-0163-48b4-9cff-3e3cd9b49ac0" />

<img width="1752" height="606" alt="image" src="https://github.com/user-attachments/assets/df5c49a0-b75c-4236-8f30-064c9d257a19" />


---

## 📁 Project Structure

```
Lane-Segmentation/
│
├── dataset/
│   ├── frames/
│   │   └── *.png
│   │
│   └── lane-masks/
│       └── *.png
│
├── notebooks/
│   └── lane_segmentation.ipynb
│
├── requirements.txt
│
└── README.md

```

---

## 🗂️ 1. Dataset

The dataset is organized into two main directories:

```
dataset/
├── frames/
└── lane-masks/

```

### 🖼️ Frames

The `frames/` directory contains the original road images used as input to the segmentation model.

```
dataset/frames/
├── img001.png
├── img002.png
├── img003.png
└── ...

```

### 🎭 Lane Masks

The `lane-masks/` directory contains the corresponding segmentation masks.

```
dataset/lane-masks/
├── img001.png
├── img002.png
├── img003.png
└── ...

```

Each image is matched with a mask having the same filename.

The notebook checks whether a corresponding mask exists for each image and only keeps valid image-mask pairs.

### 📊 Dataset Split

A total of **4,759 valid image-mask pairs** were identified.

The data is split into:

| SplitSamples |       |
| ------------ | ----- |
| Training     | 4,283 |
| Validation   | 476   |
| Total        | 4,759 |

The validation set contains **10%** of the available data, using `random_state=42`.

---

## 📓 2. Notebook

The main implementation is provided in:

```
notebooks/lane_segmentation.ipynb

```

The notebook covers the complete workflow from loading and validating the dataset to preparing the data for segmentation.

### 🔹 Main Steps

#### 1. Import Libraries

The project uses:

- OpenCV
- NumPy
- Matplotlib
- TensorFlow
- Keras
- Scikit-learn

These libraries are imported in the notebook for image processing, visualization, model development, and dataset splitting.

#### 2. Load Dataset

The dataset paths are defined as:

```
DATASET_PATH = "./dataset/"

image_base_path = "./dataset/frames"
mask_base_path = "./dataset/lane-masks"

```

#### 3. Validate Image-Mask Pairs

The notebook checks the dataset and creates two lists:

```
all_image_paths = []
all_mask_paths = []

```

Only images that have a corresponding mask are added to the dataset.

#### 4. Visualize Images and Masks

The notebook includes visualization steps for checking whether images and their corresponding masks are correctly matched before training.

#### 5. Train / Validation Split

The valid image-mask pairs are divided into training and validation sets:

```
train_images, val_images, train_masks, val_masks = train_test_split(
    all_image_paths,
    all_mask_paths,
    test_size=0.1,
    random_state=42
)

```

---

## 📦 3. Requirements

Create a `requirements.txt` file containing the required Python packages:

```
numpy
opencv-python
matplotlib
tensorflow
keras
scikit-learn

```

Install the dependencies with:

```
pip install -r requirements.txt

```

### 🔧 Environment

Recommended:

```
Python 3.x
TensorFlow
Keras
OpenCV
NumPy
Matplotlib
Scikit-learn

```

---

## 🎯 Project Goal

The goal of this project is to build an image segmentation pipeline capable of identifying **road lanes** from road images.

The input is a road image:

```
Road Image
     │
     ▼
Segmentation Model
     │
     ▼
Lane Mask

```

The segmentation target consists of two regions:

```
0 → Background
1 → Lane

```

---

## 🚀 Quick Start

Clone the repository:

```
git clone <YOUR-REPOSITORY-URL>
cd Lane-Segmentation

```

Install dependencies:

```
pip install -r requirements.txt

```

Place the dataset inside:

```
dataset/
├── frames/
└── lane-masks/

```

Then open the notebook:

```
notebooks/lane_segmentation.ipynb

```

and run the cells sequentially.

---

## 📌 Notes

- Image and mask filenames must correspond to each other.
- Images without a corresponding mask are ignored.
- The current notebook uses a **90/10 training-validation split**.
- The dataset contains **4,759 valid image-mask pairs**.
- The project focuses on **binary lane segmentation**.
