# AI-Powered Heart MRI Classification

*An educational project demonstrating deep learning for medical image classification*

---

## 📖 Project Overview

This project uses artificial intelligence to analyze heart MRI scans and classify them into different cardiac conditions. It's designed as a learning resource to understand how deep learning can be applied to medical imaging.

**What it does:** The system takes an MRI image of a heart, processes it through a trained neural network model, and predicts the cardiac condition. It also provides visual explanations showing which parts of the image influenced the prediction.

**Purpose:** This is an educational/demonstration project for students and developers learning about:
- Medical image classification
- Deep learning with Python
- Web application development
- Building end-to-end AI projects

---

## ✨ Key Features

- **Image Upload**: Upload heart MRI images for analysis
- **AI Classification**: Automatic prediction of cardiac conditions
- **Explainable AI**: Visual heatmaps showing what the model "sees"
- **Patient Management**: Simple database to track patient records
- **Web Interface**: User-friendly interface built with Flask
- **Real-time Results**: Get predictions in seconds

---

## 🛠️ Tech Stack

### Core Technologies
- **Python 3.8+**: Main programming language
- **TensorFlow/Keras**: Deep learning framework for building the CNN model
- **Flask**: Web framework for the application
- **IBM Db2**: Database for storing patient data and results
- **IBM Cloud Object Storage**: Storing MRI images

### Libraries Used
- **NumPy & Pandas**: Data manipulation
- **OpenCV**: Image processing
- **Matplotlib**: Visualization
- **Pillow**: Image handling
- **scikit-learn**: Model evaluation metrics

---

## 📊 Project Workflow

```
┌─────────────────┐
│  Upload MRI     │
│     Image       │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Preprocessing  │
│  (Resize,       │
│   Normalize)    │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│   CNN Model     │
│  (Prediction)   │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│  Generate XAI   │
│   Heatmap       │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Display Results │
│  + Confidence   │
└─────────────────┘
```

---

## 🚀 Setup Instructions

### Prerequisites
- Python 3.8 or higher
- pip (Python package manager)
- Git

### Installation Steps

1. **Clone the repository**
```bash
git clone https://github.com/Darkwebnew/AI-Powered-Heart-MRI-Classification-for-Clinical-Decision-Support.git
cd AI-Powered-Heart-MRI-Classification-for-Clinical-Decision-Support
```

2. **Create a virtual environment**
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Mac/Linux
python3 -m venv venv
source venv/bin/activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Set up environment variables**
```bash
cp .env.example .env
# Edit .env file with your database credentials (if using cloud services)
```

5. **Initialize the database**
```bash
python config/init_db.py
```

6. **Run the application**
```bash
python app.py
# Or for development mode:
flask run --debug
```

7. **Access the app**
Open your browser and go to: `http://localhost:5000`

---

## 📁 Project Structure & File Descriptions

```
├── app.py                  # Main Flask application (runs the web server)
├── train_and_test.py       # Script to train the CNN model and test it
├── model/
│   ├── cnn_model.h5        # Saved trained model
│   └── model_architecture.py  # Defines the CNN architecture
├── config/
│   ├── init_db.py          # Database initialization script
│   └── db_config.py        # Database connection settings
├── templates/
│   ├── index.html          # Home page
│   ├── upload.html         # Image upload page
│   └── results.html        # Prediction results page
├── static/
│   ├── css/                # Stylesheets
│   ├── js/                 # JavaScript files
│   └── images/             # Static images
├── utils/
│   ├── preprocessing.py    # Image preprocessing functions
│   └── xai.py              # Explainable AI visualization
├── data/
│   └── sample_mri/         # Sample MRI images for testing
└── requirements.txt        # Python dependencies
```

### Key Files Explained

- **app.py**: The main entry point. Handles web routes, file uploads, and calls the model for predictions.
  
- **train_and_test.py**: Use this to train your own model on a dataset of MRI images. It also evaluates the model's accuracy.

- **model/cnn_model.h5**: The pre-trained model file. This is loaded by app.py to make predictions.

- **utils/preprocessing.py**: Contains functions to resize, normalize, and prepare images before feeding them to the model.

- **utils/xai.py**: Generates Grad-CAM heatmaps to visualize which parts of the image the model focuses on.

---

## 💻 How to Use

1. **Start the application** using `python app.py`
2. **Open the web interface** at `http://localhost:5000`
3. **Upload an MRI image** (JPEG or PNG format)
4. **Enter patient information** (optional, for demo purposes)
5. **Click "Analyze"** to get the prediction
6. **View results**: 
   - Predicted condition
   - Confidence score
   - Heatmap showing important regions

### Example Output

```
Prediction: Myocardial Infarction
Confidence: 94.5%

[Visual heatmap overlay on MRI image]

Key Regions Detected:
- Left ventricle wall abnormality
- Reduced blood flow indicators
```

---

## 🎓 Learning Resources

### Understanding the Code

1. **CNN Basics**: The model uses a Convolutional Neural Network (CNN) with multiple layers:
   - Convolutional layers extract features from images
   - Pooling layers reduce image dimensions
   - Dense layers make the final classification

2. **Training Process**: 
   - Data is split into training (80%) and testing (20%)
   - Model learns patterns over multiple epochs
   - Accuracy and loss are tracked to prevent overfitting

3. **Explainable AI**: 
   - Grad-CAM highlights important image regions
   - Helps understand "why" the model made a prediction
   - Builds trust in AI decisions

### Suggested Modifications for Learning

- Try different CNN architectures (ResNet, VGG, etc.)
- Experiment with data augmentation techniques
- Add more cardiac conditions to classify
- Implement different visualization techniques
- Build a mobile app interface

---

## 📊 Sample Data

The `data/sample_mri/` folder contains example MRI images for testing. These are anonymized, publicly available medical images used for educational purposes.

**Note**: This project uses synthetic/demo data and is NOT intended for actual clinical diagnosis.

---

## 🧪 Running Tests

To test the model's performance:

```bash
python train_and_test.py --mode test
```

This will output metrics like:
- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix

---

## ⚠️ Important Disclaimers

- **Educational Use Only**: This project is for learning and demonstration purposes.
- **Not for Clinical Use**: Do NOT use this for actual medical diagnosis.
- **Data Privacy**: Always handle medical data responsibly and follow regulations.
- **Model Limitations**: AI predictions can be wrong; always verify with medical professionals.

---

## 🤝 Contributing

This is an educational project. Feel free to:
- Fork and experiment
- Submit improvements via pull requests
- Report issues or bugs
- Suggest new features

---

## 📄 License

This project is open source and available for educational purposes. Please check the LICENSE file for details.

---

## 🙋 Questions or Issues?

If you encounter any problems while setting up or running the project, please open an issue on GitHub with:
- Your Python version
- Error messages (if any)
- Steps you've already tried

---

*Built as a learning project to explore the intersection of AI and healthcare. Great for students, bootcamp participants, and anyone interested in medical AI applications.*
