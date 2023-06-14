# Lab 2

Lab 2 Part 1

6/20/2023

Overview: write a .do file which imports transplants.dta and performs the data management/ exploratory data analysis tasks described below using the slides we have discussed in class. Your .do file must be called lab2\_*yourname*.do and must create a log file called lab2\_*yourname*.log. This file will contain your answers for both part 1 and part 2 of today's lab. Your .do file should follow conventions for .do file structure described in class. Do not submit your log files as part of the assignment. 

Evaluation: Evaluation will be based on the log file produced by your script. 

At the start of your answer to each question, leave a blank line and then a comment indicating the question number, like this:

//QUESTION 1

Tasks:

1. Do a chi2 test to test the association between recipient HCV status (rec\_hcv) and gender (gender). Make Stata print the p value, like this:

Chi-squared p value (question 1): xxxxxx **0.006 (any formatting OK)**

Except print the correct p value.

Note: here and in other questions, if the p value is (for example) 0.4, don't have a command like

disp 0.4

Instead, write code to calculate and then display the number we are asking for.

2. Do a one-sided Fisher exact test to test the association between recipient HCV status (rec\_hcv) and gender (gender). Make Stata print the one-sided p value, like this:

One-sided Fisher exact p value (question 2): xxxxxx

Except print the correct p value. **0.003 (any formatting OK)**

3. Run a logistic regression to test the association between age and recipient HCV status (logistic rec\_hcv age). Make Stata print the odds ratio from that regression, like this:

Odds ratio (question 3): xx.xx (95% CI yy.yy-zz.zz) **1.02 (95% CI 1.01-1.04)**

4. Make Stata print the p value for the coefficient from that regression, like this:

P value (question 4): 0.yyyy **0.0009**



Lab 2 part 2

5. Write code to produce the following output: 

Question 5: mean peak PRA is 18.4 in males and 14.5 in females

But fill in the correct numbers.  **10.4, 26.4**

6. Create a variable called hypertensive which is 1 for transplant recipients who have ESRD secondary to hypertension (dx==4) and 0 for everyone else. Create another variable called college which is 1 for recipients with an associate's/bachelor's degree or a graduate degree and 0 for recipients who have no education, grade school education, or high school/GED.  Create a variable called male which is 1 for male recipients and 0 for female recipients. 

Now run a logistic regression of hypertensive on age, BMI, college, and male gender (logistic hypertensive age bmi college male). Write a program called table\_q6 that displays a table of odds ratios, like this:

Regression table (Question 6)

age        x.xx (x.xx - x.xx)

bmi        x.xx (x.xx - x.xx)

college    x.xx (x.xx - x.xx)

male       x.xx (x.xx - x.xx)

except fill in the correct numbers.

**age        1.01 (1.00-1.02)**

**bmi        1.02 (1.00-1.04)**

**college    0.91 (0.72-1.14)**

**male       1.21 (0.96-1.53)**

**Values might be slightly different since the def of "college" is undefined if rec\_educ is "some college" or missing**
