# 🚀 Aero-Predict: Drag Coefficient Prediction from 3D Models

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Gradio UI](https://img.shields.io/badge/UI-Gradio-orange.svg)](https://gradio.app/)

**Aero-Predict** is an AI-powered pipeline designed to bridge the gap between 3D design and aerodynamic analysis. By extracting high-dimensional geometric features from `.obj` and `.stl` files, the tool uses a trained **RandomForestRegressor** to predict the **Drag Coefficient ($C_d$)** instantly, bypassing the need for time-consuming CFD (Computational Fluid Dynamics) simulations during early-stage design.

![UI Preview](https://drive.google.com/uc?id=1wKwWfMDWndvWveuo9i7-wiTUn2mzJzFb)

---

## 📽️ Interactive Demo
See Aero-Predict in action. The tool visualizes the mesh, calculates geometric properties, and outputs the predicted $C_d$ in seconds.

https://github.com/user-attachments/assets/ef8849b2-2977-47b6-94e8-42289c09c733

---
---

## ✨ Features
* **Instant Prediction:** Get aerodynamic insights without waiting for hours of CFD rendering.
* **Geometric Intelligence:** Automatically extracts volume, surface area, and bounding box dimensions.
* **3D Visualization:** Integrated 3D viewer to inspect models before running the prediction.
* **Robust ML Backend:** Powered by a Random Forest ensemble model trained on diverse automotive geometries.
* **User-Friendly Interface:** Built with Gradio for a seamless, "drag-and-drop" experience.

---

## 🛠️ How It Works
1.  **Preprocessing:** The uploaded 3D file is parsed to extract raw vertex and face data.
2.  **Feature Extraction:** The system calculates critical aerodynamic predictors:
    * Projected Frontal Area
    * Total Surface Area & Volume
    * Length/Width/Height Ratios
3.  **Inference:** These features are fed into a **RandomForestRegressor** which has learned the relationship between shape and air resistance.

---


## 🔮 Future Enhancements
- ✅ **Deep Learning Model Integration**  
- ✅ **Support for Additional 3D Formats** (e.g., GLB, FBX)  
- ✅ **More Advanced 3D Visualizations**

## 📜 License  
This project is licensed under the [MIT License](LICENSE).  



