# The Analysis

## 1. What are the most in-demand skills for the 3 most popular data jobs?

I identified the top five most in-demand skills for the three most popular data job titles in the United States.  This analysis highlights key skills associated with these roles and helps guide job-seekers on which skills to prioritize based on their target position.

View my notebook with detailed steps here: 
[2_Skill_Count.ipynb](2_Data_Analytics_Project/2_Skills_Count.ipynb)

### Data Visualisation

```python
fig, ax = plt.subplots(len(job_titles), 1)

for i, job_title in enumerate(job_titles):
    df_job_skills = df_skills_count[df_skills_count['job_title_short'] == job_title].head(5)
    df_job_skills['skill_percentage'] = df_job_skills['skill_count'] / len(df_US[df_US['job_title_short'] == job_title]) * 100
    sns.barplot(data=df_job_skills, x='skill_percentage', y='job_skills', ax=ax[i], hue='skill_percentage', palette='dark:b_r')

    plt.show()
```

### Results

![Visualisation of Top 5 Skills for Data Jobseekers](2_Data_Analytics_Project/images/top_5_skills.png)

### Insights 
- Python is a versatile and highly in-demand skill across all three major data roles. It is most prominently required for Data Scientists (72% of job postings) and Data Engineers (65%), compared to Data Analysts (27%).

- SQL is the most requested skill for Data Analysts (50%) and Data Engineers (68%). For Data Scientists, Python takes the lead, appearing in over 72% of job postings.

- Data Engineers tend to require more specialized technical skills such as AWS, Azure, and Spark, while Data Analysts and Data Scientists are expected to be proficient in more general data analysis and management tools like R, Excel, and Tableau.- 
