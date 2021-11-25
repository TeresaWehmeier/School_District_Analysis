# School District Analysis

## Overview of the School District Analysis Project
The purpose of the School District Analysis project is to develop student and school performance analysis on reading and math scores, and to evaluate performance based on school size and budget level by high school and per student. Deliverables for the project include:
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

## Process
1. Before digging into the high level reports, it is important to remove test score results to address the academic dishonesty concerns. This process is performed using the .loc method, and identifies the specific high school and grade levels in question. Both the math and reading scores are set to NaN using this code:
 - student_data_df.loc[(student_data_df['school_name']=='Thomas High School') & (student_data_df['grade']=='9th'),['reading_score']]= np.nan
 - To verifiy the scores are removed, a sum of "isnull()" results is peformed with the results shown here:

    <img src = "Images/isnull_scores_new.png" width="30%" height="10%">
    
 2. The second step is to determine the average scores for both math and reading by high school.  


   

