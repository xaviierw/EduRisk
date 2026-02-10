## EduRisk – Student Dropout Risk Prediction System

EduRisk is a machine learning–powered web application designed to predict the likelihood of student dropout based on academic performance, demographic attributes, and socioeconomic indicators. The project focuses on interpretability, iterative model development, and responsible use of predictive analytics in education.

The system combines a trained machine learning model with an interactive Streamlit interface to allow users to explore predictions and understand key contributing factors.

## Project Objectives

- Predict student dropout risk using historical academic data
- Explore and validate multiple machine learning models
- Apply feature engineering to improve predictive performance
- Ensure model outputs are interpretable and realistic
- Deploy a user-friendly web application for demonstration and analysis

## Dataset

- This project uses the UCI Machine Learning Repository dataset:
  - "Predict Students’ Dropout and Academic Success"

- The dataset contains student-level information including:
  - Demographic attributes
  - Academic performance across two semesters
  - Enrollment and assessment statistics
  - Economic indicators (e.g. unemployment rate, inflation rate)

- Original target classes:
  - Dropout
  - Enrolled
  - Graduate

- For later iterations, the target was reframed into a binary classification:
  - Dropout
  - Not Dropout (Enrolled + Graduate)

## Machine Learning Approach

- The project follows an iterative modeling pipeline:

- Iteration 1 – Baseline Models
  - Logistic Regression
  - Decision Tree
  - Random Forest
  - Gradient Boosting

- Iteration 2 – Feature Engineering
  - Aggregated semester-level features (averages across semesters)
  - Approval rates and derived academic performance metrics
  - Original semester-specific features retained initially for validation

- Iteration 3 – Binary Target Reframing
  - Converted multi-class target into binary classification
  - Feature importance analysis conducted
  - Model retrained using selected important features

- Iteration 4 – Final Model Selection
  - Random Forest selected due to:
    - Balanced performance across classes
    - Robust handling of non-linear relationships
    - Reduced overfitting through ensemble learning
    - More realistic probability distributions

## Model Artifacts

- The repository includes:
  - Trained machine learning model saved using joblib
  - Feature column list used during training
  - Default input values for Streamlit UI consistency

- These artifacts ensure reproducibility between training and deployment.

## Web Application

- The EduRisk web application is built using Streamlit.
- Key features:
  - Interactive input controls for academic and demographic variables
  - GPA conversion helper for non-20-point grading systems
  - Dropout risk probability output
  - Feature importance visualization
  - Comparison between user input and dataset averages
  - Clean and accessible UI designed for analysis rather than decision-making

## Tech Stack

- Python
- Pandas, NumPy
- Scikit-learn
- Streamlit
- Joblib
- Matplotlib / Seaborn (for analysis)

## Project Structure

- app.py
  - Main Streamlit application

- app_utils.py
  - Utility functions for loading models, preprocessing, and visualization

- artifacts/
  - Saved model files and feature metadata

- notebooks/
  - Jupyter notebooks for EDA, feature engineering, and model training

- requirements.txt
  - Python dependencies

## Deployment

- The application is designed to be deployed using Streamlit Community Cloud.
- Deployment requirements:
  - Public GitHub repository
  - requirements.txt with pinned dependencies
  - app.py as the main entry point

## Ethical Considerations

- EduRisk is intended for educational and analytical purposes only.
- Important notes:
  - Predictions should not be used as the sole basis for academic or administrative decisions
  - Outputs represent probabilities, not certainties
  - Model bias and dataset limitations are acknowledged
  - Interpretability is prioritised over raw accuracy

## Future Improvements

- Bias and fairness evaluation across demographic groups
- Confidence interval visualization for predictions
- Explainability methods such as SHAP
- Expanded UI explanations for non-technical users
- Support for institution-specific data retraining

## Author

- EduRisk was developed as part of a machine learning project focused on applied data science, interpretability, and responsible AI deployment in education.
