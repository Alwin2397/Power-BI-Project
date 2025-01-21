# Power-BI-Project-
This project aims to analyze and visualize survey responses from 630 data professionals, focusing on self-improvement and practice in data analysis and visualization.
# Data Professional Survey Analysis: A Power BI Project

## Overview
This project analyzes a survey dataset of 630 data professionals to uncover insights about career trends, job satisfaction, salary distribution, and technical preferences. Designed for self-improvement and practice, this project demonstrates data cleaning, transformation, and visualization skills using Power BI.

## Objectives
- Enhance data analysis and visualization skills.
- Explore key trends and insights in the data profession.
- Practice storytelling through interactive dashboards.

## Dataset Details
The dataset comprises responses from 630 professionals across various roles in the data industry. Key fields include:

- **Demographics**: Country, age, gender, and ethnicity.
- **Career Information**: Job roles, career transitions, and industry.
- **Salary Data**: Annual salaries categorized by roles and countries.
- **Job Satisfaction**: Ratings on salary, work-life balance, management, and learning opportunities.
- **Technical Preferences**: Favorite programming languages and perceived difficulty of entering the field.

## Key Insights
1. **Demographics**:
   - Geographic distribution of respondents.
   - Age and gender breakdown.
2. **Salary Trends**:
   - Average salary across countries and job roles.
   - Insights into salary satisfaction.
3. **Job Satisfaction**:
   - Work-life balance and management ratings.
   - Factors influencing job changes.
4. **Programming Preferences**:
   - Most popular programming languages.
   - Importance of technical skills in career transitions.

## Features
- **Data Cleaning**: Removed irrelevant fields and transformed raw data for analysis.
- **Interactive Dashboards**: 
  - Visualizations of salary trends, job satisfaction, and demographics.
  - Filters to explore data by specific roles, countries, or preferences.
- **Power BI Techniques**:
  - Data modeling and relationship management.
  - DAX calculations for deriving metrics and insights.

## Tools Used
- **Power BI**: For data cleaning, modeling, and dashboard creation.
- **Microsoft Excel**: Preliminary data examination and formatting.

## Technical Process

### Data Cleaning
1. **Removed Duplicates**:
   - Identified and removed duplicate entries using Power Query.
   ```M
   Table.Distinct(#"PreviousStep")
   ```
2. **Renamed Columns**:
   - Ensured consistent naming conventions for easier reference.
   ```M
   Table.RenameColumns(#"PreviousStep", {"Q1 - Which Title Best Fits your Current Role?", "Role"})
   ```
3. **Replaced Nulls**:
   - Filled missing values with placeholders or averages where applicable.
   ```M
   Table.ReplaceValue(#"PreviousStep", null, "Unknown", Replacer.ReplaceValue, {"Country"})
   ```

### DAX Formulas
1. **Calculated Measures**:
   - Average Salary:
     ```DAX
     AverageSalary = AVERAGE(Survey[Current Yearly Salary (in USD)])
     ```
   - Job Satisfaction Score:
     ```DAX
     JobSatisfaction = AVERAGE(Survey[Q6 - How Happy are you in your Current Position with the following? (Salary)])
     ```
2. **Dynamic Filters**:
   - Created slicers for country and role filtering.

3. **Custom Columns**:
   - Age Groups:
     ```DAX
     AgeGroup = 
     SWITCH(
         TRUE(),
         Survey[Current Age] <= 25, "18-25",
         Survey[Current Age] <= 35, "26-35",
         Survey[Current Age] <= 50, "36-50",
         "50+"
     )
     ```

### Visualizations
- **Bar Charts**:
  - Used for visualizing salary comparisons and role distributions.
- **Heatmaps**:
  - Highlighted regions with the highest job satisfaction.
- **Pie Charts**:
  - Displayed gender and age-group distributions.

## How to Use
1. Clone this repository.
2. Open the `.pbix` file in Power BI Desktop.
3. Explore the interactive dashboards to analyze insights.

## Dashboard Preview
- **Demographics Overview**: Visualizes respondent distribution by country, age, and gender.
- **Salary Analysis**: Compares average salaries by country, role, and satisfaction.
- **Job Satisfaction**: Highlights key satisfaction metrics and areas for improvement.
- **Programming Trends**: Displays the most favored programming languages.

## Learning Outcomes
Through this project, I have enhanced my understanding of:
- Data cleaning and preparation for visualization.
- Storytelling with data through meaningful visualizations.
- Leveraging Power BI's advanced features for analysis.

## Future Improvements
- Incorporate additional datasets for comparison.
- Expand analysis to include longitudinal trends.
- Add predictive modeling for career transitions.

---

Feel free to explore the repository and provide feedback to help me improve!
