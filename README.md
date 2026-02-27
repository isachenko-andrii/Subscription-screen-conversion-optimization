
![Project-logo](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/raw/main/project-logo.png)

## Project title: Subscription screen conversion optimization (A/B Test)  
  
## Project description  
This project is about statistically analyzing A/B testing results to evaluate the effectiveness of product changes. We analyzed data from 20,000 users to determine whether the difference in conversion between the control (A) and test (B) groups is statistically significant.  

## Data used  
The analysis used open data from ...  
  **Source:** [ab_test_data.csv](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/blob/main/data/raw/ab_test_data.csv)   
  **Sample size:** 20,000 users 
  **Data composition:**  
  The dataset contains granular information about user interactions during an A/B testing experiment, including unique user identifiers, precise event timestamps, experimental group assignments (Control vs. Variant), and binary conversion outcomes.  

 ## Key data attributes  
   
**User Identification:** Unique user IDs to ensure sample integrity and track repeat interactions.  
**Temporal Data:** Timestamps that allow you to analyze test duration, seasonality, and conversion dynamics over time.  
**Experimental Grouping:** Dividing the audience into segments (Group A and Group B) for comparative analysis of the effectiveness of changes.  
**Conversion Metrics:** Binary indicators of success (completion or failure of the target action), which is the basis for the statistical calculation of Conversion Rate.  
  
## Technology stack  
**Language:** Python 3.12  
**Libraries:** Pandas, NumPy (data processing), Matplotlib & Seaborn (visualization), SciPy (Statistical Analysis).  
**Environment:** Jupyter Notebook / Google Colab.  

## Key stages of analysis  
  **1. Data Cleaning:** Cleansing data from duplicates, handling missing values, and formatting timestamps.  
  **2. Pre-test Analysis:** Calculation of the required sample size (Power Analysis) to determine the sensitivity of the test.  
  **3. Statistical Testing:** Conduct an independent T-test using scipy.stats to test hypotheses.  
  **4. Visual Analysis:** Construct normal distribution curves ("bell curves") for group comparisons.  
    - Visualize conversion dynamics using a 3-day rolling mean.  
    - Compare means with 95% confidence intervals.  
   
## Key results  
   
**Conversion of group A:** 6.10%  
**Conversion of group B:** 8.90%  
**P-value:** 0.000000000000054 (the result is statistically significant).  
**Conclusion:** Test variant B showed a steady increase in conversion. The test result is positive. Hypothesis H1 is confirmed. It is recommended to implement a new design of the Subscription screen for all users.    
  
 ## Visualizations  
   
The project includes:  
 - Probability distribution conversion rate.
  
![Probability-distribution-Conversion-Rate](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/raw/main/results/Probability-distribution-Conversion-Rate.png)

  
 
  
## Project structure

**Subscription-screen-conversion-optimization/** — project directory  
    ├── data/ — project data  
    │ ├──  raw/ — raw data  
    │ └──  processed/ — cleaned data  
    ├── notebooks/ — main file with analysis code (Project_0002p.ipynb)  
    ├── results/ — saved graphs and final tables  
    ├── reports/ — report of project  
    ├── Project-logo.png — project cover  
    ├── LICENSE — license file  
    ├── requirements.txt — list of libraries to run the project  
    └── README.md — project description.  
  
## How to Use  
  
**How to use this project**  
To run this analysis locally, follow these steps:  
  
**1. Download the project file**  
  
[project.ipynb](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/blob/main/notebooks/project.ipynb)  
  
File location: https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/blob/main/notebooks/  
  
**2. Download the dataset**
  
[ab_test_data.csv](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/blob/main/data/raw/ab_test_data.csv) 

File location:  
https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/blob/main/data/raw/    

CSV file content:  
  
**Detailed description of columns:**  
  
**user_id (Object/String)**:  
Type: Unique User Identifier (UUID).  
Purpose: Used to identify each test participant and track duplicates. Each ID must be unique within the entire test.  
  
**timestamp (Datetime):**  
Type: Date and time (YYYY-MM-DD HH:MM:SS).  
Purpose: Records the exact moment when the user interacted with the test variant. Required for analyzing test dynamics and checking duration.  
  
**test_group (Categorical/String):**  
Type: Categorical variable.  
Values:  
a — Control group (current version of the product).  
b — Test group (new version with changes).  
Purpose: Divides the sample into two parts for comparison.  
  
**Conversion (Binary/Integer):**  
Type: Binary variable (Boolean-like).  
Value:  
0 - The target action was not performed (the user did not make a purchase/register).  
1 - The target action was performed (successful conversion).  
  
**3. Running the analysis**
  
You can open the notebook in Jupyter Notebook, VS Code, or upload it to Google Colab:  
  
• **For Jupyter:** jupyter notebook notebooks/project-notebook.ipynb  
• **For Colab:** simply upload the project-notebook.ipynb file to your Google Drive.  
  
To connect the dataset to the project locally in step 1. "Data acquisition" of the project, replace the path:  
    
**Was:**  
df_url = '/content/ab_test_data.csv'  
  
**Now:**   
df_url = 'path to file.. /ab_test_data.csv'  
  
## Contact  
    
**Name:** [Andrii Isachenko](https://isachenko-andrii.github.io)    
**LinkedIn:** [Andrii Isachenko](https://www.linkedin.com/in/isachenko-andrii/)  
**E-mail:** isao.datastudio@gmail.com   
  
## Acknowledgments    
  
 - Thanks to the [Data Analyst/GoIT](https://goit.global/ua/courses/data-analytics/) course, which was part of this project.

---
  
**Project Status:** Completed.
    
**License:** MIT License.  
