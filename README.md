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

· Stroke, 1 means “Has Stroke”, and 0 means “No Stroke”

## Cleaning and Data Transformation 

i. Copy the whole data and paste them into the next new sheet so that we can keep the original data as it is and do data cleaning, transformations to the copied data. 

ii. Check the number of rows. Go to transform, count the rows suing =COUNTA(). The number of rows will be 5,111. But if we look carefully, there's a "Other" value in the Gender column and we will change it based on =Mode(). Then give it the value which made up most of them. 

iii. Remove unwanted columns. Remove the following: Hypertension, Work_Type, Residence_Type, Average_Glucose_Level, Smoking_Status.

iv. Change data type of the ID to text.

v. Gender. Female 2,994, Male 2,115, therefore replace "Other" with female. By ctrl+H we will replace Other with Female.

vi. Create the age range using: babies (0-2), children (3-12), teens (13-19), young adults (20-29), adult (30-45), mid age (46-60), elderly (61-120). For this purpose we use IF()

![Снимок экрана 2024-11-22 193220](https://github.com/user-attachments/assets/7a796cc1-9da0-4b0b-a88f-49a252e44fa1)

vii. Replace 1 with Heart Disease and 0 with None. Right click the column, select replace values and replace

viii. Ever-married, replace No with Single, and Yes with Married.

ix. BMI, change the data type to decimal number. This will set the N/A to errors. Then use replace errors to change the errors to 28.9.

Then set the BMI range using =IF just like we did with Age

![Снимок экрана 2024-11-22 194439](https://github.com/user-attachments/assets/8f4874fa-f477-42b5-8277-33c3c0512212)

x. In stroke column, change 1 to Stroke, and 0 to No Stroke.

## Model, Analyze, Visualize

Now Create a Pivot Table. Click on a data point, go to insert, click pivot table, click ok.

#### FIRST:
Stroke %.

Row: Stroke

Values: Count of ID
![Снимок экрана 2024-11-22 195037](https://github.com/user-attachments/assets/f077c652-e170-4e1a-97fb-b4d40040b2cf)

#### SECOND: 
Based on gender

Row: Gender

Values: Count of ID

![Снимок экрана 2024-11-22 195458](https://github.com/user-attachments/assets/a858503e-39e0-48cb-aa0b-7e4c78209448)

Findings: In the dataset, we have more females, 58.6% (2,995), than males 41.4% (2,115).



![Снимок экрана 2024-11-22 200352](https://github.com/user-attachments/assets/c1b98f59-f512-49b8-8167-00c8f0666e2e)

FINDINGS: From our analysis, when the dataset is equally distributed between females and males, I discovered that males are more likely to have stroke (5.11%) compared to females (4.71%).

#### THIRD: Based on age
![Снимок экрана 2024-11-22 200805](https://github.com/user-attachments/assets/48cd59e2-347a-4a87-9c39-9a42f84c8906)

In the dataset, we have more of elderly people (1,304), followed by middle age people (1,188), next is adults (1,103), young adults (549), children (413), teens (378 and babies (175).


![Снимок экрана 2024-11-22 201437](https://github.com/user-attachments/assets/20542ffd-6c85-4c7a-8ab4-b597b66ced80)
FINDINGS:

Elderly people are more likely to have stroke (13.57%), followed by middle age (4.97%), adult have a (1.00%) chance, babies have 0.57% and teens have 0.26%.

Based on the dataset, I don't have any record of young adults and children affected by stroke.

#### FOURTH: Marital Status

![Снимок экрана 2024-11-22 202110](https://github.com/user-attachments/assets/4609af61-e9c9-49ab-b480-6074bce0843d)

FINDINGS:

From this dataset, married people (6.6%) are more likely to have stroke than single people (1.7%)



#### FIFTH: Based on BMI Range

![Снимок экрана 2024-11-22 202500](https://github.com/user-attachments/assets/c299c53e-5ff6-4808-b779-ba293210a6de)

From the dataset, we have obesity 1,920, followed by overweight 1,610, healthy weight, 1,231 and underweight 349.



![Снимок экрана 2024-11-22 202820](https://github.com/user-attachments/assets/ebbedb80-579b-4fe1-91d6-e86539b8f746)

FINDINGS:

Over weight people are most likely to have stroke (7.14%), followed by Obesity (5.10%), Healthy Weight (2.84%), and people that are under weight will most likely not have stroke (0.29%).


 #### SIXTH: Based on Heart Disease

![Снимок экрана 2024-11-22 203307](https://github.com/user-attachments/assets/a1bfe79e-5c0d-4393-8f4e-3d064bd82ccc)


From the dataset, we have more people with no heart disease (4,834), than people with heart disease (276).

![Снимок экрана 2024-11-22 203525](https://github.com/user-attachments/assets/74c1417b-a34f-4bb0-9132-2445b5578c39)


FINDINGS:

People with heart disease are most at risk (17.03%) for developing stroke, compared to people with no heart disease (4.18%).



