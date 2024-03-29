# pandas-challenge
Module 04 - Pandas Challenge

OVERVIEW: Analyze district-wide math and reading test scores using Pandas and Jupyter Notebook. Using the techniques learned in class, summarize the data to represent the positive and negative trends in each school's performance.
-
------------------------------------------------------------------------
District Summary
Perform the necessary calculations and then create a high-level snapshot of the district's key metrics in a DataFrame.

Include the following:

Total number of unique schools (Cell 6)
    -Used .nunique() to pull out each school name and count them.

Total students (Cell 7)
    -Used .unique() to count each unique student name.

Total budget (Cell 8)
    -Used .sum() in the original school_data.csv to add up the budget for each school.
    -I chose to pull the budgets from that original data set since every value was unique and did not require additional coding.

Average math score (Cell 9)
    -Calculated using .mean() in the merged data frame in the math_score column.

Average reading score (Cell 10)
    -Calculated using .mean() in the merged data frame in the reading_score column.

% passing math (the percentage of students who passed math) (Cell 11)
    -First set up a variable to store the .count() of math scores >=70, with 70 being the lowest possible score to pass.
    -Then calculated the percentage by dividing the number of passing scores by the total number of students, and multiplying by 100.

% passing reading (the percentage of students who passed reading) (Cell 12)
    -First set up a variable to store the .count() of reading scores >=70, with 70 being the lowest possible score to pass.
    -Then calculated the percentage by dividing the number of passing scores by the total number of students, and multiplying by 100.

% overall passing (the percentage of students who passed math AND reading) (Cell 13)
    -Added together the passing math and reading scores by concatenating them with "&".
    -Then calculated the percentage by dividing the number of passing scores by the total number of students, and multiplying by 100.
    

District Summary Analysis

The summary table created at the end of this section shows that there is a total budget of about $24.7 million in a school district that serves 15 different schools. There is a total of 39,170 students enrolled in this district. 

75% of these students passed math and 86% passed reading as standalone categories. The average scores of 78.9 in math and 81.8 in reading show that students are more adept at reading than math, but are on the lower end of passing in general.

65.2% of these students passed both math and reading, which suggests that approximately one third of the total students needs more academic help to pass math or reading.
-
------------------------------------------------------------------------
School Summary
Perform the necessary calculations and then create a DataFrame that summarizes key metrics about each school.

Include the following:

School name/School type
    -Found by setting the index to school_name and type.
        -Per instructor, used .reset_index().drop_duplicates() to list each school_name and its type only once.
    -Attempted to use .unique() but this did not work.

Total students
    -Performed a .value_counts() within the school_name column to obtain the total number of students per school.

Total school budget
    -Referenced the school_name and budget columns within the merged data frame and used .mean().

Per student budget
    -Using the value from the total per school budget (above), I was able to divide each school's budget by the number of students to find
        out the per student budget.

Average math score
    -Performed .groupby() to cross-reference each math score with its corresponding school, followed by .mean() in the same line to 
        average the scores per school.

Average reading score
    -Performed .groupby() to cross-reference each reading score with its corresponding school, followed by .mean() in the same line to 
        average the scores per school.

% passing math (the percentage of students who passed math)
    -Calculated the number of students who passed math (per school) in cell 19, then used this value in cell 22, divided by the total number 
        of students per school, and multiplied by 100.

% passing reading (the percentage of students who passed reading)
    -Calculated the number of students who passed reading (per school) in cell 20, then used this value in cell 22, divided by the total
            number of students per school, and multiplied by 100.
        
% overall passing (the percentage of students who passed math AND reading)
    -Calculated the number of students who passed both math and reading (per school) in cell 21, then used this value in cell 22, divided by
        the total number of students per school, and multiplied by 100.
        

School Summary Analysis
Attempted to create the "Per School Summary" data frame, but there is an issue with my school_types variable. Instructor ran out of time in 
    office hours helping me and another student with the same issue. We had experimented with a couple of different things to get the list
    of just school names with their type, and the only thing that worked was the .reset_index().drop_duplicates().
        
        
-
------------------------------------------------------------------------

Highest-Performing Schools (by % Overall Passing)
Sort the schools by % Overall Passing in descending order and display the top 5 rows.

Save the results in a DataFrame called "top_schools".
-
------------------------------------------------------------------------

Lowest-Performing Schools (by % Overall Passing)
Sort the schools by % Overall Passing in ascending order and display the top 5 rows.

Save the results in a DataFrame called "bottom_schools".
-
------------------------------------------------------------------------

Math Scores by Grade
Perform the necessary calculations to create a DataFrame that lists the average math score for students of each grade level (9th, 10th, 11th, 12th) at each school.
-
------------------------------------------------------------------------

Reading Scores by Grade
Create a DataFrame that lists the average reading score for students of each grade level (9th, 10th, 11th, 12th) at each school.
-
------------------------------------------------------------------------

Scores by School Spending
Create a table that breaks down school performance based on average spending ranges (per student).
Use the scores above to create a DataFrame called spending_summary.

Include the following metrics in the table:

Average math score

Average reading score

% passing math (the percentage of students who passed math)

% passing reading (the percentage of students who passed reading)

% overall passing (the percentage of students who passed math AND reading)
-
------------------------------------------------------------------------
Scores by School Size
Use the following code to bin the per_school_summary.

size_bins = [0, 1000, 2000, 5000]
labels = ["Small (<1000)", "Medium (1000-2000)", "Large (2000-5000)"]
Use pd.cut on the "Total Students" column of the per_school_summary DataFrame.

Create a DataFrame called size_summary that breaks down school performance based on school size (small, medium, or large).
-
------------------------------------------------------------------------
Scores by School Type
Use the per_school_summary DataFrame from the previous step to create a new DataFrame called type_summary.

This new DataFrame should show school performance based on the "School Type".