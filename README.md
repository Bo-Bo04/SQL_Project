# Introduction
This project explores top-paying jobs, in-demand skills, and where high demand meets high salary in data analytics

Check the SQL queries here: [project_sql folder](/project_sql/)
### The questions I wanted to find out:
1. What are the top-paying data analyst jobs?
2. What skills are required for these top-paying jobs?
3. What skills are most in demand for data analysts?
4. Which skills are associated with higher salaries?
5. What are the most optimal skills to learn?

### Tools I used
- SQL
- PostgreSQL
- Visual Studio Code
# The Analysis
### 1. Top Paying Data Analyst Jobs
```sql
SELECT
    job_id,
    job_title,
    job_location,
    job_schedule_type,
    salary_year_avg,
    job_posted_date,
    name AS company_name
--LIKE "%Data Analyst%";
FROM
    job_postings_fact
    LEFT JOIN company_dim ON job_postings_fact.company_id = company_dim.company_id
WHERE 
    job_title_short = 'Data Analyst' -- LIKE "%Data Analyst%" de lay ten co chua data analyst
    AND job_location = 'Anywhere'
    AND salary_year_avg IS NOT NULL
ORDER BY salary_year_avg DESC
LIMIT 10
```
# What I learned
# Conclusions