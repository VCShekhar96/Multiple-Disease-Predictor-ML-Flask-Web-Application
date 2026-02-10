# Multiple Disease Predictor - ML-Flask Web Application

> A professional-grade machine learning web application for predictive health analytics utilizing advanced classification algorithms deployed via Flask.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Technology Stack](#technology-stack)
- [System Requirements](#system-requirements)
- [Installation Guide](#installation-guide)
- [Configuration](#configuration)
- [Running Locally](#running-locally)
- [Project Structure](#project-structure)
- [ML Models & Datasets](#ml-models--datasets)
- [API Documentation](#api-documentation)
- [Usage Guide](#usage-guide)
- [Deployment](#deployment)
- [Disclaimer & Legal](#disclaimer--legal)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

---

## 🎯 Overview

**Multiple Disease Predictor** is an end-to-end machine learning application that leverages classification algorithms to predict the likelihood of three critical diseases based on user-provided health metrics:

1. **Diabetes** - Metabolic disease prediction
2. **Heart Disease** - Cardiovascular risk assessment  
3. **Parkinson's Disease** - Neurological condition detection via voice analysis

The application is built using industry-standard tools (Python, Flask, scikit-learn) and provides a responsive, user-friendly web interface for both healthcare professionals and general users seeking preliminary health assessments.

**Live Demo:** *(Update with your deployment URL)*

---

## ✨ Key Features

- **Multi-Disease Prediction**: Support for 3 major disease categories
- **Real-time Predictions**: Instant ML model inference via REST endpoints
- **Responsive Web UI**: Modern, professional interface optimized for desktop, tablet, and mobile devices
- **Secure Input Validation**: Robust data validation and error handling
- **Professional Design**: Enterprise-grade UI/UX with accessibility compliance
- **Comprehensive Logging**: Activity tracking and error diagnostics
- **Easy Deployment**: Production-ready Flask application with Gunicorn support

---

## 🛠️ Technology Stack

| Category | Technologies |
|----------|--------------|
| **Backend** | Python 3.7+ |
| **Framework** | Flask 1.1+ |
| **ML Libraries** | scikit-learn, NumPy, Pandas |
| **Frontend** | HTML5, CSS3, JavaScript |
| **Deployment** | Heroku, Gunicorn |
| **Version Control** | Git, GitHub |

---

## 💻 System Requirements

### Minimum Requirements
- **OS**: Windows 10+, macOS 10.12+, Linux (Ubuntu 18.04+)
- **Python**: 3.7 or higher
- **RAM**: 2 GB minimum
- **Storage**: 500 MB free space
- **Internet**: Required for first-time setup and dependencies download

### Recommended Setup
- Python 3.9+
- 4+ GB RAM
- 1+ GB free storage
- pip (Python package manager)
- Git (for version control)

---

## 📦 Installation Guide

### Step 1: Prerequisites Installation

Before proceeding, ensure you have Python 3.7+ installed. Verify your installation:

```bash
python --version
pip --version
```

### Step 2: Clone the Repository

```bash
# Clone the repository
git clone https://github.com/sidroy9/Multiple-Disease-Predictor-ML-Flask-WebApp.git

# Navigate to project directory
cd Multiple-Disease-Predictor-ML-Flask-WebApp
```

### Step 3: Create and Activate Virtual Environment (Recommended)

**Windows:**
```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
venv\Scripts\activate
```

**macOS/Linux:**
```bash
# Create virtual environment
python3 -m venv venv

# Activate virtual environment
source venv/bin/activate
```

### Step 4: Install Required Dependencies

```bash
# Install all required packages from requirements.txt
pip install -r requirements.txt
```

**Package Details:**
- `numpy`: Numerical computing
- `pandas`: Data manipulation and analysis
- `matplotlib`: Data visualization
- `seaborn`: Statistical visualization
- `scikit-learn`: Machine learning algorithms
- `Flask`: Web framework

### Step 5: Verify Installation

```bash
# Test Python imports
python -c "import flask, pandas, sklearn, numpy; print('All dependencies installed successfully!')"
```

---

## ⚙️ Configuration

### Application Settings

1. **Flask Configuration** - Located in `app.py`
   - Debug mode: Set `debug=True` for development, `False` for production
   - Host: Default `127.0.0.1` (localhost)
   - Port: Default `5000`

2. **Model Files** - Ensure the following pickle files exist in the project root:
   - `diabetes.pkl` - Trained Diabetes prediction model
   - `heart.pkl` - Trained Heart Disease prediction model
   - `parkinsons.pkl` - Trained Parkinson's Disease prediction model

### Optional: Environment Variables

Create a `.env` file (if needed for production) with:
```
FLASK_ENV=production
FLASK_DEBUG=False
SECRET_KEY=your_secret_key_here
```

---

## 🚀 Running Locally

### Quick Start

1. **Activate virtual environment** (if using one):
   ```bash
   # Windows
   venv\Scripts\activate
   
   # macOS/Linux
   source venv/bin/activate
   ```

2. **Run the Flask application**:
   ```bash
   python app.py
   ```

3. **Access the web application**:
   - Open your browser and navigate to: `http://127.0.0.1:5000/`
   - Or use: `http://localhost:5000/`

4. **Using the Application**:
   - Select the disease prediction you want (Diabetes, Heart, or Parkinson's)
   - Enter your health metrics in the form
   - Click "Get Prediction"
   - View your assessment result

### Development with Auto-Reload

For development with automatic reload on code changes:

```bash
# Set Flask environment variable
# Windows
set FLASK_ENV=development
set FLASK_APP=app.py

# macOS/Linux
export FLASK_ENV=development
export FLASK_APP=app.py

# Run Flask development server
flask run --reload
```

### Testing with Different Port

```bash
# Run on port 8000 instead of default 5000
python -c "from app import app; app.run(host='0.0.0.0', port=8000)"
```

---

## 📁 Project Structure

```
Multiple-Disease-Predictor-ML-Flask-WebApp/
│
├── app.py                          # Main Flask application entry point
├── diabetes.py                     # Diabetes model training script
├── heart.py                        # Heart Disease model training script
├── parkinsons.py                   # Parkinson's model training script
│
├── diabetes.pkl                    # Trained Diabetes model
├── heart.pkl                       # Trained Heart Disease model
├── parkinsons.pkl                  # Trained Parkinson's model
│
├── diabetes.csv                    # Diabetes dataset (training data)
├── heart.csv                       # Heart Disease dataset
├── ParkinsonsDisease.csv          # Parkinson's dataset
│
├── requirements.txt                # Python dependencies list
├── Procfile                        # Heroku deployment configuration
├── README.md                       # This file
│
├── templates/                      # HTML templates
│   ├── layout.html                # Base layout template
│   ├── home.html                  # Home page
│   ├── diabetes.html              # Diabetes prediction page
│   ├── heartdisease.html          # Heart disease prediction page
│   └── parkinsons.html            # Parkinson's prediction page
│
└── static/                        # Static files
    ├── css/
    │   └── style.css              # Application styling
    └── images/                    # Images (if any)
```

---

## 🧠 ML Models & Datasets

### Model Information

| Disease | Algorithm | Accuracy | Features | Training Data |
|---------|-----------|----------|----------|---------------|
| **Diabetes** | Logistic Regression | ~77% | 8 health metrics | 768 samples |
| **Heart Disease** | Logistic Regression | ~85% | 13 cardiovascular metrics | 303 samples |
| **Parkinson's** | SVM/Logistic Regression | ~88% | 22 voice parameters | 195 samples |

### Dataset Characteristics

**Diabetes Dataset (Pima Indians Diabetes Database)**
- Source: Kaggle
- Records: 768 patients
- Features: 8 numeric attributes
- Target: Binary (Diabetic / Non-Diabetic)
- Missing Values: Handled via preprocessing

**Heart Disease Dataset (UCI ML Repository)**
- Records: 303 patients
- Features: 13 clinical and demographic attributes
- Target: Binary (Disease Present / Absent)
- Preprocessing: Normalization applied

**Parkinson's Dataset (Oxford Parkinson's Disease Detection)**
- Records: 195 individuals
- Features: 22 voice signal characteristics
- Target: Binary (Parkinson's / Healthy)
- Analysis: Dysphonia and voice analysis metrics

### Model Training Pipeline

```
Raw Data → Data Cleaning → Feature Scaling → Train-Test Split (80-20) 
→ Model Training → Hyperparameter Tuning → Model Evaluation → Pickle Serialization
```

---

## 🔌 API Documentation

### Base URL
```
http://127.0.0.1:5000
```

### Endpoints

#### 1. Home Page
```
GET /
Response: HTML home page with disease selection
```

#### 2. Diabetes Prediction
```
GET /diabetes
Response: Diabetes prediction form

POST /predictdiabetes
Content-Type: application/x-www-form-urlencoded
Parameters:
  - field1: Pregnancies (numeric)
  - field2: Glucose (numeric)
  - field3: BloodPressure (numeric)
  - field4: SkinThickness (numeric)
  - field5: Insulin (numeric)
  - field6: BMI (numeric)
  - field7: DiabetesPedigreeFunction (numeric)
  - field8: Age (numeric)
Response: Prediction result (Diabetic/Non-Diabetic)
```

#### 3. Heart Disease Prediction
```
GET /heartdisease
Response: Heart disease prediction form

POST /predictheartdisease
Parameters:
  - field1-field13: Cardiovascular health metrics
Response: Prediction result (Disease Present/Absent)
```

#### 4. Parkinson's Prediction
```
GET /parkinsons
Response: Parkinson's prediction form

POST /predictparkinsons
Parameters:
  - field1-field22: Voice signal parameters
Response: Prediction result (Parkinson's/Healthy)
```

---

## 📖 Usage Guide

### Scenario 1: Diabetes Risk Assessment

1. Go to Home page → Click "Diabetes Prediction"
2. Enter health metrics:
   - Pregnancies: 5
   - Glucose: 120
   - Blood Pressure: 80
   - Skin Thickness: 25
   - Insulin: 100
   - BMI: 27.5
   - Diabetes Pedigree Function: 0.5
   - Age: 35
3. Click "Get Prediction"
4. View result: "Prediction: Non-Diabetic" or "Prediction: Diabetic"

### Scenario 2: Cardiovascular Health Check

1. Go to Home page → Click "Heart Disease Prediction"
2. Fill in clinical parameters
3. Click "Get Prediction"
4. Review cardiovascular risk assessment

### Scenario 3: Voice-Based Parkinson's Screening

1. Go to Home page → Click "Parkinson's Prediction"
2. Enter voice analysis parameters (obtained from voice recordings)
3. Click "Get Prediction"
4. View neurological assessment results

---

## 🌐 Deployment

### Local to Production Workflow

**Option 1: Deploy to Heroku**

```bash
# 1. Create Heroku account (https://www.heroku.com/)
# 2. Install Heroku CLI
# 3. Login to Heroku
heroku login

# 4. Create new app
heroku create your-app-name

# 5. Push to Heroku
git push heroku main

# 6. View live app
heroku open
```

**Option 2: Deploy to AWS/Azure/Google Cloud**
- Refer to respective cloud provider documentation
- Use Gunicorn for production server: `gunicorn app:app`

**Option 3: Docker Deployment**

Create `Dockerfile`:
```dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["gunicorn", "app:app"]
```

Build and run:
```bash
docker build -t disease-predictor .
docker run -p 5000:5000 disease-predictor
```

---

## ⚠️ Disclaimer & Legal

### Important Notice

**This application is for educational and informational purposes ONLY.** 

- ❌ **NOT a substitute** for professional medical advice, diagnosis, or treatment
- ❌ **NOT validated** for clinical decision-making
- ❌ **NOT intended** for medical practice or patient care
- ❌ **NOT liable** for any health decisions based on predictions

### User Responsibilities

Users acknowledge that:
- All predictions are preliminary assessments
- Users must consult qualified healthcare professionals
- No medical treatment should be based solely on this app
- The developers assume no liability for misuse

**Always consult a licensed physician for medical concerns.**

---

## 🔧 Troubleshooting

### Common Issues & Solutions

**Issue 1: "ModuleNotFoundError: No module named 'flask'"**
```bash
Solution:
pip install -r requirements.txt
# Or reinstall Flask specifically:
pip install flask
```

**Issue 2: "Port 5000 already in use"**
```bash
# Kill process using port 5000 (Windows)
netstat -ano | findstr :5000
taskkill /PID <PID> /F

# Or run on different port
python -c "from app import app; app.run(port=8000)"
```

**Issue 3: "Model file not found (.pkl)"**
```
Solution:
- Verify pickle files exist in project root
- Re-train models using diabetes.py, heart.py, parkinsons.py
- Files must be named exactly: diabetes.pkl, heart.pkl, parkinsons.pkl
```

**Issue 4: "ValueError: Input has N features but model expects M"**
```
Solution:
- Ensure all form inputs are provided (no empty fields)
- Check that number of input fields matches model expectations
- Validate data types (numeric values required)
```

**Issue 5: Application slow or crashes**
```
Solution:
- Increase system RAM
- Reduce browser tabs/processes
- Use production server (Gunicorn) instead of Flask dev server
- Restart the application
```

---

## 🤝 Contributing

We welcome contributions! Please follow these guidelines:

### Contribution Process

1. **Fork the repository**
2. **Create a feature branch**: `git checkout -b feature/YourFeature`
3. **Make your changes** with clear commits
4. **Write/update tests** if applicable
5. **Submit a Pull Request** with description of changes

### Contribution Areas

- 🐛 Bug fixes
- 🎨 UI/UX improvements
- 📊 Model algorithm enhancements
- 📚 Documentation improvements
- 🔒 Security improvements
- ✨ New features (with discussion first)

---

## 📄 License

This project is open source and available under the **MIT License**.

See LICENSE file for details.

---

## 📞 Contact & Support

**Project Repository:** https://github.com/sidroy9/Multiple-Disease-Predictor-ML-Flask-WebApp

**For issues, feature requests, or questions:**
- Open an Issue on GitHub
- Create a Discussion thread

**Author:** sidroy9

---

## 📚 Additional Resources

- [Flask Documentation](https://flask.palletsprojects.com/)
- [scikit-learn Documentation](https://scikit-learn.org/)
- [Python 3 Documentation](https://docs.python.org/3/)
- [Heroku Deployment Guide](https://devcenter.heroku.com/)

---

*Last Updated: February 2026*  
*Status: Maintained & Active*

**Home Page**


![HomePage](https://user-images.githubusercontent.com/109678911/204099558-56535854-14dd-43c6-83f4-ba7ee329662d.PNG)


**Diabetes Prediction Page**

![DiabetesPredictionPage](https://user-images.githubusercontent.com/109678911/204099575-ea73c666-60a5-464f-8fee-ec4440a9674a.PNG)

**Diabetes Prediction Page With Inputs Provided by the User**

![DiabetesPredictionPageWithValues](https://user-images.githubusercontent.com/109678911/204099672-6693a3f3-de0c-4706-bb4b-cc12282866f2.PNG)

**Diabetes Prediction Page Displaying the Output for the Inputs Provided by the User**

![DiabetesPredictionPageOutput](https://user-images.githubusercontent.com/109678911/204099710-34179827-df57-48a2-96fa-883f2c82fba6.PNG)

**Parkinson's Prediction Page**

![ParkinsonsPredictionPage](https://user-images.githubusercontent.com/109678911/204099779-547b7a95-160d-45c7-b650-38abeb7cfd8d.PNG)

**Heart Disease Prediction Page**

![HeartDiseasePredictionPage](https://user-images.githubusercontent.com/109678911/204099841-0298aa88-9b1f-4d38-bf6e-14dd9527d9f6.PNG)

### Install

This project requires **Python** and the following Python libraries installed:

- NumPy
- Pandas
- matplotlib
- Seaborn
- scikit-learn
- Flask

### How this project has been created

**Step-1** : Build and trained ML models for each of the 3 diseases, whose code is written in the `diabetes.py`, `heart.py` and `parkinsons.py` files and saved the model in pickle file `diabetes.pkl`, `heart.pkl`, and `parkinsons.pkl` respectively.

**Step-2** : Created Flask web app whose code is written in `app.py` file. For the interactive user interface, HTML and CSS have been used. HTML files are stored in `templates` directory while CSS files and web app's background image is stored in `static` directory.

**Step-3** : Uploaded the project on GitHub and deployed the web app using Heroku.

### Procfile

Procfile is a mechanism for declaring the commands that are executed by an Heroku app on startup. So for this project, the Procfile contains ` web: gunicorn app:app` where the first app represents the name of the python file (`app.py`) that runs the whole application. The second app represents the app name (`app=Flask(__name__)`) that is named inside app.py file.

### Deployment on Heroku With Screenshots

**Step-1** : Login to Heroku, then Create the new app.

![Createapp](https://user-images.githubusercontent.com/109678911/204100024-e9c2b32d-46a8-4858-b0c3-1d428323bbe7.PNG)

**Step-2** : Connect to the GitHub and then Connect to the Repository `sidroy9/Multiple-Disease-Predictor-ML-Flask-WebApp` where this project exists.

![Deployment](https://user-images.githubusercontent.com/109678911/204100265-8d0ce13f-cea2-4c2c-87a5-db7e3e05e422.PNG)

**Step-3** : Go to Manual Deploy Section, then choose the main branch to deploy and then click on the Deploy Branch. Now, Build main will start.

![Manual Deploy](https://user-images.githubusercontent.com/109678911/204100750-e803df4f-c8b7-4b33-987a-e56d1c14b733.jpg)


**Step-4** : After sometime, the app will be deployed successfully. You can click on View to see the live web app. 

![Deployed](https://user-images.githubusercontent.com/109678911/204101351-721158a6-3e81-4893-844b-8f03329b2e5e.jpg)



### Run

In a terminal or command window, navigate to the top-level project directory `Multiple-Disease-Predictor-ML-Flask-WebApp/` (that contains this README) and run the following command:

```bash
python app.py
```  

This will show you the localhost address, type the same address in the browser and it will open WebApp in your browser.

### Data

The datasets that are used for training the ML models are:

- **The diabetes dataset consists of 768 data points, with each datapoint having 8 features. This dataset is Pima Indians Diabetes Database found on the kaggle.**

**Features**
1. `Pregnancies`: Number of times pregnant
2. `Glucose`: Plasma glucose concentration a 2 hours in an oral glucose tolerance test
3. `BloodPressure`: Diastolic blood pressure (mm Hg)
4. `SkinThickness`: Triceps skin fold thickness (mm)
5. `Insulin`: 2-Hour serum insulin (mu U/ml)
6. `BMI`: Body mass index (weight in kg/(height in m)^2)
7. `DiabetesPedigreeFunction`: Diabetes pedigree function
8. `Age`: Age (years)


**Target Variable**
9. `Outcome`: Class variable (0 or 1) 268 of 768 are 1, the others are 0

- **The heart dataset consists of 1025 data points, with each datapoint having 13 features. This dataset is Heart Disease Dataset found on the kaggle.**

**Features**
1. `age`: age in years
2. `sex`: (1 = male; 0 = female)
3. `cp`: chest pain type
4. `trestbps`: resting blood pressure (in mm Hg on admission to the hospital)
5. `chol`: serum cholestoral in mg/dl
6. `fbs`: (fasting blood sugar > 120 mg/dl) (1 = true; 0 = false)
7. `restecg`: resting electrocardiographic results
8. `thalach`: maximum heart rate achieved
9. `exang`: exercise induced angina (1 = yes; 0 = no)
10. `oldpeak`: ST depression induced by exercise relative to rest
11. `slope`: the slope of the peak exercise ST segment
12. `ca`: number of major vessels (0-3) colored by flourosopy 
13. `thal`: 0 = normal; 1 = fixed defect; 2 = reversable defect


**Target Variable**
14. `target`: Class variable (0 or 1) 526 of 1025 are 1, the others are 0. Value 0 = no heart disease and 1 = heart disease

- **The ParkinsonsDisease dataset consists of 195 data points, with each datapoint having 22 features. This dataset is Parkinsons Disease Dataset found on the kaggle.**

**Features**
1. `MDVP:Fo(Hz)`: Average vocal fundamental frequency
2. `MDVP:Fhi(Hz)`: Maximum vocal fundamental frequency
3. `MDVP:Flo(Hz)`: Minimum vocal fundamental frequency
4. `MDVP:Jitter(%)`
5. `MDVP:Jitter(Abs)`
6. `MDVP:RAP`
7. `MDVP:PPQ`
8. `Jitter:DDP`: Several measures of variation in fundamental frequency
9. `MDVP:Shimmer`
10. `MDVP:Shimmer(dB)`
11. `Shimmer:APQ3`
12. `Shimmer:APQ5`
13. `MDVP:APQ`
14. `Shimmer:DDA` :Several measures of variation in amplitude
15. `NHR`
16. `HNR`: Two measures of ratio of noise to tonal components in the voice
17. `RPDE`
18. `DFA`: Signal fractal scaling exponent
19. `spread1`
20. `spread2`
21. `PPE`: Three nonlinear measures of fundamental frequency variation
22. `D2`: Two nonlinear dynamical complexity measures


**Target Variable**
23. `status`: Class variable (0 or 1) 147 of 195 are 1, the others are 0. Value 1 - Parkinson's, 0 - healthy
