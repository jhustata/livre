Lab 5 Part 1

6/23/2023

Overview: write a .do file which imports the requested data sets and creates the graphs described below using the slides we have discussed in class. Your .do file must be called lab5\_*yourname*.do and must create a log file called lab5\_*yourname*.log. This file will contain your answers for both part 1 and part 2 of today's lab. Your .do file should follow conventions for .do file structure described in class. Do not submit your log files as part of the assignment. 

Evaluation: Evaluation will be based on the graphs produced by your script. 

At the start of your code for each question, leave a blank line and then a comment indicating the question number, like this:

**Look at [name]\_q1.png through q5.png**

//QUESTION 1

Tasks:

1. Import transplants.dta. Create a variable label for the variable wait\_yrs, such as "Time on the waitlist in years." Then, create a scatter plot with wait\_yrs on the y-axis and age at transplant (age) on the x-axis. 
2. Import tx\_yr.dta (created by lecture5\_2019.do).  In this task you will create one graph that is two plots overlaid on one another. The graph should illustrate (1) the number of recipients who were unemployed (variable: not\_working) per year (yr) as a bar graph and (2) the total number of transplants (variable: total) per year (yr) as a line graph. 
3. Fix your graph from question 2 so that the y-axis begins at 0 and labels go from 0 to to 250 by increments of 50.



ab 5 Part 2

`	`Edit your code for questions 1-3 so that you export the three graphs as [yourname]\_q1.png, [yourname]\_q2.png, and [yourname]\_q3.png.

4. Import transplants.dta. Create a graph that is two scatter plots overlaid. Graph recipient weight in kilograms (rec\_wgt\_kg) on the y-axis and age at transplant (age) on the x-axis, with separate colors and/or makers for males and females. (HINT: if might be helpful). The legend should denote the two categories as "male recipients" and "female recipients". Export the graph as [yourname]\_q4.png.

5. Import tx\_yr.dta (created by lecture5\_2019.do). Graph unknown, hypertensive, and diabetes by yr. Include a title, y-axis title, a red-vertical line at year 2008, change the colors and patterns of each line, change the labels in the legend, make the legend span 3 columns, and fix the y-axis. The graph should look like this: 



Export the graph as [yourname]\_q5.png.

For an extra point: Add the text "Policy Change" to the figure near the red line.


