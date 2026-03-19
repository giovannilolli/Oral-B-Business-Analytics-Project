# P&G Geo-Analytics - Retail Marketing Optimization

# Project Overview
This was a group assignment based on a real business case for P&G. Our goal was to optimize the 2026 marketing campaign for the Oral B line in Italy. We analyzed store data from 2025 to figure out what drives sales, built a machine learning model to recommend the best stores for 2026, calculated the potential profit, and designed an AI-driven marketing strategy.

# Data Privacy Note
The datasets used in this project ("Activated_Stores" and "Italian_Stores") were provided during a university seminar with P&G representatives. To respect data privacy and potential confidentiality, I have not uploaded the raw data files to this repository. This repository contains our workflows, models, and dashboard files.

# Tools Used

Data Prep & Machine Learning: KNIME Analytics

Visualization: Microsoft Power BI

Generative AI: Langflow

# How We Built It

1. Data Cleaning and Preparation (KNIME)
We started with a main table of all Italian stores and a smaller table showing the 2025 campaign results. The results table was missing several store codes and geographic coordinates. Instead of deleting these incomplete rows—which would have ruined our small training dataset—we cross-referenced the two tables, using coordinates to find missing store codes and vice versa. We also grouped fragmented age data and calculated "Income per Capita" and "Total Purchasing Power" for each store's area.

2. Machine Learning & Cross-Validation (KNIME)
We only had 170 labeled rows to train our model on, and 310 unlabeled stores to predict. Because the training set was so small, we used a Cross-Validation loop in KNIME to make sure our models were stable. We tested three algorithms: Logistic Regression, Decision Trees, and Random Forest. After comparing their accuracy and checking for overfitting, we selected Random Forest as the best model.

<img width="776" height="511" alt="image" src="https://github.com/user-attachments/assets/01b63706-9c72-4cd2-a312-08e189b22081" />


3. Calculating Business Profit
The assignment included strict financial rules: a successful store generates €2,500 in incremental sales, but running the campaign costs €1,500 per store. We used Math and Rule Engine nodes in KNIME to turn the Random Forest probability scores into a final "Yes/No" recommendation for each of the 310 stores, ensuring our final list maximized total profit.

4. Interactive Dashboard (Power BI)
To present our findings clearly, we built a geographic dashboard in Power BI. This allowed us to map out the stores across Italy and visually explore the "typical traits" of the locations that had the highest potential for generating sales.

5. AI Marketing Content (Langflow/GPT)
To reach the customers at our recommended stores, we designed a custom virtual assistant workflow. Using a set of tailored prompts, the AI automatically generated personalized marketing messages based on the specific consumer characteristics of our target areas.

# Final Output
We summarized all our technical findings and business recommendations into a 10-minute presentation designed to be easily understood by non-technical marketing managers.
