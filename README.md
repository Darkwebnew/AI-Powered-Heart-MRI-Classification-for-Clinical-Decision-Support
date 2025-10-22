<div align="center">

# 🫀 AI‑Powered Heart MRI Classification

[![Python](https://img.shields.io/badge/Python-3.9+-3776AB?logo=python&logoColor=white)](https://www.python.org/) [![Flask](https://img.shields.io/badge/Flask-2.x-000000?logo=flask&logoColor=white)](https://flask.palletsprojects.com/) [![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00?logo=tensorflow&logoColor=white)](https://www.tensorflow.org/) [![IBM Cloud](https://img.shields.io/badge/IBM%20Cloud-Services-052FAD?logo=ibmcloud&logoColor=white)](https://www.ibm.com/cloud)

### 💎 **Enterprise AI for Global Cardiac Care: Explainable, Fast, Trusted**

> **🏆 IBM FINALIST** — Recognized for innovation in AI-powered clinical decision support

</div>

---

## 🌟 Why It Matters

**Transforming cardiac diagnostics with cutting-edge AI that delivers real-world clinical impact:**

- ⚡ **Faster Diagnosis** — Reduces MRI interpretation time from hours to seconds, enabling rapid clinical response
- 🔬 **Clinical Trust & Transparency** — Explainable AI (XAI) heatmaps provide visual evidence for every prediction, building physician confidence
- 🎯 **Automated Priority Triage** — Intelligent classification helps prioritize critical cases, optimizing workflow efficiency
- ☁️ **Scalable Cloud Infrastructure** — Built on IBM Cloud with enterprise-grade storage, database, and AI services for global deployment
- 🏅 **IBM Selection** — Validated by IBM as a finalist, demonstrating technical excellence and real-world applicability

---

## 💡 Innovation & WOW Factors

**What makes this project stand out from the crowd:**

### 🔥 **XAI Overlays: See What the AI Sees**
- **Grad-CAM & Integrated Gradients** generate pixel-level heatmaps showing exactly which anatomical regions influenced each prediction
- Transforms "black box" models into **transparent, trustworthy clinical tools**
- Enables radiologists to validate AI reasoning against their own expert analysis

### 🧠 **Proactive Clinical Insights**
- Real-time confidence scoring helps clinicians understand prediction certainty
- Automated flagging of ambiguous cases for human review
- Historical case comparison and cohort analytics reveal patterns across patient populations

### 💬 **Real-Time Watsonx Chatbot Integration**
- Query patient data, model predictions, and medical literature conversationally
- Natural language access to complex diagnostic information
- Reduces cognitive load during high-pressure clinical decision-making

### 🎯 **Breaking the Black Box**
- Every prediction is auditable and explainable
- Full model lineage tracking for regulatory compliance
- Reproducible results with version-controlled models and data pipelines

---

## 🏥 Clinical Use Case

**Empowering Clinicians in Real-World Cardiac Care:**

This application transforms how cardiologists and radiologists approach heart MRI analysis. When a patient's cardiac imaging arrives, the system accepts standard DICOM or PNG files and instantly classifies the MRI sequence (e.g., normal vs. pathological findings). Instead of waiting hours or days for specialist review, the AI provides an immediate preliminary assessment with visual explainability overlays highlighting regions of interest. Clinicians can quickly verify the AI's reasoning, prioritize urgent cases, and make informed treatment decisions faster. The system maintains a complete audit trail in IBM Db2, stores all imaging data securely in IBM Cloud Object Storage, and provides dashboard analytics to monitor diagnostic accuracy trends across the entire patient cohort. By augmenting—not replacing—clinical expertise with transparent AI insights, this tool reduces diagnostic bottlenecks, improves patient outcomes, and scales expert-level analysis to underserved regions globally.

---

## 🚀 Overview

This project delivers a clinician-friendly web app that classifies heart MRI sequences and surfaces explainable insights via XAI heatmaps. It streamlines the workflow from DICOM/PNG upload to inference, visualization, and report generation—aiming to augment, not replace, clinical decision-making.

- **Fast, accurate MRI classification** with deep learning
- **Explainability-first design** (Grad-CAM/Integrated Gradients overlays)
- **Cloud-ready storage**, logging, and model lifecycle
- **Production web UI** using Flask, with dashboard analytics

---

## 🎯 Technical Achievements

> **🎖️ IBM Finalist Selection** — Acknowledged for innovation, scalability, and clinical impact

- ✅ **Robust CNN-based classifier** with transfer learning (ResNet50/VGG16 backbones)
- 🔎 **XAI overlays** to build clinician trust and traceability (Grad-CAM, Integrated Gradients)
- ☁️ **IBM Cloud object storage + Db2 integration** for data and metadata
- 🔐 **Role-based access**, audit-friendly logs, reproducible runs
- 🚀 **Production-ready deployment** with Flask, containerization support

---

## 🛠️ Technology Stack

- **Application:** Flask, Jinja2, Bootstrap, Chart.js
- **AI/ML:** TensorFlow/Keras, OpenCV/NumPy, scikit-image, Grad-CAM
- **Data:** IBM Cloud Object Storage, IBM Db2 (metadata, results)
- **Deployment:** Docker-ready, IBM Cloud deployment options
- **XAI:** Grad-CAM, Integrated Gradients, visualization pipelines

---

## 🏗️ Architecture

```
┌─────────────────┐
│   User Upload   │
│  (DICOM/PNG)    │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Flask Web App  │
│  (UI + API)     │
└────────┬────────┘
         │
         ▼
┌─────────────────┐       ┌──────────────────┐
│  TensorFlow     │◄──────┤  XAI Engine      │
│  CNN Classifier │       │  (Grad-CAM)      │
└────────┬────────┘       └──────────────────┘
         │
         ▼
┌─────────────────────────────────────┐
│         IBM Cloud Services          │
│  ┌─────────────┐   ┌──────────────┐ │
│  │ Object      │   │   Db2        │ │
│  │ Storage     │   │   Database   │ │
│  └─────────────┘   └──────────────┘ │
└─────────────────────────────────────┘
```

---

## ⚙️ Setup & Installation

### Prerequisites
- Python 3.9+
- pip and virtualenv
- IBM Cloud account (for COS and Db2 services)

### Installation Steps

1) **Clone the repository:**
```bash
git clone https://github.com/Darkwebnew/AI-Powered-Heart-MRI-Classification-for-Clinical-Decision-Support.git
cd AI-Powered-Heart-MRI-Classification-for-Clinical-Decision-Support
```

2) **Install dependencies:**
```bash
pip install -r requirements.txt
```

