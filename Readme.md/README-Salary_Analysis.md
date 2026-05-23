# The Analysis

## What are the most demanded skills for top three most popular data roles?

To find the most demanded skills for the top 3 most popular roles. I filtered out those positions by which ones were the most popular, and got the top 5 skils for these top 3 roles, these queries high lights the most popular job titles and their top skills, shwing their top skills i should pay attention to depnding on the role i am interested.

View my notebook with detailed steps here:[2_Skill_Demand.ipynb](2__Project\2_Skill_Demand.ipynb)

### Visualize Data

```python
fig, ax = plt.subplots(len(job_titles), 1, figsize=(10, 6*len(job_titles)))

for i, job_title in enumerate(job_titles):
    df_plot = df_skills_count[df_skills_count['job_title_short'] == job_title].head(5)
    
    df_plot.plot(
        kind='barh', 
        x='job_skills', 
        y='skill_count', 
        ax=ax[i],           # ← Fixed: use ax[i]
        title=job_title
    )
    
    # Optional: Improve appearance
    ax[i].invert_yaxis()    # So highest skill is at the top
    ax[i].set_xlabel('Skill Count')
    ax[i].legend().set_visible(False)

plt.tight_layout()
plt.show()


```python
 
## 3.How well do jobs and skills pay for Data Engineers?

### Salary Analysis for Data Engineers

### Visualize Data

```python
sns.boxplot(data=df_Canada_top6, x='salary_year_avg',y='job_title_short', order= job_order)
sns.set_theme(style='ticks')



plt.title('Salary Didstribution in the Canada Country')
plt.xlabel('Yearly Salary($Ksh)')
plt.ylabel('')
ax = plt.gca()
ax.xaxis.set_major_formatter(plt.FuncFormatter(lambda x, pos: f'${int(x/1000)}'))
plt.xlim(0,600000)
plt.show()

```python

![salary Distributions of Data Jobs in the US]
(2__Project\Images\salary_analysis.png)
*Box plot visualizing the salary distributions for the top 6 data job titles.*

## 💰 Salary Analysis

![Salary Distribution in Canada](2__Project/Images/salary_analysis.png)

### Key Insights:

- **Machine Learning Engineer** leads with the highest median salary.
- **Senior Data Engineer** and **Software Engineer** also show strong earning potential.
- **Data Analyst** has the lowest median and tightest salary distribution.
- Significant high-end outliers exist, especially for Data Scientists and Data Engineers, indicating potential for very high compensation with experience.

**Conclusion**: The Canadian data job market offers lucrative opportunities, particularly for specialized and senior roles.

# The Analysis
## How well do jobs and skills pay for the Data
###Highest Paid 6 Most demanded skills for Data
#### Visualixze Data

```Python
fig, ax = plt.subplots(2, 1, figsize=(10, 24))

sns.set_theme(style="ticks")

# Top 10 Highest Paid skills in DE 
sns.barplot(data=df_DE_top_pay, x='median', y=df_DE_top_pay.index, ax=ax[0],hue='median',palette='dark:b_r')
ax[0].legend().remove()

ax[0].set_title('Top 10 Highest Paid Data Jobs')
ax[0].set_ylabel('')
ax[0].set_xlabel('')
ax[0].xaxis.set_major_formatter(plt.FuncFormatter(lambda x, _: f'${int(x/1000)}K'))  # ✅

sns.barplot(data=df_DE_skills, x='median', y=df_DE_skills.index, ax=ax[1],hue='median',palette='light:b')
ax[1].legend().remove()
ax[1].set_title('Most Common Skills for DE in Canada')
ax[1].set_ylabel('')
ax[1].set_xlim(ax[0].get_xlim())
ax[1].xaxis.set_major_formatter(plt.FuncFormatter(lambda x, _: f'${int(x/1000)}K'))  # ✅

plt.tight_layout()
plt.show()

```

In-demand skills for DE in Canada:
![The Highest Psaid %& Most in demand skills for Data Anlysts in the US](Readme.md\README-Salary_Analysis.md)
* Two separate bar graphs but visualizing the highest paid skills and most in demand skills for data analysts in the US*
