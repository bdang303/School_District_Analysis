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

* How is the district summary affected?
o Below is an overall summary at the district level. Following these changes, there was < 1.0% decrease in percentage of students passing math, reading, and overall. The average math and reading scores were minimally impacted. 
o ![DISTRICT SUMMARY](URL)

* How is the school summary affected?
o The replacement of scores results in a significant increase in % of Students passing reading at Thomas high school (+30%) and overall passing % (+25%)
* How does replacing the ninth gradersÕ math and reading scores affect Thomas High SchoolÕs performance relative to the other schools?
o Prior to the replacement of scores, Thomas High School had a significantly lower overall % passing rate compared to other schools in the district. However, following the change, the school actually now has the second highest overall passing %
o ![SCHOOL SUMMARY](URL)
o 
* How does replacing the ninth-grade scores affect the following:
o Math and reading scores by grade
* Thomas High School had one of the highest average math & reading scores for students in 9th grade, so by replacing it the summary table no longer reflects average scores for Thomas High school at this grade.
o Scores by school spending
* Scores by school spending did not reflect any changes to results in the spending summary table. 
o Scores by school size
* Thomas High School fell into the ÒMediumÓ size school bin, however, the averages did not reflect any difference 
o Scores by school type
* As a charter school, the replacement of results did not reflect any impact to the results of charter schools

## Analysis Summary

In summary, there were a few main impacts after the results for 9th grade students at Thomas high School had their scores replaced. 1) % of students passing math increased by 26.3% 2) % of students passing reading increased by 27.4% 3) Overall % of students passing increased by 25.6% 4) Thomas High went from one of the schools with the lower overall passing rates to one of the schools with the highest overall passing rate.§ 

# Election Analysis using Python

## Overview of Election Analysis
A dataset of votes from a U.S. Congressional election in Colorado was provided that contained ballots for candidate votes in multiple counties. Using a python script to conduct an automated analysis, we were able to store the data elements from a CSV file using lists & dictionaries. The script allowed us to access the data and perform various calculations to determine the results of the election. In addition to the results, the script also summarized and reported out details via a text file.


### Purpose

##Election Audit Results
* How many votes were cast in this congressional election? In this election, there were a total of 369,711 votes cast
* Provide a breakdown of the number of votes and the percentage of total votes for each county in the precinct. There were 3 Counties where votes were tabulated, Denver had the majority of votes at 306,055 (82.8%), following by Jefferson County with 38,855 votes (10.5%), and Arapahoe County with 24,801 (6.7%). To calculate the number of votes, a ÒForÓ loop was created to retrieve the county votes for each county:

    for county_name in county_votes:
        cvotes = county_votes.get(county_name)

Using the following formula, we calculated the percentage of results:

        countyvote_percentage = float(cvotes) / float(total_votes) * 100
        county_results = (
            f"{county_name}: {countyvote_percentage:.1f}% ({cvotes:,})\n")


* Which county had the largest number of votes? Per the breakdown above, Denver had the largest County turnout in this election. 
* Provide a breakdown of the number of votes and the percentage of the total votes each candidate received. 3 Candidates were in the running in this election. Diana DeGette had 272,892 votes, followed by Charles Casper Stockham with 85,213 votes, and Raymon Anthony Doane with 11,606 votes.
* Which candidate won the election, what was their vote count, and what was their percentage of the total votes? Diana DeGette was the candidate who received the most votes with 272,892 votes which was 73.8% of the total votes and therefore the winner of the election.

![Election Summary]( https://github.com/bdang303/Election_Analysis/blob/main/Resources/Election_Summary.png)


##Election Audit Summary
The python script that was created to automate the election audit and results could definitely be utilized by the election commission for other elections. Not only can the base of this script be used for county elections, it can be modified to be used for local elections at the city level (ex. Mayor Elections). To do so, we can create separate lists & dictionaries to do this. In addition, if there were other positions or seats within an election, and that data was available via a separate column in the CSV file, we can modify the scrip to report out the winner of each position or seat. 

