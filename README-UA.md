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
   
**Ідентифікація користувача:** Унікальні ідентифікатори користувачів для забезпечення цілісності зразка та відстеження повторних взаємодій.  
**Часові дані:** Мітки часу, які дозволяють аналізувати тривалість тестування, сезонність та динаміку конверсій з плином часу.  
**Експериментальне групування**: Поділ аудиторії на сегменти (Група А та Група Б) для порівняльного аналізу ефективності змін.  
**Показники конверсії**: бінарні показники успіху (завершення або невдачі цільової дії), що є основою для статистичного розрахунку коефіцієнта конверсії.  
  
## Технологічний стек  
**Мова програмування:** Python 3.12  
**Бібліотеки:** Pandas, NumPy (data processing), Matplotlib & Seaborn (visualization), SciPy (Statistical Analysis).  
**Навколишнє середовище:** Jupyter Notebook / Google Colab.  

## Методологія та етапи впровадження  

**- Аналіз перед тестуванням:** Розрахунок необхідного розміру вибірки для досягнення потужності 80% та рівня значущості 5%.  
**- Очищення даних:** Очищення набору даних (20 000 записів), видалення дублікатів, перевірка на відсутність даних та перетворення типів даних.  
**- Перевірка гіпотез:**  
* Проведення Z-тесту для порівняння гіпотез.  
* Проведення T-тесту для перевірки середніх значень.  
   
**- Візуальна інтерпретація:** Побудова графіків розподілу густини (PDF), довірчих інтервалів та динаміки конверсії. 
   
## Ключові результати  
   
**Конверсія групи А:** 6.10%  
**Конверсія групи B:** 8.90%  
**P-значення:** 0.000000000000054 (результат є статистично значущим).  
**Відносне зростання:** +45.9%  
**Статистика:** Отримане p-значення (0,00000000000005) значно менше за поріг 0,05.  
**Z-статистика:** 7,52 (вище критичного значення 1,96).   
  
**Висновок:** Тестовий варіант B показав стабільне зростання конверсії. Результат тесту позитивний. Гіпотеза H1 підтверджена. Рекомендується впровадити новий дизайн екрана підписки для всіх користувачів.      
  
 ## Візуалізації  
   
Проєкт включає:
- Коефіцієнт перетворення розподілу ймовірностей. 
  
![Probability-distribution-Conversion-Rate](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/raw/main/results/Probability_distribution_Conversion_Rate_(v2).png)  
  
- Щільність розподілу ймовірностей.  
    
![Probability-distribution-Conversion-Rate](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/raw/main/results/Probability_Distribution_Conversion_Rate_(v1).png)  

- Динаміка конверсій  
  
![Probability-distribution-Conversion-Rate](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/raw/main/results/Conversion_dynamics.png)
  
## Структура проекту

**Subscription-screen-conversion-optimization/** — каталог проекту  
    ├── data/ — дані проєкту  
    │ ├──  raw/ — необроблені дані   
    │ └──  processed/ — очищені дані  
    ├── notebooks/ — головний файл з кодом аналізу  
    ├── results/ — збережені графіки та підсумкові таблиці  
    ├── reports/ — звіт про проект    
    ├── Project-logo.png — обкладинка проекту   
    ├── LICENSE — MIT License  
    ├── requirements.txt — список бібліотек для запуску проєкту   
    └── README.md — опис проекту   
  
## Як використовувати  
  
**Як використовувати цей проект**  
  
Щоб виконати цей аналіз локально, виконайте такі дії:  
  
**1. Завантажте файл проєкту**  
  
[project.ipynb](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/blob/main/notebooks/project.ipynb)  
  
Розташування файлу: https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/blob/main/notebooks/  
  
**2. Завантажити набір даних**
  
[ab_test_data.csv](https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/blob/main/data/raw/ab_test_data.csv) 

Розташування файлу:  
https://github.com/isachenko-andrii/Subscription-screen-conversion-optimization/blob/main/data/raw/    

Вміст CSV-файлу:  
  
**Детальний опис колонок:**  
  
**user_id (Object/String)**:  
Тип: Унікальний ідентифікатор користувача (UUID).  
Призначення: Використовується для ідентифікації кожного учасника тестування та відстеження дублікатів. Кожен ідентифікатор має бути унікальним у межах усього тесту.  
  
**timestamp (Datetime):**   
Тип: Дата та час (РРРР-ММ-ДД ГГ:ХХ:СС).
Призначення: Записує точний момент взаємодії користувача з варіантом тесту. Необхідно для аналізу динаміки тесту та перевірки тривалості.
Purpose: Records the exact moment when the user interacted with the test variant. Required for analyzing test dynamics and checking duration.  
  
**test_group (Categorical/String):**  
Тип: Категорична змінна.
Значення:
a — Контрольна група (поточна версія продукту).
b — Тестова група (нова версія зі змінами).
Мета: Розділяє вибірку на дві частини для порівняння.
  
**Conversion (Binary/Integer):**  
Тип: Бінарна змінна (подібна до булевої).
Значення:
0 - Цільова дія не виконана (користувач не здійснив покупку/не зареєструвався).
1 - Цільова дія виконана (успішна конверсія).
  
**3. Виконання аналізу**  
  
Ви можете відкрити блокнот у Jupyter Notebook, VS Code або завантажити його до Google Colab: 
  
• **У Jupyter:** jupyter notebook notebooks/project-notebook.ipynb  
• **У Colab:** просто завантажте project-notebook.ipynb файл до вашого Google Drive.  
  
Щоб підключити набір даних до проекту локально на кроці 1. "Збір даних" проекту, замініть шлях:  
    
**Було:**  
df_url = '/content/ab_test_data.csv'  
  
**Стало:**   
df_url = 'шлях до файлу.. /ab_test_data.csv'  
  
## Контакти  
    
**Автор:** [Andrii Isachenko](https://isachenko-andrii.github.io)    
**Посада:** Junior Data Analyst  
**LinkedIn:** [Andrii Isachenko](https://www.linkedin.com/in/isachenko-andrii/)  
**E-mail:** andrii.isachenko@gmail.com   
    
## Подяки    
  
 - Висловлюю подяку [Data Analyst/GoIT](https://goit.global/ua/courses/data-analytics/) курс, частиною навчання на якому є виконання цього проєкту.

---
  
**Статус проекту:** Завершено.
    
**Ліцензія:** MIT License.  
