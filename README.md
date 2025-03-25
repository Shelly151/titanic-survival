# 🚢 Titanic Survival Predictor: Containerized Streamlit App

## 📌 Overview
The **Titanic Survival Prediction Model** is a machine learning web application that predicts whether a passenger would have survived the Titanic disaster based on various input features.

🔹 **Tech Stack:** Python, scikit-learn, pandas, Streamlit  
🔹 **Deployment:** Docker containerized for seamless portability  

## 📂 Project Structure
```
Titanic-Prediction-Model/
│── Dockerfile                # Configuration for containerization
│── requirements.txt          # Dependencies for the application
│── main.py                   # Streamlit-based web application
│── titanic_model.py          # Model training script
│── titanic_model.pkl         # Serialized trained model
```

## 🛠️ Model Training (titanic_model.py)
The model is trained using a **Random Forest Classifier** from scikit-learn, based on the Titanic dataset features. The trained model is saved as `titanic_model.pkl` using joblib for efficient storage and loading.

### 📌 Steps in `titanic_model.py`:
1️⃣ Load and preprocess the Titanic dataset  
2️⃣ Handle missing values and encode categorical data  
3️⃣ Train the **Random Forest Model**  
4️⃣ Save the trained model as `titanic_model.pkl`  

## 🎨 Streamlit Web Application (main.py)
The **Streamlit app** provides an intuitive and interactive interface for users to input passenger details and predict survival chances.

✨ **Key Features:**
✔️ User-friendly UI with enhanced CSS  
✔️ Live predictions using the trained `.pkl` model  
✔️ Interactive sliders & dropdowns for easy input selection  

## 🐳 Docker Setup
To ensure seamless deployment, the application is containerized using **Docker**.

### 📄 `Dockerfile`
```dockerfile
# Use Python 3.12 slim as base image
FROM python:3.12-slim

# Set working directory
WORKDIR /app

# Copy necessary files
COPY requirements.txt requirements.txt
COPY main.py main.py
COPY titanic_model.pkl titanic_model.pkl

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Expose the application port
EXPOSE 8501

# Run the Streamlit app
CMD ["streamlit", "run", "main.py", "--server.port=8501", "--server.address=0.0.0.0"]
```

## 🚀 Running the Application with Docker

### 1️⃣ Navigate to the Project Directory
```sh
cd Titanic-Prediction-Model
```

### 2️⃣ Build the Docker Image
```sh
docker build -t titanic-prediction .
```

### 3️⃣ Run the Docker Container
```sh
docker run -p 8501:8501 titanic-prediction
```

### 4️⃣ Access the Application
Open your browser and navigate to:  
🔗 **[http://localhost:8501](http://localhost:8501)**

---
**📢 Ready to Predict?** 🚀 Start exploring survival probabilities now! Happy coding! 🎉

![Streamlit App Screenshot](https://github.com/vidhi-jaju/DockSpace/blob/503edea0a8d31ac50889f767b41cfc13cfd07b51/3.Titanic%20Survival%20Predictor%20Containerized%20Streamlit%20App/img2.png)


