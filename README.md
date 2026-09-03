# 🏥 AI MedLab – AI-Powered Healthcare Management System


AI MedLab is an AI-powered healthcare management system that predicts possible diseases from patient symptoms and provides role-based healthcare workflows for **Patients, Doctors, and Nurses**.

The system combines **Machine Learning, Flask REST APIs, HTML/CSS/JavaScript, healthcare recommendation datasets, patient history management, and automated PDF health reports** into one integrated application.

> ⚠️ **Disclaimer:** This project is intended for educational and demonstration purposes. Disease predictions and recommendations should not be treated as a substitute for professional medical diagnosis or treatment.

---

## 🚀 Key Features

### 🤖 AI Disease Prediction

- Predicts a possible disease based on selected symptoms.
- Uses a trained **XGBoost Machine Learning model**.
- Supports patient age and gender information.
- Stores prediction results in patient history.
- Uses encoded healthcare datasets for prediction.

### 👤 Patient Management

Patients can:

- Register and log in.
- Enter age and gender.
- Select multiple symptoms.
- Generate disease predictions.
- View prediction history.
- View health recommendations.
- View doctor health tips.
- View nurse reports.
- Download comprehensive health reports as PDF.

### 👨‍⚕️ Doctor Dashboard

Doctors can:

- View registered patients.
- View patient information and prediction history.
- View patient gender and demographics.
- Add health tips for patients.
- Automatically generate health recommendations based on predicted disease.
- Add doctor name and appointment information.
- Provide personalized healthcare guidance.

### 👩‍⚕️ Nurse Dashboard

Nurses can:

- View tracked patients.
- View patient prediction history.
- View patient gender information.
- Generate comprehensive nurse reports.
- Automatically generate reports using disease-specific healthcare data.
- Add observations and vital information.
- Customize automatically generated reports.
- Add nurse name for report attribution.
- Remove patients from the tracking list.
- Download patient health reports as PDF.

### 📄 Automated PDF Health Reports

The system provides professional PDF health reports containing:

- Patient information
- Age
- Gender
- Predicted disease
- Symptoms
- Health recommendations
- Doctor information
- Nurse information
- Appointment details
- Nurse observations
- Prediction timestamp

Generated reports use the format:

