# The Analysis
## What is the most optimal skill to learn for data Analysis?

### Visualize Data
```python
from adjustText import adjust_text

# Step 1 - Create plot
df_DE_skills_high_demand.plot(kind='scatter', x='skill_percent', y='median_salary', figsize=(10, 6))

# Step 2 - Add skill name labels ✅
texts = []
for i, txt in enumerate(df_DE_skills_high_demand.index):
    texts.append(plt.text(
        df_DE_skills_high_demand
    ['skill_percent'].iloc[i],
        df_DE_skills_high_demand
    ['median_salary'].iloc[i],
        txt  # ← this is the skill name e.g. 'python', 'sql'
    ))

# Step 3 - Prevent overlapping
adjust_text(texts, arrowprops=dict(arrowstyle='->', color='gray', lw=1.5))

# Step 4 - Labels and title
plt.xlabel('Percent of DE Jobs')
plt.ylabel('Median Yearly Salary')
plt.title('Most Optimal Skills for Data Engineers in the Canada')

from matplotlib.ticker import PercentFormatter
ax = plt.gca()
ax.yaxis.set_major_formatter(plt.FuncFormatter(lambda y, pos: f'${int(y/1000)}K'))
ax.xaxis.set_major_formatter(PercentFormatter(decimals=0))

plt.tight_layout()
plt.show()

```python


![Most Optimal Skills for Data Engineers in Canada](2__Project\Images\Optimal Skills.ipynb)
* A scatter plot visualizing the most optimal skills (high paying & high demand) for data analysts in the US.*

#### Key Insights

📊 Most Optimal Skills for Data Engineers in Canada

Optimal = high salary AND high demand

🏆 Key Findings
Best of both worlds (high pay + high demand):

AWS stands out the most — appearing in ~52% of job postings with a median salary of ~$125K, making it the single most valuable skill to have
Snowflake and Redshift offer strong salaries (~$125-130K) at moderate demand (25-30%), signaling cloud data warehousing is highly valued
SQL and Python dominate demand (65-70% of jobs) but at relatively lower salaries (~$100K) — they're essential but not differentiating

High pay, low demand (niche/specialist skills):

SAS and Excel top the salary chart (~$148K) but appear in under 5% of jobs — rare but lucrative
BigQuery, Git, and Databricks pay well (~$125-130K) at low-moderate demand

High demand, moderate pay:

Python and SQL are in nearly 70% of postings but median salary sits around $100K — table stakes skills every DE needs

###### Summary
💡 Takeaway for aspiring Data Engineers in Canada

Master SQL + Python as your foundation, then specialize in AWS + Snowflake to maximize both employability and earning potential.