![Project-logo](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/raw/main/project-logo.png)
#### [EN](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/blob/main/README.md) | [UA](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/blob/main/README-UA.md) Цей матеріал також доступний англійською мовою..
---  
<div align="center">  
    
## Оптимізація конверсії екрану підписки<br>(A/B Test)   
  
</div>
  
## Опис проекту
Цей проєкт аналізує результати A/B-тестування. Метою дослідження є перевірка гіпотези про те, що візуальне виділення переваги (додавання банера «Знижка 50%) збільшить конверсію в тижневу підписку, навіть якщо фактична ціна ($4,99) залишається незмінною.  
  
## Постановка проблеми  
Необхідно визначити, чи є різниця в поведінці користувачів між контрольною та тестовою групами статистично значущою. Бізнес-мета полягає в прийнятті рішення на основі даних: впровадити новий дизайн екрана оплати для 100% трафіку чи зберегти поточну версію.  
  
## Використані дані   
  **Джерело даних:** [ab_test_data.csv](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/blob/main/data/raw/ab_test_data.csv)   
  **Розмір вибірки:** 20,000 користувачів  
  **Склад даних:** 
  Набір даних містить детальну інформацію про взаємодію користувачів під час A/B-тестування, включаючи унікальні ідентифікатори користувачів, точні позначки часу подій, розподіл експериментальних груп (контрольна група проти варіантної) та результати бінарної конверсії.  

 ## Ключові атрибути даних  
   
**User Identification:** Unique user IDs to ensure sample integrity and track repeat interactions.  
**Temporal Data:** Timestamps that allow you to analyze test duration, seasonality, and conversion dynamics over time.  
**Experimental Grouping:** Dividing the audience into segments (Group A and Group B) for comparative analysis of the effectiveness of changes.  
**Conversion Metrics:** Binary indicators of success (completion or failure of the target action), which is the basis for the statistical calculation of Conversion Rate.  
  
## Технологічний стек  
**Language:** Python 3.12  
**Libraries:** Pandas, NumPy (data processing), Matplotlib & Seaborn (visualization), SciPy (Statistical Analysis).  
**Environment:** Jupyter Notebook / Google Colab.  

## Методологія та етапи впровадження  

**- Pre-test Analysis:** Calculating the required sample size to achieve 80% power and a 5% significance level.  
**- Data Cleaning:** Cleaning the dataset (20,000 records), removing duplicates, checking for missing data, and converting data types.  
**- Hypothesis Testing:**  
 * Conducting a Z-test to compare hypotheses.  
 * Conducting a T-test to verify mean values.  
   
**- Visual Interpretation:** Plotting density distribution graphs (PDF), confidence intervals, and conversion dynamics.  
   
## Ключові результати  
   
**Conversion of group A:** 6.10%  
**Conversion of group B:** 8.90%  
**P-value:** 0.000000000000054 (the result is statistically significant).  
**Relative growth:** +45.9%  
**Statistics:** The resulting p-value (0.00000000000005) is significantly less than the threshold of 0.05.  
**Z-statistic:** 7.52 (above the critical value of 1.96).  
  
**Conclusion:** Test variant B showed a steady increase in conversion. The test result is positive. Hypothesis H1 is confirmed. It is recommended to implement a new design of the Subscription screen for all users.    
  
 ## Візуалізації 
   
The project includes:  
 - Probability distribution conversion rate.
  
![Probability-distribution-Conversion-Rate](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/raw/main/results/Probability_distribution_Conversion_Rate_(v2).png)  

- Probability distribution density.
    
![Probability-distribution-Conversion-Rate](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/raw/main/results/Probability_Distribution_Conversion_Rate_(v1).png)  

- Conversion dynamics
  
![Probability-distribution-Conversion-Rate](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/raw/main/results/Conversion_dynamics.png)
 
  
## Структура проекту

**Subscription-screen-conversion-optimization/** — project directory  
    ├── data/ — project data  
    │ ├──  raw/ — raw data  
    │ └──  processed/ — cleaned data  
    ├── notebooks/ — main file with analysis code  
    ├── results/ — saved graphs and final tables  
    ├── reports/ — report of project  
    ├── Project-logo.png — project cover  
    ├── LICENSE — MIT License  
    ├── requirements.txt — list of libraries to run the project  
    └── README.md — project description.  
  
## Як використовувати  
  
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
  
## Контакти  
    
**Ім'я:** [Andrii Isachenko](https://isachenko-andrii.github.io)    
**LinkedIn:** [Andrii Isachenko](https://www.linkedin.com/in/isachenko-andrii/)  
**E-mail:** isao.datastudio@gmail.com   
    
## Подяки    
  
 - Висловлюю подяку [Data Analyst/GoIT](https://goit.global/ua/courses/data-analytics/) курс, частиною навчання на якому є виконання цього проєкту.

---
  
**Статус проекту:** Завершено.
    
**Ліцензія:** MIT License.  
