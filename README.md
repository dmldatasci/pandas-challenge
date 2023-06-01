# standardized-test-performace-analysis
This project is an analysis of district-wide standardized test results provided by the government of a small city. We were given access to every student's math and reading scores, as well as various information on all schools in the district.

## Procedure

### District Summary
Perform the necessary calculations and then create a high-level snapshot of the district's key metrics in a DataFrame.

Elements:
- Total number of unique schools
- Total students
- Total budget
- Average math score
- Average reading score
- % passing math (the percentage of students who passed math)
- % passing reading (the percentage of students who passed reading)
- % overall passing (the percentage of students who passed math AND reading)

![District Summary](/images/district_summary.png)

### School Summary
Perform the necessary calculations and then create a DataFrame that summarizes key metrics about each school.

Elements:
- School name
- School type
- Total students
- Total school budget
- Per student budget
- Average math score
- Average reading score
- % passing math (the percentage of students who passed math)
- % passing reading (the percentage of students who passed reading)
- % overall passing (the percentage of students who passed math AND reading)

![School Summary](/images/school_summary.png)

### Highest-Performing Schools (by % Overall Passing)
Sort the schools by `% Overall Passing` in descending order and display the top 5 rows.

Save the results in a DataFrame called "top_schools".

![Top Schools](/images/top_schools.png)

### Lowest-Performing Schools (by % Overall Passing)
Sort the schools by `% Overall Passing` in ascending order and display the top 5 rows.

Save the results in a DataFrame called "bottom_schools".

![Bottom Schools](/images/bottom_schools.png)

### Math Scores by Grade
Perform the necessary calculations to create a DataFrame that lists the average math score for students of each grade level (9th, 10th, 11th, 12th) at each school.

![Math Scores by Grade](/images/math.png)

### Reading Scores by Grade
Create a DataFrame that lists the average reading score for students of each grade level (9th, 10th, 11th, 12th) at each school.

![Reading Scores by Grade](/images/reading.png)

### Scores by School Spending
Create a table that breaks down school performance based on average spending ranges (per student).

Create four bins with reasonable cutoff values to group school spending as follows:

    spending_bins = [0, 585, 630, 645, 680]
    labels = ["<$585", "$585-630", "$630-645", "$645-680"]

Use `pd.cut` to categorize spending based on the bins.

Calculate mean scores per spending range as follows:

    spending_math_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"])["Average Math Score"].mean()
    spending_reading_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"])["Average Reading Score"].mean()
    spending_passing_math = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Passing Math"].mean()
    spending_passing_reading = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Passing Reading"].mean()
    overall_passing_spending = school_spending_df.groupby(["Spending Ranges (Per Student)"])["% Overall Passing"].mean()

Use the scores referenced above to create a DataFrame called `spending_summary`.

Elements:
- Average math score
- Average reading score
- % passing math (the percentage of students who passed math)
- % passing reading (the percentage of students who passed reading)
- % overall passing (the percentage of students who passed math AND reading)

![Scores by School Spending](/images/spending.png)

### Scores by School Size
Bin the `per_school_summary` as follows:

    size_bins = [0, 1000, 2000, 5000]
    labels = ["Small (<1000)", "Medium (1000-2000)", "Large (2000-5000)"]

Use `pd.cut` on the "Total Students" column of the `per_school_summary` DataFrame.

Create a DataFrame called `size_summary` that breaks down school performance based on school size (small, medium, or large).

![Scores by School Size](/images/size.png)

### Scores by School Type
Use the `per_school_summary` DataFrame from the previous step to create a new DataFrame called `type_summary`.

This new DataFrame shows school performance based on the "School Type".

![Scores by School Type](/images/type.png)