# Power-BI-Projects

# pwc Call Centre Dashboard


## Problem Statement

This dashboard helps to visualize pwc call center trends. That helps to analysis overall Performance of each agent, answered and abandoned call, resolved and unresolved issues. Additionally having a customer satisfaction rating will analysis the agent Performance.

## Datasource :

Dataset used for this task was presented by [Pwc](https://www.pwc.ch/en/careers-with-pwc/students/virtual-case-experience.html) and call centre trends dataset:

Dataset: [Call Centre Trends](https://github.com/yogeshkasar778/PWC_task-Call_Centre_trends-dashboard/blob/main/01%20Call-Center-Dataset.xlsx)

## Data Preparation:
Dataset loaded into Microsoft Power BI Desktop and start the data transformation using Power Query.

Dataset Structure:

- `Call Center trends dataset` which has `10 columns and 5000 rows` of observation

Data Cleaning for the dataset was done in the power query editor as follows:

- Removed Unnecessary columns
- Removed Unnecessary rows
- Data type validation for each column

## Data Modeling:

## Data Analysis (DAX):

Measures used in  all visualization are:

- Agent Rank = RANKX(ALLSELECTED(Sheet1[Agent]), [Total Calls])
- AnsweredCall = CALCULATE(COUNT(Sheet1[Answered (Y/N)]), Sheet1[Answered (Y/N)]= "Y")
- Month = FORMAT(Sheet1[Date], "MMMM")
- MonthNum = MONTH(Sheet1[Date])
- ResolvedIssue = CALCULATE(COUNT(Sheet1[Resolved]), Sheet1[Resolved]= "Y")
- Top Performer = 
    VAR TopAgent = TOPN(1, ALL(Sheet1), [Total Calls], DESC)
    VAR TopAgentName = MAXX(TopAgent,Sheet1[Agent])
  RETURN
    TopAgentName
- Total Calls = COUNT(Sheet1[Call Id])
  
## Data Visualization (Dashboard) :

Data visualization for the data analysis (DAX) was done in Microsoft Power BI Desktop:

Shows visualizations from Call Center Trends :

| Call Centre Dashboard - Overview |
| ----------- |
|![Overview_Pwc_callcenter](https://github.com/user-attachments/assets/b8224d4f-cb9b-4afc-a696-2f59ed435727)

| Call Centre Dashboard - Agent's Analysis |
| ----------- |
![AgentAnalysis_Pwc_callcenter](https://github.com/user-attachments/assets/857b6cd0-50fa-4ad0-ba34-019b5b5e11b2)

## Insights from Data Visualization :

Key Points:
- Top Performer based on Call count - Steward
- Average Satisfaction rating is 3.4
- Most calls for streaming issue, then technical support and payment related and others.
- The top call counts in January decreased in February and March, indicating that the issue has been reduced.
---
