# Disaster-Response-Pipelines


# Motivation

The purpose of the project is to build a model for an API that classifies disaster messages. Using the web app an emergency worker can input a new message and get classification results in several categories so to have an idea what kind of help is needed: "water", "shelter", "food", etc.

The web app also displays visualizations of the data.

In this project, I analyzed the data provided by Figure Eight containing the messages in three different categories. Goal of the project is to build a model for an API that classifies disaster messages across 36 different categories.

![Screenshoots](disaster-response-project1.png)
![Screenshoots](disaster-response-project2.png)
![Screenshoots](Screenshot 2020-05-12 at 00.31.35.png)

# Install

This project requires Python 3.x and the following Python libraries installed:

NumPy
Pandas
Matplotlib
Json
Plotly
Nltk
Flask
Sklearn
Sqlalchemy
Sys
Re
Pickle
You will also need to have software installed to run and execute an iPython Notebook

# Code and data

process_data.py: This code extracts data from both CSV files: messages.csv (containing message data) and categories.csv (classes of messages) and creates an SQLite database containing a merged and cleaned version of this data.
train_classifier.py: This code takes the SQLite database produced by process_data.py as an input and uses the data contained within it to train and tune a ML model for categorizing messages. The output is a pickle file containing the fitted model. Test evaluation metrics are also printed as part of the training process.
ETL Pipeline Preparation.ipynb: The code and analysis contained in this Jupyter notebook was used in the development of process_data.py. process_data.py automates this notebook.
ML Pipeline Preparation.ipynb: The code and analysis contained in this Jupyter notebook was used in the development of train_classifier.py. In particular, it contains the analysis used to tune the ML model and determine which model to use. train_classifier.py automates the model fitting process contained in this notebook.
disaster_messages.csv, disaster_categories.csv contain sample messages (real messages that were sent during disaster events) and categories datasets in csv format.
templates folder: This folder contains all of the files necessary to run and render the web app.


# In a terminal navigate to the top-level project directory udacity-disaster-response/ (that contains this README) and run commands in the following sequence:

* python process_data.py disaster_messages.csv disaster_categories.csv DisasterResponse.db
* python train_classifier.py DisasterResponse.db classifier.pkl
* python run.py
* Run the web application Go to http://0.0.0.0:3001/ (if facing problems try http://localhost:3001 in a browser)

In the web app you may input any text message (English) and it will categorize it among 35 classes.

# Data observations

As can be seen from test data visualization most of the classes (categories) are highly imbalanced. This affects model F1 prediction score. One using this project should take this into consideration and apply measures like synthetic data generation, model selection and parameters fine-tuning, etc.

# License

This app was completed as part of the Udacity Data Scientist Nanodegree. Code templates and data were provided by Udacity. The data was originally sourced by Udacity from Figure Eight.
