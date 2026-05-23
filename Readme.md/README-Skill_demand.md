# Python Data Analysis - Canadian Job Market Skills

An exploratory data analysis project on **in-demand skills** in the Canadian job market for Data roles.

## 📊 Project Overview

This project analyzes real job postings to discover the most requested technical skills for positions like:
- Data Engineer
- Data Analyst  
- Senior Data Analyst
- Business Analyst
- Cloud Engineer
- Data Scientist

## 🎯 Main Goals
- Clean and process job skills data
- Calculate skill demand as **percentage**
- Visualize top skills per job title using Seaborn

## 🛠 Technologies Used
- Python
- Pandas
- Matplotlib & Seaborn
- Jupyter Notebook

## 📁 Project Structure

View my notebook with detailed steps here:[2_Skill_Demand.ipynb](2__Project\2_Skill_Demand.ipynb)

### Visualize Data

```pythonimport seaborn as sns
import matplotlib.pyplot as plt

sns.set_theme(style='whitegrid')

fig, ax = plt.subplots(len(job_titles), 1, figsize=(14, 6 * len(job_titles)))

for i, job_title in enumerate(job_titles):
    df_plot = df_skill_perc[df_skill_perc['job_title_short'] == job_title].head(5).copy()
    
    # Sort so highest skill is at the top
    df_plot = df_plot.sort_values(by='skills_perc', ascending=True)
    
    sns.barplot(
        data=df_plot, 
        x='skills_perc', 
        y='job_skills', 
        ax=ax[i],
        palette='Blues_d',           # Clean dark-to-light blue
        hue='skills_perc',           # Color intensity based on percentage
        legend=False
    )

    ax[i].invert_yaxis()
    
    # Improve appearance
    ax[i].set_title(job_title, fontsize=13, pad=12)
    ax[i].set_ylabel('')
    ax[i].set_xlabel('Skill Percentage (%)' if i == len(job_titles)-1 else '')
    ax[i].set_xlim(0, 80)
    
    # Add percentage labels on the bars
    for container in ax[i].containers:
        ax[i].bar_label(container, fmt='%.1f%%', padding=5, fontsize=11)

    if i !=len(job_titles) - 1:
        ax[i].set_xticks([])    

fig.suptitle('Likelihood of Skills Requested in Canada Job Postings', 
             fontsize=18, y=0.98)
fig.tight_layout()
plt.show()
```Python

###  Results

![Visualization of top Skills for Data Nerds]
(2__Project\Images\Skill_Demand Oof_data_roles.png)

### Insights
## 📌 Key Insights

- **SQL** is the most demanded skill across all roles, especially ## 📌 Key Insights

- **SQL** is the most demanded skill across all roles, especially for Data Engineers (65–67%).
- **Python** is extremely important — nearly as critical as SQL for Data Engineers and Senior Data Engineers.
- **Data Analysts** rely heavily on **Excel, Tableau, and Power BI** in addition to SQL and Python.
- **Cloud skills** (AWS and Azure) are highly valued for Data Engineer roles, with AWS being particularly strong for Senior positions.
- **Big Data tools** like **Spark** show strong demand in Engineering roles (over 40% for Senior Data Engineers).

**Summary**: SQL and Python dominate the Canadian data job market, while cloud platforms and visualization tools are key differentiators by role.for Data Engineers (65–67%).
- **Python** is extremely important — nearly as critical as SQL for Data Engineers and Senior Data Engineers.
- **Data Analysts** rely heavily on **Excel, Tableau, and Power BI** in addition to SQL and Python.
- **Cloud skills** (AWS and Azure) are highly valued for Data Engineer roles, with AWS being particularly strong for Senior positions.
- **Big Data tools** like **Spark** show strong demand in Engineering roles (over 40% for Senior Data Engineers).

**Summary**: SQL and Python dominate the Canadian data job market, while cloud platforms and visualization tools are key differentiators by role.

# Python Data Analysis - Canadian Job Market Skills

An exploratory data analysis project on **in-demand skills** in the Canadian job market for Data roles.

## 📊 Project Overview

This project analyzes real job postings to discover the most requested technical skills for positions like:
- Data Engineer
- Data Analyst  
- Senior Data Analyst
- Business Analyst
- Cloud Engineer
- Data Scientist

## 🎯 Main Goals
- Clean and process job skills data
- Calculate skill demand as **percentage**
- Visualize top skills per job title using Seaborn

## 🛠 Technologies Used
- Python
- Pandas
- Matplotlib & Seaborn
- Jupyter Notebook

## 📁 Project Structure

View my notebook with detailed steps here:[2_Skill_Demand.ipynb](2__Project\2_Skill_Demand.ipynb)

### Visualize Data

```pythonimport seaborn as sns
import matplotlib.pyplot as plt

sns.set_theme(style='whitegrid')

fig, ax = plt.subplots(len(job_titles), 1, figsize=(14, 6 * len(job_titles)))

for i, job_title in enumerate(job_titles):
    df_plot = df_skill_perc[df_skill_perc['job_title_short'] == job_title].head(5).copy()
    
    # Sort so highest skill is at the top
    df_plot = df_plot.sort_values(by='skills_perc', ascending=True)
    
    sns.barplot(
        data=df_plot, 
        x='skills_perc', 
        y='job_skills', 
        ax=ax[i],
        palette='Blues_d',           # Clean dark-to-light blue
        hue='skills_perc',           # Color intensity based on percentage
        legend=False
    )

    ax[i].invert_yaxis()
    
    # Improve appearance
    ax[i].set_title(job_title, fontsize=13, pad=12)
    ax[i].set_ylabel('')
    ax[i].set_xlabel('Skill Percentage (%)' if i == len(job_titles)-1 else '')
    ax[i].set_xlim(0, 80)
    
    # Add percentage labels on the bars
    for container in ax[i].containers:
        ax[i].bar_label(container, fmt='%.1f%%', padding=5, fontsize=11)

    if i !=len(job_titles) - 1:
        ax[i].set_xticks([])    

fig.suptitle('Likelihood of Skills Requested in Canada Job Postings', 
             fontsize=18, y=0.98)
fig.tight_layout()
plt.show()
```Python

###  Results

![Visualization of top Skills for Data Nerds]
(2__Project\Images\Skill_Demand Oof_data_roles.png)

### Insights
## 📌 Key Insights

- **SQL** is the most demanded skill across all roles, especially ## 📌 Key Insights

- **SQL** is the most demanded skill across all roles, especially for Data Engineers (65–67%).
- **Python** is extremely important — nearly as critical as SQL for Data Engineers and Senior Data Engineers.
- **Data Analysts** rely heavily on **Excel, Tableau, and Power BI** in addition to SQL and Python.
- **Cloud skills** (AWS and Azure) are highly valued for Data Engineer roles, with AWS being particularly strong for Senior positions.
- **Big Data tools** like **Spark** show strong demand in Engineering roles (over 40% for Senior Data Engineers).

**Summary**: SQL and Python dominate the Canadian data job market, while cloud platforms and visualization tools are key differentiators by role.for Data Engineers (65–67%).
- **Python** is extremely important — nearly as critical as SQL for Data Engineers and Senior Data Engineers.
- **Data Analysts** rely heavily on **Excel, Tableau, and Power BI** in addition to SQL and Python.
- **Cloud skills** (AWS and Azure) are highly valued for Data Engineer roles, with AWS being particularly strong for Senior positions.
- **Big Data tools** like **Spark** show strong demand in Engineering roles (over 40% for Senior Data Engineers).

**Summary**: SQL and Python dominate the Canadian data job market, while cloud platforms and visualization tools are key differentiators by role.