```text

health_report_<email>_<timestamp>.pdf


🧠 Machine Learning

The application uses a trained XGBoost classifier for disease prediction.

ML Components
Backend/model/
│
├── disease_prediction_model_xgb.pkl
├── gender_mapping.pkl
├── label_encoder.pkl
├── healthcare_dataset_onehot.csv
├── healthcare_dataset_processed.csv
│
├── train_model.py
├── retrain_model.py
├── quick_retrain.py
├── preprocess_data.py
├── check_dataset.py
└── test_current_model.py

#Prediction WorkFlow

Patient
   │
   ▼
Select Symptoms
   │
   ▼
Age + Gender + Symptoms
   │
   ▼
Feature Preprocessing
   │
   ▼
XGBoost Model
   │
   ▼
Disease Prediction
   │
   ▼
Patient History

💊 Healthcare Recommendation System
The project contains disease-specific healthcare recommendation datasets.

Backend/HealthPredict/
│
├── description.csv
├── medications.csv
├── diets.csv
├── precautions_df.csv
└── workout_df.csv

🏗️ System Architecture

                    ┌──────────────────────┐
                    │       Patient        │
                    │  Symptoms + Details  │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Frontend UI        │
                    │ HTML / CSS / JS      │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Flask REST API     │
                    │      Backend         │
                    └──────────┬───────────┘
                               │
                ┌──────────────┴──────────────┐
                │                             │
                ▼                             ▼
       ┌─────────────────┐          ┌────────────────────┐
       │ XGBoost Model   │          │ Health Recommendation│
       │ Disease         │          │ CSV Datasets         │
       │ Prediction      │          └────────────────────┘
       └────────┬────────┘
                │
                ▼
       ┌─────────────────────┐
       │ Patient History     │
       │ JSON Storage        │
       └──────────┬──────────┘
                  │
        ┌─────────┼─────────┐
        ▼         ▼         ▼
     Patient    Doctor     Nurse
        │         │         │
        └─────────┼─────────┘
                  │
                  ▼
       ┌─────────────────────┐
       │ Comprehensive PDF   │
       │ Health Report       │
       └─────────────────────┘


🛠️ Technology Stack
Frontend
HTML5
CSS3
JavaScript
Fetch API
Responsive dashboard interface
Backend
Python
Flask
Flask-CORS
REST APIs
Machine Learning
XGBoost
Scikit-learn
Pandas
NumPy
Joblib
Data Storage

The current project uses:

JSON files for user information
JSON files for patient history
CSV files for healthcare recommendations
Pickle files for trained ML models

MongoDB support is included as a dependency for potential future database migration.

PDF Generation
ReportLab

📁 Project Structure

AI_MedLab/
│
├── Backend/
│   ├── app.py
│   │
│   ├── config/
│   │   └── db.py
│   │
│   ├── model/
│   │   ├── disease_prediction_model_xgb.pkl
│   │   ├── gender_mapping.pkl
│   │   ├── label_encoder.pkl
│   │   ├── healthcare_dataset_onehot.csv
│   │   ├── healthcare_dataset_processed.csv
│   │   ├── train_model.py
│   │   ├── retrain_model.py
│   │   ├── quick_retrain.py
│   │   ├── preprocess_data.py
│   │   └── test_current_model.py
│   │
│   ├── HealthPredict/
│   │   ├── description.csv
│   │   ├── medications.csv
│   │   ├── diets.csv
│   │   ├── precautions_df.csv
│   │   └── workout_df.csv
│   │
│   ├── routes/
│   │   ├── auth.py
│   │   └── predict.py
│   │
│   ├── utils/
│   │   ├── __init__.py
│   │   ├── health_recommendations.py
│   │   └── pdf_generator.py
│   │
│   ├── reports/
│   │   └── Generated PDF reports
│   │
│   ├── users.json
│   ├── patient_history.json
│   ├── test.py
│   ├── test_api.py
│   ├── test_model_predictions.py
│   └── test_health_recommendations.py
│
├── frontend/
│   ├── index.html
│   ├── dashboard.html
│   ├── script.js
│   ├── style.css
│   ├── favicon.svg
│   └── test_auto_generate.html
│
├── ARCHITECTURE_AND_API.md
├── Code_Implementation_and_Evaluation.md
├── DEPLOYMENT_GUIDE.md
├── IMPLEMENTATION_SUMMARY.md
├── NURSE_WORKFLOW_GUIDE.md
├── README_NURSE_FEATURE.md
├── SETUP_CHECKLIST.md
├── TROUBLESHOOTING_AND_FAQ.md
├── VISUAL_WORKFLOW_GUIDE.md
├── project_diagrams.md
├── requirement.txt
├── requirements.txt
├── setup_windows.bat
└── setup_macos_linux.sh

⚙️ Installation

1. Clone the Repository
git clone <YOUR_GITHUB_REPOSITORY_URL>

Then

cd AI_MedLab

2. Create a Virtual Environment
Windows
python -m venv venv
.\venv\Scripts\Activate.ps1
macOS/Linux
python3 -m venv venv
source venv/bin/activate
3. Install Dependencies
pip install -r requirements.txt
▶️ Run the Application
Start the Backend

Open a terminal and run:

cd Backend
python app.py

The backend will run on:

http://127.0.0.1:5000
Start the Frontend

Open another terminal:

cd frontend
python -m http.server 8000

Open the application in your browser:

http://localhost:8000
🔌 API Endpoints
Authentication
POST /register
POST /login
Disease Prediction
GET  /symptoms
POST /predict
GET  /available_diseases
Patient History
GET    /patient_history/<email>
DELETE /patient_history/<email>/record
DELETE /patient_history/<email>/clear
Doctor Features
GET  /doctor/patients
POST /doctor/add_health_tips
Nurse Features
GET  /nurse/patients
POST /nurse/generate_report
DELETE /remove_patient/<email>
Healthcare Recommendations
GET /health_recommendations/<disease>
GET /health_recommendations/formatted/<disease>
PDF Reports
POST /generate_pdf_report/<email>
Backend Information
GET /api/info
🧪 Testing

The project includes testing scripts for the API, ML model, prediction functionality, and healthcare recommendations.

Examples:

cd Backend
python test_api.py
python test_model_predictions.py
python test_health_recommendations.py
🔄 Application Workflow
Registration
     │
     ▼
   Login
     │
     ├───────────────┬────────────────┐
     ▼               ▼                ▼
  Patient          Doctor           Nurse
     │               │                │
     ▼               ▼                ▼
Symptoms          Patients         Patients
     │               │                │
     ▼               ▼                ▼
AI Prediction    Health Tips      Patient Reports
     │               │                │
     └───────────────┴────────────────┘
                     │
                     ▼
              Patient History
                     │
                     ▼
              PDF Health Report
🔐 Security

The current project is intended for demonstration and educational use.

It includes:

Password hashing
User authentication
Role-based workflows
Patient history management
CORS configuration

For production deployment, additional security measures should be implemented, including HTTPS, JWT authentication, secure environment variables, database security, stronger access controls, and audit logging.

🚀 Future Enhancements
MongoDB production database
JWT-based authentication
Cloud deployment
Online appointment scheduling
Email/SMS notifications
Patient-doctor messaging
Advanced patient analytics
Health data visualization
Explainable AI predictions
Mobile application
Docker deployment
Secure cloud-based medical records
📚 Documentation

Additional project documentation is available in the repository:

ARCHITECTURE_AND_API.md
Code_Implementation_and_Evaluation.md
DEPLOYMENT_GUIDE.md
IMPLEMENTATION_SUMMARY.md
NURSE_WORKFLOW_GUIDE.md
README_NURSE_FEATURE.md
SETUP_CHECKLIST.md
TROUBLESHOOTING_AND_FAQ.md
VISUAL_WORKFLOW_GUIDE.md
project_diagrams.md
⚠️ Disclaimer

AI MedLab is an educational and demonstration project.

The disease predictions, medications, diet suggestions, precautions, and workout recommendations provided by this application should not be used as a replacement for professional medical advice, diagnosis, or treatment.

Always consult a qualified healthcare professional for medical decisions.

⭐ Project Highlights

AI/ML: XGBoost Disease Prediction

Backend: Python + Flask REST API

Frontend: HTML + CSS + JavaScript

Healthcare: Patient, Doctor & Nurse Workflows

Reports: Automated PDF Health Reports

Data: Healthcare Recommendation Datasets

Storage: JSON-based application storage


### After pasting

Save the file with:

**`Ctrl + S`**

Then in your terminal, run:

```powershell
git add README.md
git commit -m "Add professional project README"
git push origin master


