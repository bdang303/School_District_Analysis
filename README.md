# School_District_Analysis using Pandas

## Overview of the school district analysis:
Using various methods in Pandas, this python script was able to conduct an analysis on two CSV datasets containing information from 15 high schools, and testing scores from students within those schools. The high school data includes details such as school size & budget, and the student data set contained gender, grade level, as well as standardized test scores for each student. The analysis output was able to provide insights on the performance of each school within the district and trends associated with those performance levels. These insights were provided to decision makers to help determine appropriate funding & allocation in the future.

## Analysis Results
Upon learning that the 9th grade scores for students at Thomas High School had been altered, there were a number of items that were impacted after those scores were replaced with NaNs. 

### Using loc to replace dishonest test scores
The following script was used to replace the scores with NaN:

    student_data_df.loc[
    (student_data_df["school_name"] == "Thomas High School") &
    (student_data_df["grade"] == "9th") 
    , "reading_score"] = np.NaN

    student_data_df.loc[
    (student_data_df["school_name"] == "Thomas High School") &
    (student_data_df["grade"] == "9th") 
    , "math_score"] = np.NaN

* Below is an overall summary at the district level. Following these changes, there was < 1.0% decrease in percentage of students passing math, reading, and overall. The average math and reading scores were minimally impacted. 
    
    ![DISTRICT SUMMARY](https://github.com/bdang303/School_District_Analysis/blob/main/Resources/DistrictSummary.png)

* The replacement of scores results in a significant increase in % of Students passing reading at Thomas high school (+30%) and overall passing % (+25%)
* Prior to the replacement of scores, Thomas High School had a significantly lower overall % passing rate compared to other schools in the district. However, following the change, the school actually now has the second highest overall passing %

    ![SCHOOL SUMMARY](https://github.com/bdang303/School_District_Analysis/blob/main/Resources/SchoolSummaryScreenshot.png)

* How does replacing the ninth-grade scores affect the following:
** Math and reading scores by grade
*** Thomas High School had one of the highest average math & reading scores for students in 9th grade, so by replacing it the summary table no longer reflects average scores for Thomas High school at this grade.
o Scores by school spending
* Scores by school spending did not reflect any changes to results in the spending summary table. 
o Scores by school size
* Thomas High School fell into the ÒMediumÓ size school bin, however, the averages did not reflect any difference 
o Scores by school type
* As a charter school, the replacement of results did not reflect any impact to the results of charter schools

## Analysis Summary

In summary, there were a few main impacts after the results for 9th grade students at Thomas high School had their scores replaced. 1) % of students passing math increased by 26.3% 2) % of students passing reading increased by 27.4% 3) Overall % of students passing increased by 25.6% 4) Thomas High went from one of the schools with the lower overall passing rates to one of the schools with the highest overall passing rate.§ 
