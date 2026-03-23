# 🚀 Aero-Predict: AI-Driven Drag Coefficient Estimation

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Gradio UI](https://img.shields.io/badge/UI-Gradio-orange.svg)](https://gradio.app/)


> **Aero-Predict** is an AI-driven pipeline that bridges the gap between 3D design and aerodynamic analysis. By extracting high-dimensional geometric features from `.obj` and `.stl` files, the system leverages a trained **Random Forest Regressor** to instantly predict the **drag coefficient ($C_d$)**. This approach significantly reduces reliance on computationally expensive CFD (Computational Fluid Dynamics) simulations, enabling faster and more efficient evaluation during the early stages of design.

This project empowers mechanical engineers, automotive designers, and hobbyists to rapidly iterate on designs without the immediate computational overhead and time constraints of complex CFD (Computational Fluid Dynamics) simulations.

![UI Preview](https://drive.google.com/uc?id=1wKwWfMDWndvWveuo9i7-wiTUn2mzJzFb)

---

## 📽️ Interactive Demo

Watch Aero-Predict in action. The tool visualizes the mesh, calculates geometric properties in the background, and outputs the predicted C_d instantly.

https://github.com/user-attachments/assets/48e8113f-14ee-4d2f-8adf-6b8004fe0772

---

## ✨ Key Features

* **⚡ Instantaneous Inference:** Obtain actionable aerodynamic insights in seconds, drastically reducing the traditional CFD waiting period during early-stage prototyping.
* **📐 Automated Geometric Intelligence:** The backend automatically parses 3D meshes to extract vital aerodynamic predictors, including volume, surface area, bounding box dimensions, and cross-sectional frontal area.
* **📊 Robust ML Backend:** Powered by an ensemble Random Forest model trained on a diverse dataset of automotive and aerodynamic geometries.
* **👁️ Integrated 3D Visualization:** Inspect and interact with your uploaded 3D models directly within the browser before running predictions.
* **🖱️ Frictionless UI:** Built entirely on Gradio, offering a clean, drag-and-drop web interface accessible to users of all technical levels.

---

## 🧠 System Architecture & Workflow

Aero-Predict operates on a streamlined, multi-stage pipeline that transforms raw 3D geometry into actionable aerodynamic metrics:

1.  **Data Ingestion (UI Layer):** The user uploads a `.obj` or `.stl` file via the Gradio web interface. The file is temporarily cached for processing.
2.  **Mesh Parsing & Feature Engineering:** The Python backend reconstructs the 3D mesh. Mathematical algorithms calculate a comprehensive suite of geometric features that influence drag, including:
    * *Projected Frontal Area* (the silhouette exposed to the wind).
    * *Total Surface Area & Mesh Volume*.
    * *Aspect Ratios* (Length/Width/Height proportions extracted from the bounding box).
3.  **Data Normalization:** The extracted raw features are passed through a pre-fitted Standard Scaler (`scaler.pkl`) to normalize the data, ensuring it matches the distribution of the original training dataset.
4.  **Machine Learning Inference:** The normalized feature vector is fed into our trained `RandomForestRegressor` model (`drag__coefficient__model.pkl`). The model leverages learned non-linear relationships between shape parameters and air resistance to estimate the final C_d.
5.  **Output Generation:** The predicted Drag Coefficient is returned to the Gradio frontend alongside an interactive 3D plot of the ingested mesh.

---

## 📂 Repository Structure

```text
├── Models/
│   ├── drag__coefficient__model.pkl   # Trained Random Forest model
│   └── scaler.pkl                     # Feature normalization scaler
├── assets/
│   └── Screen Recording.mp4           # Demo video
├── data/
│   ├── sample .obj/                   # Directory of sample 3D shapes for testing
│   ├── dataset.txt                    # Extracted features dataset used for training
│   └── drag_coefficients.xlsx         # Target variables mapping
├── src/
│   └── Aero_Predict.ipynb             # Main pipeline and Gradio UI execution
├── LICENSE                            # MIT License file
├── README.md                          # Project documentation
└── requirements.txt                   # Python dependencies
```
---

## 🔮 Future Enhancements
- ✅ **Deep Learning Integration** – Explore 3D CNNs and PointNet for direct mesh-based predictions  
- ✅ **Expanded 3D Format Support** – Add compatibility for formats like `.GLB`, `.GLTF`, and `.FBX`  
- ✅ **Advanced 3D Visualizations** – Introduce drag/pressure heatmaps and improved mesh interaction tools  
- 🚧 **API Development** – Build a FastAPI backend for integration with external tools and CAD software  
---

## 📜 License  
This project is licensed under the [MIT License](LICENSE).  
You are free to use, modify, and distribute this software with proper attribution.  
