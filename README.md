Emotion Prediction App
This project implements an Emotion Prediction application using Natural Language Processing (NLP) techniques and a Logistic Regression model. Users can input text, and the application will predict the underlying emotion (e.g., sadness, joy, anger, fear, love, surprise).

Table of Contents
Project Overview
Features
Technologies Used
Installation
Usage
Files
Model Details
Deployment (Streamlit App)
Project Overview
The goal of this project is to classify emotions from textual data. The process involves data loading, extensive text preprocessing (lowercasing, punctuation removal, emoji removal, number removal, stop word removal), training a machine learning model, and deploying it as an interactive web application using Streamlit.

Features
Data Preprocessing: Cleans raw text data by removing noise and normalizing text.
Feature Extraction: Converts text into numerical features using Bag-of-Words (BoW).
Machine Learning Model: Trains a Logistic Regression model for emotion classification.
Model Evaluation: Assesses model performance using accuracy scores.
Streamlit Web Application: Provides an intuitive interface to test the emotion prediction model in real-time.
Technologies Used
Python 3.x
pandas (for data manipulation)
numpy (for numerical operations)
scikit-learn (for machine learning models and utilities)
nltk (for natural language processing tasks like stop words)
joblib (for saving and loading models)
streamlit (for building the web application)
matplotlib & seaborn (for data visualization - though not explicitly in app, used in notebook)
Installation
To run this project locally, follow these steps:

Clone the repository (if hosted on GitHub) or download the project files.
Install the required libraries: It's recommended to use a virtual environment.
pip install pandas numpy scikit-learn nltk joblib streamlit
Download NLTK data: The nltk library requires stopwords and punkt tokenizers. These will be downloaded automatically when running the Streamlit app, but you can also do it manually:
import nltk
nltk.download('stopwords')
nltk.download('punkt')
Usage
Notebook
The Jupyter/Colab notebook (Emotion_Prediction_Project.ipynb) contains all the steps from data loading and preprocessing to model training and evaluation. You can run cells sequentially to reproduce the results and train the model.

Streamlit Application
Ensure model artifacts are present: After running the notebook, make sure the following files are in the same directory as your app.py:

lr_model_bow.pkl
bow_vectorizer.pkl
emotion_mapping.pkl
Run the Streamlit app: Open your terminal or command prompt, navigate to the project directory, and execute:

streamlit run app.py
This will open a new tab in your web browser with the Emotion Prediction App.

Files
train.txt: The raw dataset containing text and corresponding emotions.
Emotion_Prediction_Project.ipynb: The Jupyter/Colab notebook with all the code.
lr_model_bow.pkl: The trained Logistic Regression model.
bow_vectorizer.pkl: The fitted Bag-of-Words vectorizer.
emotion_mapping.pkl: A dictionary mapping numerical labels back to emotion names.
app.py: The Python script for the Streamlit web application.
Model Details
The emotion prediction is performed using a Logistic Regression classifier. Text features are extracted using a Bag-of-Words (BoW) approach, specifically CountVectorizer from scikit-learn. The model was trained on a dataset of text snippets labeled with various emotions.

Deployment (Streamlit App)
The app.py file contains the Streamlit code which loads the pre-trained model and vectorizer, applies the same preprocessing steps to user input, and provides real-time emotion predictions. This allows for easy interaction with the trained model without needing to re-run the entire training pipeline.
