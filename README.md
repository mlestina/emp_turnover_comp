
# Employee Turnover Competition from DataCamp
### Can I help reduce Employee Turnover at your company?

### link = https://app.datacamp.com/learn/competitions/reducing-employee-turnover
### my submission = https://app.datacamp.com/workspace/w/76aca967-77d6-4437-bd78-3fff828c6905

## Background
### I (hypothetically) work for the human capital department of a large corporation. The Board is worried about the relatively high turnover, and my job is to look into ways to reduce the number of employees leaving the company. The team needs to understand better the situation, which employees are more likely to leave, and why. Once it is clear what variables impact employee churn, I must then present my findings along with my ideas on how to attack the problem.

## The Challenge:
### I must create a report that covers the following:
### Part I:  Which department has the highest employee turnover? Which one has the lowest?
### Part II:  Investigate which variables seem to be better predictors of employee departure.
### Part III:  What recommendations would I make regarding ways to reduce employee turnover?

## My Submission

### First I will import modules, read in data, and then print the first few rows of data:
department | promoted | review | projects | salary | tenure | satisfaction | bonus | avg_hrs | left
--- | --- | --- | --- | --- | --- | --- | --- | --- | ---
operations | 0 | 0.5775 | 3 | low | 5.0 | 0.6268 | 0 | 180.8666 | no
operations | 0 | 0.7519 | 3 | medium | 6.0 | 0.4437 | 0 | 182.7081 | no
support | 0 | 0.7225 | 3 | medium | 6.0 | 0.4468 | 0 | 184.4160 | no
logistics | 0 | 0.6752 | 4 | high | 8.0 | 0.4401 | 0 | 188.7075 | no
sales | 0 | 0.6762 | 3 | high | 5.0 | 0.5776 | 1 | 179.8211 | no


### As can be seen above, each row represents an employee, the 'left' column indicates whether or not the employee separated or left the company, and the other rows show the department of the employee, performace appraisal, employee satisfaction, salary range, whether the employee was recently promoted, average hours worked per month, number of projects employee is working on, years of service, and whether the employee received a bonus.

### In this project, I will illustrate how employee turnover is correlated with each of these employee attributes

# Part I: Which Department had the most and least turnover?
### First I will plot a barchart of turnover rate for each department

