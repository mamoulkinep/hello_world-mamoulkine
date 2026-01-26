# 2012 SAT Results - https://data.cityofnewyork.us/Education/2012-SAT-Results/f9bf-2cp4/data_preview

# edstem workspace link: [https://edstem.org/us/courses/91931/workspaces/pyrPXkGC6Ul2skYNCUG1jN6zNxZ89x4M](https://edstem.org/us/courses/91931/workspaces/pc8xTjScwTaAf50pqAdVqVLAuqRw4ZLw)

## Why I Chose This Dataset : 
I chose this dataset because it's local (NYC) and the data structure is straightforward. Each row corresponds to one school and each column describes an attribute of that school's SAT results e.g. number of test takers. The dataset is large enough and not too large like some other datasets on the website, and fits all of the criteria for this assignment.



# Three Data Questions :
### Question 1: How many schools have more than 100 SAT test takers?

over100count = (pd.to_numeric(df["Num of SAT Test Takers"], errors="coerce") > 100).sum()  
print(over100count) #output: 100

This works because the dataset is tabular where each row represents one school, and the "Num of SAT Test Takers" column contains a numeric value which corresponds to a school. We can count all schools where this column contains a value greater than 100.

### Question 2: How many schools have an average SAT Math score above 500?

over500count = (pd.to_numeric(df["SAT Math Avg. Score"], errors ="coerce") > 500).sum()  
print(over500count) #output: 34

This works because the dataset is tabular and each row represents one school, therefore we can count each school where "SAT Math Avg. Score" contains a value greater than 500.

### Question 3: How many schools have more than 100 SAT test takers and an average SAT Math score above 500?

over100_over500 = ((pd.to_numeric(df["Num of SAT Test Takers"], errors="coerce") > 100) &  
(pd.to_numeric(df["SAT Math Avg. Score"], errors ="coerce") > 500)).sum()  
print(over100_over500) #output: 25

This works because the dataset contains multiple attributes for each school, making it possible to answer a two-condition question where we count schools that satisfy two requirements : "SAT Math Avg. Score" contains a value greater than 500 AND "Num of SAT Test Takers" contains a value greater than 100.

## What the data cannot answer

We might want to know which individual student has the highest overall SAT score, however this dataset does not provide student-level data. Therefore, we cannot determine which individual student achieved the highest overall SAT scores, as we are only provided with school-wide averages that include many students. It would be misleading to assume that the school with the highest average SAT score also contains the single highest-scoring individual student.
