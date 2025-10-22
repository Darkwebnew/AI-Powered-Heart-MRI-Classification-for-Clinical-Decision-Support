<div align="center">

# 🫀 AI‑Powered Heart MRI Classification

[![Python](https://img.shields.io/badge/Python-3.9+-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-2.x-000000?logo=flask&logoColor=white)](https://flask.palletsprojects.com/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00?logo=tensorflow&logoColor=white)](https://www.tensorflow.org/)
[![IBM Cloud](https://img.shields.io/badge/IBM%20Cloud-Services-052FAD?logo=ibmcloud&logoColor=white)](https://www.ibm.com/cloud)


### 💎 Project Status: <img alt="Selected" src="https://img.shields.io/badge/Selected-IBM%20Finalist-052FAD?logo=ibm&logoColor=white"/>

</div>

> Revolutionizing cardiac decision support with AI-driven MRI classification, explainable heatmaps, and cloud-native deployment. Built with Flask + TensorFlow, integrated with IBM Cloud services and watsonx for robust, scalable clinical insights.

---

## 🚀 Overview
This project delivers a clinician-friendly web app that classifies heart MRI sequences and surfaces explainable insights via XAI heatmaps. It streamlines the workflow from DICOM/PNG upload to inference, visualization, and report generation—aiming to augment, not replace, clinical decision-making.

- Fast, accurate MRI classification with deep learning
- Explainability-first design (Grad-CAM/Integrated Gradients overlays)
- Cloud-ready storage, logging, and model lifecycle
- Production web UI using Flask, with dashboard analytics

---

## 📌 Highlights
- ✅ IBM Finalist selection acknowledging innovation and impact
- 🧠 Robust CNN-based classifier with transfer learning
- 🔎 XAI overlays to build clinician trust and traceability
- ☁️ IBM Cloud object storage + Db2 integration for data and metadata
- 🔐 Role-based access, audit-friendly logs, reproducible runs

---

## 🛠️ Technology Stack
- Application: Flask, Jinja2, Bootstrap, Chart.js
- AI/ML: TensorFlow/Keras, OpenCV/NumPy, scikit-image, Grad-CAM
- Data: IBM Cloud Object Storage, IBM Db2 (metadata, results)
- Ops: Docker, GitHub Actions (CI), IBM Cloud/Code Engine compatible

---

## 🧭 Architecture
A color-coded, end-to-end flow from user upload to explainable results and storage.

```mermaid
flowchart LR
  subgraph User[User 👩‍⚕️]
    U1[Upload MRI/DICOM]
    U2[Review Results]
  end

  subgraph Web[Flask App 💻]
    W1[Upload & Preprocess
        - DICOM/PNG/MP4
        - Normalization / Resize]
    W2[Inference API]
    W3[Results Dashboard]
  end

  subgraph Cloud[IBM Cloud ☁️]
    C1[Object Storage
       - Raw + Processed Images]
    C2[Db2
       - Cases, Metrics, Audit]
    C3[watsonx.ai
       - Experiment Tracking]
  end

  subgraph AI[AI Model 🧠]
    M1[TensorFlow CNN]
    M2[XAI Heatmaps
       (Grad-CAM)]
  end

  U1 --> W1 --> W2 --> M1 --> M2 --> W3 --> U2
  W1 --> C1
  W2 --> C2
  M1 -. metrics .-> C3
  W3 --> C2
```

Color legend: User (teal), Flask (indigo), IBM Cloud (blue), AI Model (orange).

---

## 🧪 Demo Images
Showcasing the app’s explainability and UI. Replace placeholders with real outputs from your runs.

- Heatmap overlay on MRI slice
  
  ![Heatmap Overlay](/docs/images/heatmap.png)

- Sample heart MRI frame
  
  ![MRI Example](/docs/images/mri_example.png)

- Web dashboard with predictions and trends
  
  ![Dashboard](/docs/images/dashboard.png)

---

## 🎬 Video Demo
Experience the workflow end-to-end in this short demo.

[▶️ Watch on YouTube](https://youtu.be/JMZrROrt5qQ?si=V046ShjApX__89Iv)

---

## 🧩 Key Features
- Drag-and-drop upload (DICOM/PNG) with on-the-fly preprocessing
- Real-time inference with confidence scores and XAI heatmaps
- Case history, search, and CSV/DB export for audits
- Environment-ready for containerized deployment on IBM Cloud

---

## ⚙️ Setup & Run
1) Clone and install

```bash
git clone https://github.com/Darkwebnew/AI-Powered-Heart-MRI-Classification-for-Clinical-Decision-Support.git
cd AI-Powered-Heart-MRI-Classification-for-Clinical-Decision-Support
pip install -r requirements.txt
```

2) Configure environment (examples in .env.example)

- IBM_COS_BUCKET, IBM_COS_APIKEY, IBM_COS_ENDPOINT
- DB2_DSN / credentials

3) Launch

```bash
python app.py
# or
flask run --host 0.0.0.0 --port 8080
```

---

## 👩‍⚕️ Usage
- Upload MRI/DICOM -> view prediction + XAI heatmap
- Save case: metadata stored in Db2; images to Object Storage
- Monitor dashboard: cohort stats, model confidence distribution

---

## 🧭 Repository Structure
```
.
├── app.py
├── models/
├── notebooks/
├── static/ | templates/
├── docs/
│   └── images/
│       ├── heatmap.png
│       ├── mri_example.png
│       └── dashboard.png
└── README.md
```

---

## 👩‍💻 Authors & Contributors
- SRIRAM V — [GitHub profile](https://github.com/)
- SHIVRAJ R G — [GitHub profile](https://github.com/)
- M MADHURI G — [GitHub profile](https://github.com/)
- DARSHANI — [GitHub profile](https://github.com/)

If you share GitHub usernames, we’ll update these links to point directly to your profiles.

---

## 🙏 Acknowledgments
- IBM Cloud and the IBM Academic/Startup programs for credits, tooling, and guidance
- Open-source community: TensorFlow, Flask, and visualization libraries

---

## 📜 License
This project is intended for research and educational use. For clinical deployment, ensure regulatory compliance and validation.
