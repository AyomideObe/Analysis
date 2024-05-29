
# Absenteeism at Work

### Dashboard Link : https://app.powerbi.com/groups/me/reports/a63d7552-cc61-4ad6-be15-ba25ad714920?pbi_source=desktop
## Problem Statement

The HR department requires data analysis support to optimize employee wellness programs and improve workforce management. This project aims to address three key requests:

- Identify Eligible Participants for Healthy Bonus Program: Develop a system to identify employees with a clean bill of health and a low absenteeism record who qualify for a $1,000 healthy bonus. This will incentivize healthy lifestyles and potentially reduce healthcare costs.

- Calculate Wage Increase for Non-Smokers: Analyze employee data to determine the appropriate wage increase for non-smoking employees. The analysis should consider the total insurance budget of $983,221 for non-smokers, aiming to allocate a portion of the savings from lower healthcare expenses towards wage increases and potentially improve employee retention.

- Build Absenteeism Dashboard based on HR Wireframe: Create a data visualization dashboard aligned with the HR department's approved wireframe. This dashboard will provide insights into absenteeism patterns across the organization, helping HR identify areas for improvement and implement targeted interventions to reduce absenteeism and its associated costs.

By addressing these requests, this data analytics project will contribute to a healthier workforce, improved employee morale, and potentially generate cost savings for the organization.


### Steps followed 
- Step 1 : Preprocessing and Identifying Healthy Employees
        Clean and filter data in MySQL Workbench based on analysis criteria.
Define and apply conditions to determine employee health status.
        Utilize COUNT(*) function to identify the number of employees meeting health criteria (111 out of 740).
        Then calculate individual bonus amount based on total bonus pool and number of qualifying employees ($1,000 / 111 = $9 per employee).

  The SQL query below is used to calculate the list of healthy individuals with a low absent record.

        # List of Healthy individuals with low Absent record is 111, each employee gets per hour they get $9  
        Select count(*) as Healthy_Employees from `work`.absenteeism_at_work 
        WHERE  `Body mass index` between 18.5 and 24.9 and `Social smoker` = 0 and `Social drinker` = 0 and `Absenteeism time in hours` < 6.92        

- Step 2: Analyzing and Calculating Wage Increase for Non-Smokers
        Identify the total number of non-smokers in the dataset (686).
        Divide the allocated non-smoker insurance budget by the total number of non-smokers to determine individual wage increase amount ($983,221 / 686 = $1,414.

  The SQL code below is used to calculate the compensation for non-smokers based on the given budget
  
        # compensate non-smokers/ budget $983,221  so 0.68 increase per hour/ 1,414.4 per year
        select count(*)  as non_smokers from `work`.absenteeism_at_work
        where `Social smoker` = 0;
- Step 3: Building Absenteeism Dashboard based on HR Wireframe
        Design dashboard header titled "HR Analytics: Absenteeism."
        Develop visualizations based on the approved HR wireframe to analyze absenteeism patterns (details on specific visualizations can be omitted).


## Snapshots and Discription of each sections

### SECTION 1: 
![SECTION 1](https://github.com/AyomideObe/Analysis/assets/158526132/04e97e03-9e68-42ce-8087-94755e56c0a6)

The primary component within this section is the Key Performance Indicator (KPI), accompanied by Power BI Smart Narrative functionality. This feature dynamically updates based on the selected filters within the dashboard, providing real-time insights.
Additionally, a splicer is incorporated to facilitate seasonal analysis, allowing users to effortlessly observe how the KPI fluctuates across different months throughout the year. Another splicer is included to display the Body Mass Index (BMI) category of employees, categorized into Healthy, Overweight, and Obese segments.

### SECTION 2:
![SECTION 2](https://github.com/AyomideObe/Analysis/assets/158526132/670a9c7d-53e0-4d62-9d5d-e0468f83813d)

The Employee and Category section presents essential metrics regarding employees' absenteeism. It includes the total number of employees and their corresponding total absentee hours, providing a comprehensive overview of workforce absenteeism.
In addition to these metrics, the section features four distinct pie charts. Each chart offers insights into various employee characteristics, including Education, Pet ownership, BMI Category, and number of Children. These visualizations serve to illustrate the distribution of employees across different categories, enhancing understanding of workforce demographics and potential factors influencing absenteeism.

### SECTION 3:
![SECCTION 3 4](https://github.com/AyomideObe/Analysis/assets/158526132/244d2fe8-ada4-4684-8582-8ef2d83e1e1d)

The final two sections of the dashboard focus on tracking trends over time and analyzing the reasons for employee absenteeism.
The Trends Over Time section provides dynamic visualizations that illustrate how absenteeism patterns evolve over different time periods. Users can interact with these metrics, such as selecting specific time ranges or intervals, to gain deeper insights into temporal trends.


## Full visualization 
![Full Visual of Absenteeism](https://github.com/AyomideObe/Analysis/assets/158526132/b56cf13c-50bb-4282-ac1c-dbb69a29670a)