![image](https://user-images.githubusercontent.com/28972117/159268872-47f4c1df-23bd-46ed-b31e-7abfdeaff133.png)

### As can be seen from the above, it is a very tight race with very little variance between Departments. We will have to break the tie by actually calculating the turnover rate for each department and looking at the results. I will therefore print out the turnover rate for each department using a 'groupby' and value counting the 'left' column

## Calculation of Turnover for each Department:


Department | Turnover
--- | ---
IT | 0.308989
Admin | 0.281324
Engineering | 0.288259
Finance | 0.268657
Logistics | 0.308333
Marketing | 0.302993
Operations | 0.286465
Retail | 0.305646
Sales | 0.285183
Support | 0.288435

# Part II: Investigate which variables seem to be better predictors of employee departure
### I will now investigate the relationship between each remaining variable versus turnover. For each variable, I will first calculate mean, and then plot the data and discuss results

## 1. Employee Performance Reviews
### I will now investigate the relation between employee performance ratings and employee turnover

Separated | Performance Rating
--- | ---
No | 0.6352
Yes | 0.6923

![image](https://user-images.githubusercontent.com/28972117/159269316-0016147e-2ee8-4cd1-815c-050d9d1baa8d.png)

### Both the calculated numbers and the violin plot seem to show that employees that receive a high performance rating are more apt to leave the company than those in the middle of the curve.

## 2. Recent Promotions
### Lets now see whether an employee was recently promoted has an influence on whether the employee stays or leaves the company
Separated | Fraction Recently Promoted
--- | ---
No | 0.0343
Yes | 0.0205

![image](https://user-images.githubusercontent.com/28972117/159269519-c3eb86a2-e85e-40fa-9e0d-ee4cb33caee4.png)

### It appears that Promotions are a very big predictor of whether an employee will leave the company. If an employee has not been recently promoted, that employee is much more apt to leave the company than one who has been promoted.

## 3. Number of Projects employee is involved in
### Lets look at the relationship between number of projects an employee is working on versus whether they leave the company
Separated | Num of Projects
--- | ---
No | 3.2795
Yes | 3.2626

![image](https://user-images.githubusercontent.com/28972117/159269619-d08fa7ed-173c-40a0-831f-32c65ecd178c.png)

### Both the calculated values and the bar chart seem to say that the turnover rate of employees does not vary much with regard to the number of projects an employee is involved in.

## 4. Tenure -- Years of Service
### Lets now calculate the average seniority for separated vs retained emplouees:
Separated | Years of Service
--- | ---
No | 6.5455
Yes | 6.5794

![image](https://user-images.githubusercontent.com/28972117/159269762-1b4c9caa-1c1b-4375-a930-e65ba9beecb9.png)

### The boxplot tells a slightly different picture. It appears that employees in the 7-8 year of seniority are most likely to separate, those around 6 years are least likely to separate, and those with 10 years or so are also less likely to separate. So it appears that turnover does vary with seniority to at least a mild extent.

## 5. Employee Satisfaction
### Lets now calculate employee satisfaction ratings for separated and retained employees
Separated | Employee Satisfaction
--- | ---
No | 0.5056
Yes | 0.5022

![image](https://user-images.githubusercontent.com/28972117/159269868-72ca131a-5e6f-4fb6-8eb8-e0335c565e44.png)

### The violin plot seems to show that the very satisfied and the least satisfied are most apt to want to leave the company, while the ones in the middle are most apt to stay.

##6 Bonus
Separated | Received Bonus
--- | ---
No | 0.2151
Yes | 0.2047
### We will now look at how employee turnover varies according to whether an employee receives a bonus. Data and barchart show fraction receiving a bonus. Again, left = 'yes' indicates separation, left = 'no' indicates retention

![image](https://user-images.githubusercontent.com/28972117/159270024-63213ffa-a749-4e1a-8a56-02380f6f974f.png)

### It appears from both the bar chart and the calculated numbers that whether or not an employee receives a bonus has little bearing on whether that employee is likely to leave.

## 7. Average Hours per Month:
### Lets now calculate mean average hours per month of retained employees (i.e. left = 'no') and separated employees (i.e.left = 'yes')
Separated | Avg Hours/Month
--- | ---
No | 184.6376
Yes | 184.7197

![image](https://user-images.githubusercontent.com/28972117/159270142-8f9a8b15-24de-4f9d-94aa-79c7b0d8fae3.png)

### The violin plot show much more. Employees that worked a lot of hours (i.e. 190) are much more likely to separate and employees working less hours (i.e. 180) are least likely to separate. But because a few workers who work extreme hours (near 200) did not leave, these outliers result in equal means.

## 8. Salary
### I will now calculate and produce employee turnover rate (i.e. 'left') according to salary (i.e. high, medium and low)
Separated | Salary | Turnover
--- | --- | ---
No | High | 0.7145
Yes | High | 0.2855
No | Medium | 0.7049
Yes | Medium | 0.2951
No | Low | 0.7169
Yes | Low | 0.2831

![image](https://user-images.githubusercontent.com/28972117/159270250-4b17beaa-44d3-4c31-9f38-b0d80985be92.png)

### It appears from the above that employee turnover rates does not vary much by salary.

# Part III: My Recommendations to reduce turnover
## Since failing to get promoted seems to be the biggest predictor of employee turnover, and since many who leave are high achievers with high monthly hours worked and high reviews by superiors, my recommendation to prevent turnover would be to fix the promotion system so that so many high achievers dont get overlooked. This could be achieved by promoting more high end achievers, eliminating promotions of lower end achievers, or provide some other benefits to high end achievers so that they do not want to leave the company.



