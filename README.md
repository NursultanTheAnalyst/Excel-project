# Stroke Prediction Dataset

This is the link to download the dataset that I used from Kaggle:

https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset

![fs-stroke](https://github.com/user-attachments/assets/69755e63-ccc5-4af7-914a-f4a4ff1ee54b)

## Overview of the project

According to the World Health Organization (WHO) stroke is the 2nd leading cause of death globally, responsible for approximately 11% of total deaths.

The tool I will use for this case study is MS Excel 2022/GoogleSheet.

The data analytics process will follow the PMAVD (Prepare, Model, Analyze, Visualize and Dashboard) process.

## Objectives

In this dataset, I will create a dashboard that can be used to predict whether a patient is likely to get stroke based on the input parameters like gender, age, various diseases, and smoking status. Each row in the data provides relevant information about the patient.

## Measures

The dataset for the project has the following columns:

1) id: unique identifier
2) gender: "Male", "Female" or "Other"
3) age: age of the patient
4) hypertension: 0 if the patient doesn't have hypertension, 1 if the patient has hypertension
5) heart_disease: 0 if the patient doesn't have any heart diseases, 1 if the patient has a heart disease
6) ever_married: "No" or "Yes"
7) work_type: "children", "Govt_jov", "Never_worked", "Private" or "Self-employed"
8) Residence_type: "Rural" or "Urban"
9) avg_glucose_level: average glucose level in blood
10) bmi: body mass index
11) smoking_status: "formerly smoked", "never smoked", "smokes" or "Unknown"*
12) stroke: 1 if the patient had a stroke or 0 if not

*Note: "Unknown" in smoking_status means that the information is unavailable for this patient

## Dictionary

![1696237563579](https://github.com/user-attachments/assets/04df853d-a83e-45ab-b723-2a312f117a2c)

## EDA (Exploratory Data Analysis)

EDA are set of steps used to explore and understand the dataset better, before cleaning and transformation.

Rows: 5110
Columns: 12 Columns

![Снимок экрана 2024-11-22 190128](https://github.com/user-attachments/assets/8e087496-0b8c-47b0-ae31-3703983c797f)

 In gender column, ID=56156 gender is other. I will replace this value using statistics (mode).

· Age is between 0.08 and 82 years. I will use a range to group the ages.

· Heart Disease, change 0 to “None”, and 1 to “Heart Disease”.

· Marital status, change no to “Single”, and yes to “Married”.

· The BMI range from 10.3 to 97.6, with N/A. I will replace the N/A using statistics (median). Also the BMI will be grouped. Also check if the missing values (N/A) are more than 30% of the count of data in the column. If yes, delete the column and reject the data. Else continue by replacing the N/A with the mean/average.

![Снимок экрана 2024-11-22 192804](https://github.com/user-attachments/assets/6e2d6d5b-1489-44dd-a095-55d8588b236b)



![Снимок экрана 2024-11-22 192618](https://github.com/user-attachments/assets/7a4d1d75-f4b8-4dbf-9354-0c27ea9370b2)
