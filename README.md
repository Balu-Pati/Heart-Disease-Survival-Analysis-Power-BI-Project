# Heart-Disease-Survival-Analysis-Power-BI-Project
===================================================
> Analyzed clinical records of 299 patients using Power BI.
> Designed an interactive dashboard to track 67.89% survival rate, segmented by age, gender, and health conditions.
> Calculated DAX measures (e.g., Average Age of Survival = 58.76 years, > Survival Rate = 67.89%, Total Survivors vs. Deaths) to deliver accurate insights.
> Segmented patients into age groups (≤50, 51–70, ≥71), revealing that majority of survivors fall in the 51–70 age group.
> Visualized correlations between smoking, diabetes, high BP, and anaemia with survival outcomes, helping stakeholders understand healthcare risks.

💡 Impact: This project demonstrates how data visualization can transform raw healthcare data into actionable insights, supporting data-driven decisions in healthcare.

Measures Created:
-----------------

1.Average_Age_of_Survival = CALCULATE( AVERAGE(heart_Disease_clinical_records_[age]), 'heart_Disease_clinical_records_'[DEATH_EVENT]=0/100 ).

2.AGE GROUP = SWITCH( TRUE(), 'heart_Disease_clinical_records_'[age] >=40 && 'heart_Disease_clinical_records_'[age] <=50,"40-50", 'heart_Disease_clinical_records_'[age] >=51 && 'heart_Disease_clinical_records_'[age] <=60,"51-60", 'heart_Disease_clinical_records_'[age] >=61 && 'heart_Disease_clinical_records_'[age] <=70,"61-70", 'heart_Disease_clinical_records_'[age] >=71,"71+", "Below 40" ).

3.Gender = IF('heart_Disease_clinical_records_'[sex] =0,"Female","Male").

4.Survival_Rate = 1- DIVIDE( SUM(heart_Disease_clinical_records_[DEATH_EVENT]), COUNT(heart_Disease_clinical_records_[count]) ).

5.Total_Death = CALCULATE( COUNT(heart_Disease_clinical_records_[count]), 'heart_Disease_clinical_records_'[DEATH_EVENT]=1 ).

6.Total_Surviour = CALCULATE( COUNT(heart_Disease_clinical_records_[count]), 'heart_Disease_clinical_records_'[DEATH_EVENT]=0 ).
