<div align="center">

# 🫀 AI-Powered Heart MRI Classification

[![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-2.x-000000?logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00?logo=tensorflow&logoColor=white)](https://www.tensorflow.org/)
[![IBM Cloud](https://img.shields.io/badge/IBM%20Cloud-Services-052FAD?logo=ibmcloud&logoColor=white)](https://www.ibm.com/cloud)


### 💎 Project Status: <img alt="Selected" src="https://img.shields.io/badge/Selected-IBM%20Finalist-052FAD?logo=ibm&logoColor=white" />

**Revolutionizing Cardiac Diagnosis with AI-Powered MRI Analysis**

</div>

---

## 🚀 Overview
This project demonstrates an end-to-end AI system that classifies cardiac MRI images into clinical categories and explains its predictions. Built to showcase strong engineering practices and medical AI rigor for IBM selection.

- 🧠 Deep learning pipeline with explainability (Grad-CAM)
- 🌐 Production-ready Flask web app for clinicians
- ☁️ Cloud-native storage and deployment on IBM Cloud
- 🔒 Privacy-by-design with audit-friendly logging

---

## 📌 Highlights
- 💡 Smart Inference: Classifies MRI slices/series with confidence scores
- 🗺️ Explainable AI: Heatmaps to visualize model attention (Grad-CAM)
- ⚡ Fast & Robust: Optimized preprocessing and batched inference
- 🛡️ Clinical Safety: Thresholding, disclaimers, and review workflows
- 🧾 Traceability: Request IDs, structured logs, and versioned models

---

## 🧩 Key Features
- 🖼️ Image Upload & Preview — Drag-and-drop MRI DICOM/PNG/JPG
- 🤖 AI Classification — CNN-based model with calibrated probabilities
- 🔍 Explainability — Per-image attribution maps and downloadable overlays
- 👥 Patient Management — Minimal demo DB for case tracking
- 🖥️ Web UI — Clean, responsive interface built with Flask + Bootstrap
- 📦 Deployment — Dockerized app ready for IBM Cloud Foundry/Code Engine

---

## 🛠️ Technology Stack
- 🐍 Python 3.9+
- 🔶 TensorFlow 2.x / Keras
- 🧪 OpenCV, NumPy, Pandas, scikit-image
- 🌶️ Flask, Jinja, Bootstrap, Gunicorn
- 🗄️ IBM Db2 (optional demo), SQLite (local)
- ☁️ IBM Cloud Object Storage for image artifacts

> Tip: Swap in PyTorch easily—architecture is modular.

---

## 📊 Project Workflow

| Stage | Input | Processing | Output |
|---|---|---|---|
| 1. Ingest | MRI (DICOM/PNG) | Validate, anonymize, normalize | Clean tensor |
| 2. Preprocess | Tensors | Resize, center-crop, z-score | Model-ready batch |
| 3. Inference | Batch | CNN forward pass | Class + confidence |
| 4. Explainability | Image + grads | Grad-CAM/Score-CAM | Heatmap overlay |
| 5. Store | Results/meta | COS/DB write, versioning | Traceable record |
| 6. Serve | HTTP request | Flask controller + templates | UI + JSON response |

---

## 🧪 Sample Results & Screenshots
- Model prediction view with confidence bar
- Grad-CAM heatmap overlay on MRI slice
- Case list with status and timestamps

Placeholders (replace with real screenshots):

![App Dashboard](docs/images/app_dashboard_placeholder.png)
![Prediction + Heatmap](docs/images/heatmap_placeholder.png)
![Case List](docs/images/case_list_placeholder.png)

---

## ⚙️ Setup & Run

1) Create environment
- python -m venv .venv && source .venv/bin/activate  # Windows: .venv\\Scripts\\activate
- pip install -r requirements.txt

2) Configure environment
- Copy .env.example to .env and set keys (IBM COS, DB2 if used)

3) Run locally
- flask --app app run --debug

4) Docker
- docker build -t heart-mri-ai .
- docker run -p 8080:8080 heart-mri-ai

5) IBM Cloud (example)
- ibmcloud login
- ibmcloud target --cf
- ibmcloud cf push heart-mri-ai

---

## 🧭 Repository Structure
- app/
  - routes.py, services/, models/, utils/
- models/
  - saved_model/, versioning.json
- static/ | templates/
- docs/images/
- tests/
- requirements.txt | Dockerfile | .env.example

---

## 👩‍⚕️ Usage
- Upload an MRI image or series
- Click Analyze to run inference and generate heatmaps
- Review predictions, download overlays, and export JSON

> Important: This is a research/educational tool, not a diagnostic device.

---

## 👩‍💻 Authors & Contributors
- Lead ML Engineer — Your Name (LinkedIn)
- Backend & DevOps — Your Name (LinkedIn)
- Clinical Advisor — Your Name, MD (LinkedIn)

Replace with your team and links:
- Jane Doe — linkedin.com/in/janedoe
- John Smith — linkedin.com/in/johnsmith

---

## 🙏 Acknowledgments
- IBM Skills Network & Mentors for guidance and cloud credits
- Open-source community: TensorFlow, Flask, OpenCV
- Public medical imaging datasets used for prototyping

---

<div align="center">
  <sub>Made with ❤️ for healthcare innovation</sub>

  <br/>
  <img alt="IBM" src="https://img.shields.io/badge/Powered%20by-IBM%20Cloud-052FAD?logo=ibm&logoColor=white" />
</div>
