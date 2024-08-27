# Quishing (QR Phising Detection)
## Overview
The QR Code URL Classifier is a Python project that lets you detect QR codes using a webcam and classify the URLs embedded in them. By leveraging machine learning, this tool helps you figure out if a URL might be malicious, so you can take action accordingly. The project is split into two main parts: QR code detection and URL classification.
##Code Breakdown
### 1. Importing Libraries
First things first, we import the necessary libraries for video capture, data handling, visualization, and machine learning.
### 2. Loading the Dataset
Next, we load up a dataset that contains URLs and their labels (malicious, benign, defacement, phishing) into a Pandas DataFrame for processing.
### 3. Feature Engineering
Here, we define several functions to pull out key features from the URLs, like:
Checking for IP addresses
Spotting abnormal URLs
Counting certain components (dots, "www", "@" symbols)
Detecting shortened URLs
Flagging suspicious words (like "login" or "bank")
### 4. Model Training and Analysis
We split the dataset into training and testing sets and try out different classifiers, including Random Forest, LightGBM, and XGBoost.
Model Evaluation: A Jupyter notebook (model_analysis.ipynb) compares the performance of each model to find the best one for classifying URLs.
Optimal Model: The Random Forest classifier turns out to be the best, hitting an accuracy score of 95.7%. (Heads up: We didn’t do much preprocessing or parameter tuning, so there could be some overfitting.) This model is then used in the main app for real-time predictions (quishing_main.ipynb).
### 5. Real-Time QR Code Detection
With OpenCV, the app captures video frames from your webcam, detects QR codes, and classifies the URLs they contain in real time. The results are shown directly on the video feed.
### 6. Evaluation Metrics
We evaluate each model’s performance using classification reports, accuracy scores, F1 scores, and confusion matrices to give a full picture of how well they work.
## Contributing
If you have ideas for improvements or new features, feel free to open an issue or send in a pull request!
Need access to the training .csv dataset? Just shoot me an email at sukalyanchakraborty7@gmail.com.

