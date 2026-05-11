# 📸 Real-Time Smart Attendance System with InsightFace

![Python](https://img.shields.io/badge/Python-3.x-blue)
![InsightFace](https://img.shields.io/badge/Library-InsightFace-orange)
![Anaconda](https://img.shields.io/badge/Environment-Anaconda-green)
![Status](https://img.shields.io/badge/Status-Prototype-success)

## 📖 Project Overview
This project is a high-accuracy, real-time attendance system leveraging the **InsightFace** library for deep learning-based face analysis. Unlike standard detection systems, InsightFace offers robust performance even in varying lighting conditions.

The system employs a **Hybrid Workflow**:
1.  **Cloud Side (Google Colab):** Heavy lifting for feature extraction and generating face embeddings (training phase) to create the model file (`.pkl`).
2.  **Local Side (Anaconda Environment):** Lightweight real-time inference using a webcam to mark attendance directly into an **Excel spreadsheet**.

**Key Features:**
* **High Accuracy:** Uses InsightFace (ArcFace) for state-of-the-art detection.
* **Real-Time Processing:** Instantly detects faces via Webcam.
* **Automated Export:** Attendance logs are automatically saved to `.csv` (Excel).
* **Portable Model:** Uses a serialized `.pkl` file for easy deployment on local machines.

## 🛠️ Tech Stack
* **Language:** Python
* **Core Library:** InsightFace, OpenCV, Pandas (for Excel export), SciPy (for classification)
* **Environment:** Anaconda (Conda)
* **Training/Preprocessing:** Google Colab
* **Output:** Excel Report

## ⚙️ Workflow Architecture
To ensure performance efficiency, the workflow is split:
1.  **Face Registration:** Images are uploaded to Google Colab to generate face embeddings.
2.  **Model Generation:** A `.pkl` file containing the known face encodings is downloaded.
3.  **Deployment:** The `.pkl` file and `veriface.py` script are run locally via Anaconda to start the webcam.

## 🚀 How to Run (Local Deployment)

### Prerequisites
* Anaconda installed on your machine.
* Webcam attached.

### Step-by-Step Guide
1.  **Clone this Repository**
    ```bash
    git clone https://github.com/yosukeyung/Veriface.git
    cd repo-name
    ```

2.  **Prepare the Environment**
    Open **Anaconda Prompt** and create a new environment (optional but recommended):
    ```bash
    conda create -n face-attendance python=3.8
    conda activate face-attendance
    ```

3.  **Install Dependencies**
    *(Make sure you have requirements.txt, or install manually)*
    ```bash
    pip install -r requirements.txt
    ```

4.  **Setup Files**
    * Ensure `veriface.py` is in the folder.
    * Ensure the latest `.pkl` model file (downloaded from Colab) is placed in the same directory.

5.  **Run the System**
    In Anaconda Prompt, run:
    ```bash
    python veriface.py
    ```

6.  **Usage**
    * The webcam window will open automatically.
    * When a face is recognized, the system logs the name and timestamp.
    * Check the generated **Excel file** in the folder for the attendance report.

## 📂 Note on Dataset
To protect privacy, the raw training images and the `.pkl` file containing biometric data are **excluded** from this repository. This repo focuses on the inference logic (`veriface.py`).

---
**Author:** Yosuke Yung
*CS Student @ BINUS UNIVERSITY*


