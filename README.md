Here is the `README.md` file in English, following the structure from the image and using the data from the provided PDF report.

***

# Students Exam Score Analysis

## Overview
This program performs exploratory data analysis (EDA) and predictive modeling on a dataset of students' exam scores. It explores relationships between study habits and academic performance and trains regression models to predict exam scores.

## Business Problem
The primary objective of this analysis is to understand the factors that contribute to student success and to build a model capable of predicting exam scores. By identifying key drivers (such as study hours or attendance), educators and students can focus on the most impactful habits to improve performance. The project also aims to classify students based on a pass/fail threshold to identify those at risk.

## Dataset
The analysis is based on the student_exam_scores.csv file. It contains 200 entries describing student habits and performance.
Data Source: https://www.kaggle.com/datasets/kainatjamil12/students-exams-score-analysis-dataset/data

* **Key Features:**
    * `student_id`: Unique identifier for each student.
    * `hours_studied`: Number of hours spent studying (Range: 1.0 - 12.0).
    * `sleep_hours`: Average hours of sleep (Range: 4.0 - 9.0).
    * `attendance_percent`: Percentage of class attendance.
    * `previous_scores`: Scores from previous exams.
    * `exam_score`: The target variable (final exam score).
* **Derived Features:**
    * `isPassed`: A categorical variable created during the analysis (Passed if score > 30.0, otherwise Failed).

## Tools & Technologies
The project is implemented in Python using the following libraries:
* **Data Manipulation:** `pandas`, `numpy`.
* **Visualization:** `seaborn`, `matplotlib.pyplot`.
* **Machine Learning:** `sklearn` (LinearRegression, RandomForestRegressor, train_test_split, metrics) .

## Project Structure
1.  **Importing Libraries:** Loading necessary Python packages.
2.  **Loading Data:** Reading the CSV file into a DataFrame.
3.  **Data Inspection:** Checking data types and basic descriptive statistics.
4.  **Data Cleaning:** Checking for null values and duplicates (none found).
5.  **Feature Engineering:** Creating the `isPassed` column.
6.  **Exploratory Data Analysis (EDA):** Visualizing relationships and distributions.
7.  **Model Training:** Splitting data and fitting Linear Regression and Random Forest models.
8.  **Evaluation:** Comparing models using MSE and $R^2$ metrics.

## Data Cleaning & Preparation
* **Null Values:** The dataset was checked for missing values, and none were found.
* **Duplicates:** Duplicate entries were checked and removed if present.
* **Categorization:** A new column `isPassed` was added to categorize scores based on a threshold of 30.0.

## Exploratory Data Analysis (EDA)
Key visualizations included:
* **Scatter Plots:** Showed a clear direct relationship between `hours_studied` and `exam_score`, colored by the pass/fail status.
* **Linear Regression Plots:** Visualized the trend lines for `hours_studied` and `attendance_percent` against exam scores.
* **Correlation Heatmap:** Revealed that `hours_studied` has a strong positive correlation (0.78) with `exam_score`, while `sleep_hours` has almost no correlation (0.08).
* **Histograms:** Displayed the distribution of study habits and scores across the student population.

## Research Questions & Key Findings
* **What affects exam scores the most?** The number of hours studied is strongly associated with the exam score (0.78 correlation).
* **Does sleep affect the score?** There is a negligible correlation (0.08) between sleep hours and exam scores in this dataset.
* **Model Performance:**
    * **Linear Regression:** Performed well with a Test $R^2$ of **0.82** and Test MSE of **8.37**.
    * **Random Forest:** Performed significantly worse with a Test $R^2$ of **0.63** and Test MSE of **17.06**, indicating potential overfitting or unsuitability for this specific linear trend.

## Dashboard
The project generates a series of plots that serve as an analytical dashboard:
1.  Exam Score vs. Hours Studied (Scatter with hue).
2.  Correlation Matrix Heatmap.
3.  Distribution Histograms for all numeric variables.
4.  Predicted vs. Experimental Exam Score scatter plot.

## How to Run This Project
1.  Ensure you have Python installed with `pandas`, `seaborn`, `matplotlib`, and `scikit-learn`.
2.  Place `student_exam_scores.csv` in the same directory as the script.
3.  Run the script/notebook.
4.  The output will display the dataframe info, statistical summaries, generate the plots, and print the model evaluation metrics (MSE and $R^2$) for both models.

## Final Recommendations
Based on the analysis:
* **Model Selection:** The **Linear Regression** model is recommended for predicting scores on this dataset as it achieved a significantly higher accuracy ($R^2 = 0.82$) compared to the Random Forest Regressor ($R^2 = 0.63$).
* **Student Advice:** To pass the exam and achieve higher scores, students should prioritize increasing their study hours, as this variable shows the strongest positive impact on results.

## Author & Contact
* **Author:** Marta Golka
* **Date:** November 20, 2025
* **E-mail:** golka.marta09@gmail.com
