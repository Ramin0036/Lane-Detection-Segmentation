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
├── dataset
│
├── notebooks/
│   └── lane_segmentation.ipynb
│
├── requirements.txt
│
└── README.md

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
git clone <https://github.com/Ramin0036/Lane-Detection-Segmentation/tree/main>
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
