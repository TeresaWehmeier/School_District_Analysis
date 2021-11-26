# School District Analysis

## Overview of the School District Analysis Project
The purpose of the School District Analysis project is to develop student and school performance analyses on reading and math scores, and to evaluate performance based on school size and budget level by high school and per student. Deliverables for the project include:
- High level snapshot of the district's key metrics
- Overview of the key metrics for each school
- Tables include
  - Top 5 and bottom 5 performing schools based on overall passing rates
  - Average math and reading scores by students in each grade level at each high school
  - School performance based on budget per student
  - School performance based on school size
  - School performance based on type of school

During development of the analysis, the district manager was informed by the school board of possible academic dishonesty from one of the high schools in the district. To uphold state-testing standards, the student scores in question were converted to null values (NaN - not a number), which required recompiling the anaylsis. As part of the project, the data deliverables were adjusted, and comparisons between the two results provided to determine how the changes affect the overall analysis.

## Resources
Resources include
- Clean data CSV files for analysis located <a href="https://github.com/TeresaWehmeier/School_District_Analysis/tree/main/Resources" target="_blank">in the resources folder.</a>
- Jupyter notebook
- Pandas libraries

## Results
### Impact on Thomas High School
Before digging into the high level reports, it is important to remove test score results to address the academic dishonesty concerns. This process is performed using the .loc method, and identifies the specific high school and grade levels in question. Both the math and reading scores are set to NaN using this code:

```
        student_data_df.loc[(student_data_df['school_name']=='Thomas High School')
        & (student_data_df['grade']=='9th'),['subject_score']]= np.nan
```
 - To verifiy the scores are removed, a sum of "isnull()" is performed with the results shown here:

    <img src = "Images/isnull_scores_new.png" width="30%" height="10%">
    
The next step is to re-establish the average scores for both math and reading by high school, and recompile the summary by high school report. Overall passing rates for Thomas High School decline from 90.9% to 90.6%, or less than half a percent, as a result of the modifications made to the school test results. Average math scores for the same high school decline from 83.4 to 83.35, or less than .05 of a point, while average reading scores _increase_ from 83.8 to 83.9.

Based on the high school summary report, overall percentage passing rates and average math and reading scores, revisions to Thomas High School show a minimal impact to their overall results. The revised high school summary report is pictured here:

<img src = "Images/summary_by_school_new.png" width="70%" height="50%">

### Impact on Comparative Results
The top five and bottom five performing schools were identified in the original analysis, and Thomas High School remains in the top five, even after modifications to the test scores. In fact, the high school's position remained at second position, and has no affect on the other top five performers.

1. Original Top Five Performance Results

  <img src = "Images/top_five_schools_old.png" width="60%" height="40%">

2. Revised top Five Performance Results

  <img src = "Images/top_five_schools.png" width="60%" height="40%">

3. Bottom Five Performance Results (no change after revision)

<img src = "Images/bottom_five_schools.png" width="60%" height="40%">

4. Average math and reading scores by grade level and high school were also compiled, with the only change in the new analysis that of the 9th grade results for Thomas High School set to NaN. Both math and reading were compiled, with only math shown here.

<img src = "Images/math_results_groupby_hs_grade_level.png" width="60%" height="40%">

### High Level Summaries
#### Spending Ranges Per Student
Spending ranges were developed to determine math, reading and overall performance based on budget per student. In the initial report, the spending per student bins are defined as <$585, $585-629, $630-644, and $645-675. These results are based on descriptive statistics, with some minor adjustment to more evenly balance the high school distribution in the bins. Once the changes are made, and the spending ranges per student are recompiled, there is no difference in performance based on spending per student. Thomas High School falls into the $630-644 spending bin, where none of the metrics are impacted by the data changes. 

1. Spending Ranges Per Student Report - Recompiled (no change)

<img src = "Images/summary_spending_new.png" width="40%" height="%20%>
                                                                 
                                                                 

