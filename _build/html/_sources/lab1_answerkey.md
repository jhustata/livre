# Lab 1     
     
## Part 1     
     
Write Stata commands to solve the following questions. Keep them in a **.txt** or **.docx** file. In the second half of today's class you will learn how to put them in a **.do file** or script to run all of the commands at the same time. For now, put them in a text file and copy & paste one line at a time into Stata to get the answers.        
     
You will turn this work in together with Lab 1 Part 2.     
     
Write Stata commands to answer the following questions:     
     
1. How many total patients are in the dataset? `2000`     
2. The variable "dx" represents diagnosis and "age" represents patient age. How many patients were between the ages of 50 and 60 and had diabetes as their primary diagnosis at the time of transplant? `29`     
3. The variable *wait_yrs* represents the amount of time a patient spent on the transplant waitlist prior to transplant. How many patients waited longer than 5 years for a transplant? `214`     
4. What is the age, race (variable: *race*), and Hepatitis C status (variable: *rec_hcv_antibody*) of patient with ID=493?  `75/1 (white) / negative`      
5. What are the mean ages at transplant for male and female recipients? (<u>Hint</u>: consider *tab*, *sum*) (Variable: *gender* 0=Male, 1 = Female). `50.96; 49.52`       
     
## Part 2
     
6. Generate a variable called *age_categories* that is 0 for children (ages<18), 1 for adults (18-60), and 2 for senior citizens (>60). What is the mean number of years patients spent on the waitlist in each age group? (<u>Hint</u>: consider *tab*, *sum*)  `0.71y; 2.48y; 2.27y`      
7. Type the command *describe* to see a list of all variables. Which ones don't have a variable label? Write code to give a variable label to all variables that don't yet have one. Then run describe again to show the labeled variables.  `Any description is fine`       
8. Variable "abo" represents blood type and is coded as 1=A, 2=B, 3=AB, 4=O. Variable "prev" represents whether the patient has had a previous transplant and is coded 0=No, 1=Yes. Create a value label for "prev" that labels . Put the command tab abo prev in your script, to produce the following output (with xxxx filled in):      

           |    Prev Kidney Tx
       abo |         0          1 |     Total
-----------+----------------------+----------
       1=A |       613        107 |       720 
       2=B |       226         23 |       249 
      3=AB |       104         12 |       116 
       4=O |       800        115 |       915 
-----------+----------------------+----------
     Total |     1,743        257 |     2,000

9. Generate a new variable called bmi_whocat, representing WHO categories of BMI. BMI category should have the following values: missing if BMI is missing; 1 (labeled "underweight") if BMI<18.5; 2 (labeled "normal") if BMI is 18.5-25; 3 (labeled "overweight") if BMI is 25.1-30; 4 (labeled "obese") if BMI is 30.1=40. 

 bmi_whocat |      Freq.     Percent        Cum.
------------+-----------------------------------
          1 |         51        2.77        2.77
          2 |        629       34.13       36.90
          3 |        632       34.29       71.19
          4 |        531       28.81      100.00
------------+-----------------------------------
      Total |      1,843      100.00


10. List the ID and age of every patient who is older than 80. List them in order with the oldest patient first.

       1535    85  
       1636    84  
       1592    84  
        736    82  
       1527    82  
        911    82  
        647    81  
       1061    81  
       1435    81  
