Lab 3 Part 1

6/21/2023

Overview: write a .do file which imports transplants.dta and performs the data management/ exploratory data analysis tasks described below using the slides we have discussed in class. Your .do file must be called lab3\_*yourname*.do and must create a log file called lab3\_*yourname*.log. This file will contain your answers for both part 1 and part 2 of today's lab. Your .do file should follow conventions for .do file structure described in class. Do not submit your log files as part of the assignment. 

Evaluation: Evaluation will be based on the log file produced by your script. 

At the start of your answer to each question, leave a blank line and then a comment indicating the question number, like this:

//QUESTION 1

Tasks:

1. Perform a chi2 test to test the association between recipient work-status (rec\_work) and gender (gender). Using conditional if and else statements, make Stata print:

Question 1: Working for income is associated with gender, p = x.xxx

If the p-value is less than 0.05, or make Stata print: 

Question 1: Working for income is NOT associated with gender, p=x.xx

If the p-value is greater than 0.05.

**Question 1: working for income is associated w gender, p=0.002**

2. From lab 2: Create a variable called hypertensive which is 1 for transplant recipients who have ESRD secondary to hypertension (dx==4) and 0 for everyone else. Create another variable called college which is 1 for recipients with any college, an associate's/bachelor's degree or a graduate degree and 0 for recipients who have no education, grade school education, or high school/GED.  Create a variable called male which is 1 for male recipients and 0 for female recipients. 

Run a logistic regression of hypertensive on age, BMI, college, and male gender (logistic hypertensive age bmi college male). 

Write a program called table\_loop that is an updated version of your program called table\_q6 from Lab 2. table\_loop should use a foreach loop to create the display of odds ratios, like this: 

Regression table (Question 2)

age        x.xx (x.xx - x.xx)

bmi        x.xx (x.xx - x.xx)

college    x.xx (x.xx - x.xx)

male       x.xx (x.xx - x.xx)

except fill in the correct numbers.

**age           1.01  (1.00-1.02)**

**bmi           1.02  (1.00-1.04)**

**college       0.91  (0.72-1.14)**

**male          1.21  (0.96-1.53)**

**OR**

**age           1.01  (1.00-1.02)**

**bmi           1.02  (1.00-1.04)**

**college       0.81  (0.60-1.08)**

**male          1.21  (0.95-1.53)**

**Check that script uses a loop**

Lab 3 Part 2

3. Write a program called table\_varlist that is an updated version of table\_loop from question 2. table\_varlist should incorporate syntax varlist and a foreach loop to create the display of odds ratios. So if we run table\_varlist age male bmi college we should get the following table:

Regression table (Question 3)

age        x.xx (x.xx - x.xx)

male       x.xx (x.xx - x.xx)

bmi        x.xx (x.xx - x.xx)

college    x.xx (x.xx - x.xx)

**See above. Make sure vars aren't hard-coded in the program**

except fill in the correct numbers.

4 . Create a variable called tall that is 1 if the recipient’s height (rec\_hgt\_cm) is greater than or equal to the 75th percentile of height of all recipients in the dataset. (Hint: how can you use summarize and macros to generate a variable based on the mean of another variable?) tall should be equal to 0 for recipients with height less than the overall 75th percentile for height. Create a variable called white that is 1 if the recipient is white and 0 for all other races. Create a variable called age\_10y which is age in decades (age/10). You will need to create variable labels for new variables tall, white, and age\_10y, and you can change existing variable labels to improve readability of the table as well. 

Run a logistic regression of tall on age, weight (rec\_wgt\_kg), gender, and white race (logistic tall age rec\_wgt\_kg gender white)

Use putexcel to create a table in Excel that displays the odds ratios:

|**Variable**|**OR**|**95% CI**|
| :- | :- | :- |
|**Age (per 10y)**|**0.93**|**0.85-1.01**|
|**Weight in kg**|**1.06**|**1.05-1.07**|
|**Female Gender**|**0.05**|**0.03-0.08**|
|**White vs Non-white**|**1.57**|**1.22-2.02**|

