# sms_spam_detector
Module 21 Challenge 

This project is an SMS spam detection application that uses a machine learning model to classify text messages as "spam" or "not spam" (ham). The application is built using Python, scikit-learn for machine learning, and Gradio for creating a user-friendly interface.

## Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Usage](#usage)
- [Code Explanation](#code-explanation)
- [Testing](#testing)
- [License](#license)

## Overview

The project involves refactoring an existing SMS text classification solution to encapsulate the model creation and training process in a function. The model uses TF-IDF vectorization and a Linear Support Vector Classification (SVC) algorithm. A Gradio app is then created to allow users to input SMS messages and receive predictions on whether the messages are spam.

## Installation

To run this project, you need to have Python installed along with the following packages:

- pandas
- scikit-learn
- gradio

You can install these packages using pip:

```bash
pip install pandas scikit-learn gradio
```

## Usage

1. **Load the Dataset**: Ensure that the SMS spam dataset (`SMSSpamCollection.csv`) is in the `Resources` directory.
2. **Run the Application**: Execute the Python script to start the Gradio app.
3. **Interact with the App**: Enter SMS text messages in the Gradio interface to check if they are spam or not.

## Code Explanation

### Initial Solution

The initial solution involved loading the SMS dataset, preprocessing the data, and building a pipeline with TF-IDF vectorization and Linear SVC for classification. The model was trained and tested on the dataset, and predictions were made on sample text messages.

### Refactored Code

The refactored code introduces a function-based approach for better modularity and reusability:

- **`sms_classification` Function**: This function takes a DataFrame containing SMS messages and labels, splits the data into training and testing sets, and builds a pipeline with TF-IDF vectorization and Linear SVC. The model is trained on the training data and returned for future predictions.

- **`sms_prediction` Function**: This function uses the trained model to predict whether a given text message is spam or not. It returns a message indicating the classification result.

- **Gradio Interface**: The `sms_prediction_interface` function creates a Gradio app with a text input for SMS messages and an output displaying the prediction. The app is launched with a public link for easy access.

### Gradio Integration

Gradio is used to create a simple web interface where users can input SMS text and receive predictions. The interface is designed with input and output text boxes, providing a user-friendly experience.

## Testing

The following sample text messages can be used to test the application:

1. "You are a lucky winner of $5000!"
2. "You won 2 free tickets to the Super Bowl."
3. "You won 2 free tickets to the Super Bowl text us to claim your prize."
4. "Thanks for registering. Text 4343 to receive free updates on medicare."

These messages can be entered into the Gradio interface to see if they are classified as spam or not.
