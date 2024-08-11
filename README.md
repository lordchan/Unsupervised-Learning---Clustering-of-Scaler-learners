# Scaler Learner Profiling and Clustering

## Project Overview

This project aims to profile the best companies and job positions to work for from the Scaler database. The goal is to cluster learners based on their job profile, company, and other features, ensuring that these clusters have similar characteristics. The project involves exploratory data analysis, data preprocessing, manual clustering, and unsupervised clustering techniques.

## Dataset

The dataset used for this project is `scaler_kmeans.csv`. The data contains anonymized information about learners, including their current employer, job position, CTC, and employment details.

## Data Dictionary

- `Unnamed: 0`: Index of the dataset
- `Email_hash`: Anonymized Personal Identifiable Information (PII)
- `Company_hash`: Anonymized identifier for the company
- `orgyear`: Employment start date
- `CTC`: Current CTC
- `Job_position`: Job profile in the company
- `CTC_updated_year`: Year in which CTC got updated (Yearly increments, Promotions)

## Project Workflow

### 1. Exploratory Data Analysis (EDA)

- Imported the dataset and checked the structure and characteristics.
- Analyzed unique emails and their frequency.
- Checked for missing values and prepared the data for imputation.
- Cleaned special characters from the dataset using Regex.
- Removed duplicates from the dataset.
- Created new features like 'Years of Experience' by subtracting `orgyear` from the current year.

### 2. Manual Clustering

- Performed manual clustering based on the learner’s company, job position, and years of experience.
- Calculated the 5-point summary of CTC (mean, median, max, min, count) based on company, job position, and years of experience.
- Created flags showing learners with CTC greater than the average of their company’s department having the same years of experience:
  - **Designation Flag**: Values [1, 2, 3]
  - **Class Flag**: Values [1, 2, 3]
  - **Tier Flag**: Values [1, 2, 3]
- Answered business-related questions based on manual clustering results.

### 3. Data Pre-processing

- Imputed missing values using mean/KNN imputation.
- Cleaned company names using Regex.
- Standardized and encoded the data using label encoding/one-hot encoding.

### 4. Unsupervised Learning - Clustering

- Checked clustering tendency.
- Applied the Elbow method to determine the optimal number of clusters.
- Performed PCA and UMAP to verify the number of clusters
- Performed K-means clustering.
- Performed hierarchical clustering on a sample of the dataset.
- Provided actionable insights and recommendations based on clustering results.


## Results

1. The most common job roles we have is Backend Engineer, Full-stack and Frontend Engineer. Since we are more likely to come across such students, we can have special roadmaps prepared from scaler team for these roles.
2. CTC updated year for most students is after 2019. Our sales team can target those who have their ctc updated before 2019, because these learners will be most likely to look for appraisal. And if they haven't received it recently they are desperate for a job switch.
3. From Manual Clustering, if we are considering designation 3 students who are in a company where they are getting paid less than their fellow company collegues. Targeting them with a narrative saying that we will help them in getting appraisal. Because they are already in a good company as their peers are getting paid well. So they need not switch.
4. From Manual Clustering, if we are considering class 3 students, Targeting them with a narrative saying that we will help them in getting promotion to a higher position within the same department. Because 1. they are already in a good company as their peers are getting paid well. So they need not switch. And 2. He is probably surrounded by peers who are more senior to him and are leading the team. So for this person rather than appraisal, he can negotiate for a role with more power.
5. From Manual Clustering, if we are considering tier 3 students, Targeting them with a narrative saying that we will help them in switching to a new job role. Because point no. 1. they are already in a good company as their peers are getting paid well. So they need not switch. And point no. 2. Their peers are probably in a better job role. So we can help him transition to a higher paying job role.
6. Our marketing campains, ads and sales call resources need not be wasted on people who are in class 1, tier 1 or designation 1 as they are already having a high ctc.
7. From the top 10 companies analysis we see that there are a list of companies which pays well across different job roles. So we can be sure that we need not waste our time with students who are already in these companies.
8. From target encoding of job role column we can get a average ctc of that particular role and compare that with the ctc of a student. If it is lower than that we could ask those learners to upskill and try for an internal promotion because there is still scope for increment.
9. From target encoding of job role column we can get a average ctc of that particular role and compare that with the ctc of a student. If it is higher than the job role average, then we can ask them to take our course and upskill and switch to a better job role which is better paying but also aligning with the current skillset of the learner so that he won't be a fresher.
10. If we find the bottom 10 companies in terms of ctc, and if a student is in these companies we can pitch him that we will be helping them transition to a higher paying product based company.

## Conclusion

This project successfully profiled and clustered learners from the Scaler database based on their job profiles, companies, and other features. The combination of manual and unsupervised clustering techniques provided valuable insights and actionable recommendations for the business.

## How to Run the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/scaler-clustering.git
   cd scaler-clustering
