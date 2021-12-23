# School_District_Analysis
## Overview
This analysis conducts an in-depth look at the reading and math scores from across District and Charter schools in Py City. The scores come from students in 9th - 12th grade taking standardized reading and math tests.

### Purpose
This analysis aims to find trends in the scores from different schools in Py City. We find the average math and reading scores for each school, as well as the average scores grouped by grade in each school. We also find the average percentage of students passing math, students passing reading, and students passing both math and reading, from each school, across schools grouped by size, and across Charter and District schools. 

The analysis was conducted twice to account for suspected academic dishonety among the 9th graders at Thomas High School. The second analysis removes all Thomas High School 9th graders from the scores. 

## Results

### Overall Analysis
Our analysis found that the top five schools for math and reading test scores were all Charter schools, with Cabrera High School coming in as the top school. 
![Top Schools Table]()

We also found that Small and Medium schools had very similar scores, while Large schools had significantly lower scores, with less than 60% of students passing both math and reading.
![Scores by School Size]()

We also created a DataFrame storing the average math and reading scores by grade for each school. Please see the code file for the full DataFrame
Math:
```
ninth_grade_math_scores = ninth_graders.groupby(["school_name"]).mean()["math_score"]

tenth_grade_math_scores = tenth_graders.groupby(["school_name"]).mean()["math_score"]

eleventh_grade_math_scores = eleventh_graders.groupby(["school_name"]).mean()["math_score"]

twelfth_grade_math_scores = twelfth_graders.groupby(["school_name"]).mean()["math_score"]

math_scores_by_grade = pd.DataFrame({
               "9th": ninth_grade_math_scores,
               "10th": tenth_grade_math_scores,
               "11th": eleventh_grade_math_scores,
               "12th": twelfth_grade_math_scores})
```
Reading:
```
ninth_grade_reading_scores = ninth_graders.groupby(["school_name"]).mean()["reading_score"]

tenth_grade_reading_scores = tenth_graders.groupby(["school_name"]).mean()["reading_score"]

eleventh_grade_reading_scores = eleventh_graders.groupby(["school_name"]).mean()["reading_score"]

twelfth_grade_reading_scores = twelfth_graders.groupby(["school_name"]).mean()["reading_score"]
reading_scores_by_grade = pd.DataFrame({
              "9th": ninth_grade_reading_scores,
              "10th": tenth_grade_reading_scores,
              "11th": eleventh_grade_reading_scores,
              "12th": twelfth_grade_reading_scores})
```

### Analysis without Thomas High School 9th Graders
Removing the results of the 9th graders from Thomas High School did cause small changes in the overall scores. However the changes were less than 1% across all categories. This did not change Thomas High School's overall rank in the Top 5 Schools. 
![Top Scores Adjusted for THS]()

## Summary
Our analysis found the average math and reading test scores for each school, as well as each grade in each school. We found that the Top 5 Schools in Py City were all Charter schools. (Congrats Cabrera High School for coming out on top!) We also organized the scores by school size and found that Large schools had an alarmingly low percentage of students passing both math and reading tests. Small and Medium schools both had about 90% of students passing both tests. For more details on the test scores, please see Analyzing_Reading_and_Math_Scores().