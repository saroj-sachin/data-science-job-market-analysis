# Data Science Job Market Analysis in Excel

## Introduction  
A comprehensive analysis of data science job market trends, implemented as a hands-on project using Excel.  
It showcases the use of Excel's power tools for data analysis and visualizations.  

### Questions to Analyze  
To understand the data science job market, I asked the following questions:  

1. **Do more skills get a higher salary?**
2. **What is the salary for data science jobs in different regions?**
3. **What are the top skills for data science jobs?**
4. **What are the top high paying skills?**

### Excel Skills Used  
The following are the Excel skills utilized for analysis:

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### Data Jobs Dataset

The dataset used for this project contains real-world data on job information in data science from 2023. The dataset is acquired from Luke Barousse's YouTube channel.

It includes detailed information on :

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**


## 1️⃣ Do more skills get a higher salary

### Skill: Power Query (ETL)

#### Extract
- I first used Power Query to extract the original data (job_market_analysis.xlsx) and created two Queries:
  1. First one with all the data jobs information.
  2. The second listing the skills for each job ID.

#### Tranform
- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
  - data_jobs_all
    
    <img src="/Screenshots/applied_steps_1.png" width="330.5" height="358">

  - data_jobs_skills

    <img src="/Screenshots/applied_steps_2.png" width="330.5" height="358">

#### Load
- Finally, I loaded both transformed queries into the Excel workbook, setting the foundation for my subsequent analysis.
  - data_jobs_all
    
    <img src="/Screenshots/data_jobs_all.png">

  - data_jobs_skills
 
    <img src="/Screenshots/data_jobs_skills.png">

### Analysis

#### 💡 Insights

- There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

    <img src="/Screenshots/salary_vs_skills.png">

#### 🤔 So What

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.


## 2️⃣ What is the salary for data science jobs in different regions?

### Skills: PivotTables & DAX

#### Pivot Table

- I created a PivotTable using the Data Model I created with Power Pivot.
- I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
- Then I added new measure to calculate the median salary for United States jobs.

  ```
  =CALCULATE(
      MEDIAN(data_jobs_all[salary_year_avg]),
      data_jobs_all[job_country] = "United States")
  ```

#### DAX
- To calculate the Median Yearly Salary I used DAX.

  ```
  Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
  ```

### Analysis

#### 💡 Insights

- Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

  <img src="/Screenshots/salary_analysis.gif">

#### 🤔 So What

- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.


## 3️⃣ What are the top skills for data science jobs?

### Skill: Power Pivot

#### Power Pivot

- I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- Since I had already cleaned the data using Power Query, Power Pivot created a relationship between these two tables.

#### Data Model

- I created a relationship between my two tables using the `job_id` column.

  <img src="/Screenshots/data_model.png">

#### Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

  <img src="/Screenshots/power_pivot.png">

### Analysis

#### 💡 Insights

- SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

  <img src="/Screenshots/job_analysis.gif">

#### 🤔So What

- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.


## 4️⃣ What are the top high paying skills?

### Skill: Advanced Charts (Pivot Chart)

#### PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
  1. **Primary Axis:** Median Salary (as a Clustered Column)
  2. **Secondary Axis:** Skill Likelihood (as a Line with Markers)

- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### 📊 Analysis

#### 💡 Insights

- Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
- Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

  <img src="/Screenshots/skill_likelihood.gif">

### 🤔So What

- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

## Conclusion

As an aspiring data analyst, I embarked on this Excel-based project to uncover valuable insights about the data science job market. Using the dataset from the Luke Barousse's Excel course on YouTube, I analyzed job titles, salaries, locations, and essential skills. 

By leveraging Excel features like Power Query, PivotTables, DAX, and charts, I discovered key correlations between multiple skills and higher salaries, particularly in Python, SQL, and cloud technologies. 

I hope this project serves as a practical guide for data professionals and provides an overview of the skills needed for higher-paying roles.