3) **Configure environment** (examples in `.env.example`):
   - `IBM_COS_BUCKET`, `IBM_COS_APIKEY`, `IBM_COS_ENDPOINT`
   - `DB2_DSN` / credentials

4) **Launch the application:**
```bash
python app.py
# or
flask run --host 0.0.0.0 --port 8080
```

---

## 👩‍⚕️ Usage

- **Upload MRI/DICOM** → view prediction + XAI heatmap
- **Save case:** metadata stored in Db2; images to Object Storage
- **Monitor dashboard:** cohort stats, model confidence distribution

---

## 🧭 Repository Structure

```
.
├── app.py                      # Main Flask application
├── models/                     # Trained model files
├── notebooks/                  # Jupyter notebooks for experiments
├── static/ | templates/        # Frontend assets
├── docs/
│   └── images/
│       ├── heatmap.png
│       ├── mri_example.png
│       └── dashboard.png
└── README.md
```

---

## 👩‍💻 Authors & Contributors

- **SRIRAM V** — [GitHub profile](https://github.com/)
- **SHIVRAJ R G** — [GitHub profile](https://github.com/)
- **M MADHURI G** — [GitHub profile](https://github.com/)
- **DARSHANI** — [GitHub profile](https://github.com/)

*If you share GitHub usernames, we'll update these links to point directly to your profiles.*

---

## 🙏 Acknowledgments

- **IBM Cloud** and the IBM Academic/Startup programs for credits, tooling, and guidance
- **Open-source community:** TensorFlow, Flask, and visualization libraries

---

## 📜 License

This project is intended for **research and educational use**. For clinical deployment, ensure regulatory compliance and validation.

---

<div align="center">

**Made with ❤️ for advancing global cardiac care through explainable AI**

</div>
