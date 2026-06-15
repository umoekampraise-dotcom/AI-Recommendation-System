# AI-Recommendation-System
An AI Recommendation System that calculates using mathematics to accurately recommend your role based on the skills you input. 

markdown

 # 🧑‍💻 Recommendation System
 

## 🤷‍♂️ What This Recommendation System Does?
This system offers you Top 5 roles that will suit you best after you input your skills.

## How It Works
1. Gets User to type in their skills
2. System converts skills into numbers using TF-IDF
3. Cosine Similarity measures how closely skills match each role
4. Top 3 matches are returned

## 👩‍💻Technologies Used
- Python
- Pandas
- Scikit-learn (TF-IDF, Cosine Similarity)


## Complete Pipeline

### Step 1 (INSTALL LIBRARIES)
import pandas as pd
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.metrics.pairwise import cosine_similarity

### Step 2 (READ THE RAW-SKILL.CSV I CREATED)
df = pd.read_csv("raw-skills.csv")

### Step 3 (GETS USER'S SKILLS)
user_input = input("Enter your skills (separated by spaces): ")

###Step 4 (LEARNING THE DATA IN RAW-SKILLS.CSV FILE)
tdif_matrix = vectorizer.fit_transform(df["skills"])

### Step 4 (APPLY THE DATA LEARNT ON THE USER'S SKILLS)
user_vector= vectorizer.transform([user_input])

### Step 5 (MEASURES THE ROLE MATHEMATICALLY TO MATCH FROM TOP 1-TOP 3)
scores = cosine_similarity(user_vector, tdif_matrix)
top_indices = scores[0].argsort()[::-1][:3]

### Step 6 (RECOMMENDS THE TOP 3 ROLES TO THE USER)
print("\n Top 3 Recommended Roles for you:")
for i , idx in enumerate(top_indices):
    role=df["role"].iloc[idx]
    score=scores[0][idx]
    print(f"{i + 1}. {role} - Match score: {round(score * 100, 2)}%")


## How To Run It
1. Clone the repository
2. Make sure you have Python installed
3. Install requirements: pip install pandas scikit-learn
4. Run: python recommender.py
5. Type in your skills when prompted

## RESULT Example
Enter your skills (separated by spaces): pandas n8n Workflow_automation make.com zapier sklearn promptengineering basicpython APIs machine_learning

 Top 3 Recommended Roles for you:
1. AI Automation Specialist - Match score: 69.74%
2. AI Engineer - Match score: 26.71%
3. Data Scientist - Match score: 22.58%

Process finished with exit code 0


## 📁 Dataset Structure (raw-skills.csv)

| role | skills |
|------|--------|
|AI Engineer | Python TensorFlow PyTorch Machine_Learning Deep_Learning APIs Model_Deployment Docker|
|Prompt Engineer | LLMs Prompt_Design ChatGPT Claude API_Integration NLP AI_Tools Evaluation Fine_Tuning|
|AI Automation | Specialistn8n Make Zapier APIs Workflow_Automation LLMs Prompt_Design No_Code AI_Tools|
|AI Trainer | Python Data_Labeling Annotation Prompt_Design LLMs Evaluation Quality_Control RLHF|
|Machine Learning Engineer | Python Scikit_learn TensorFlow PyTorch Model_Training Feature_Engineering Data_Preprocessing Statistics|
|Data Scientist | Python SQL Statistics Data_Analysis Machine_Learning Data_Visualization Pandas Numpy Jupyter|
|NLP Engineer | Python NLP Transformers BERT LLMs Text_Processing Hugging_Face Deep_Learning Linguistics|
|Computer Vision Engineer | Python OpenCV TensorFlow PyTorch Image_Processing CNNs Object_Detection Deep_Learning|
|MLOps Engineer | Python Docker Kubernetes CI_CD Model_Deployment AWS Cloud MLflow Monitoring|
|Data Analyst | Python SQL Excel Data_Visualization Pandas Statistics Power_BI Reporting Business_Intelligence|




## About
Built by Torobong Umoekam as part of DecodeLabs AI Engineering 
Internship Project 3
📧 umoekampraise@gmail.com 🔗 LinkedIn: https://www.linkedin.com/in/torobong-umoekam-32b0b2291


