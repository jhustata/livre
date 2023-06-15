# Lab 4

## Part 1

Write a .do file which imports [transplants.txt](https://raw.githubusercontent.com/jhustata/livre/main/transplants.txt) and performs the data management/exploratory data analysis tasks described below using the slides we have discussed in class. Your .do file (lab4_lastname.do) and must create a log file (lab4_lastname.log). This file will contain your answers for both part 1 and part 2 of today's lab. Your .do file should follow conventions for .do file structure described in class. Do **not** submit your log files as part of the assignment.    
    
1. Create a new variable called `ctr_volume` that contains the transplant center volume (total number of transplants performed in each transplant center). The transplant center can be identified by `ctr_id`.     

`Just make sure that they did it`   
    
2. Use `summarize, detail` to show the distribution of `ctr_volume`. For question 2, you should analyze one observation per center, not one observation per transplant recipient. (<u>Hint</u>: Tagging can help with this)  

```stata
      Percentiles      Smallest
 1%            8              8
 5%            8              8
10%           26             26       Obs                  25
25%           61             54       Sum of Wgt.          25

50%           79                      Mean                 80
                        Largest       Std. Dev.      34.17358
75%          105            116
90%          127            127       Variance       1167.833
95%          128            128       Skewness      -.5265107
99%          128            128       Kurtosis       2.662681

```

3. Generate a variable called `unknown` which is a 1 for all patients whose cause of end-stage renal disease (ESRD) is unknown/uncertain/blank (`extended_dgn` = "ESRD UNKNOWN ETIOLOGY", "ESRD OF UNCERTAIN ETIOLOGY", etc.) and a zero for all other patients. Display the following sentence:

```stata
xxx of 2000 patients (yy.y%) have an unknown cause of ESRD.
```
Except fill in the correct numbers.

`My count was 893 but this will be all over the map. Just give credit if they made a reasonable effort`   

4. How many patients died within six months of their transplant (died==1 and transplant date falls ≤ 180 days before end date)? Display the following sentence:

```stata
xxx of 2000 patients (yy.y%) died within 6 months of their transplant date.
```

Except fill in the correct numbers.     

`46/2.3%`   
    
5. For each blood type, what is the mean waiting time for a transplant? (variable: wait\_yrs) What is the median waiting time for a transplant? Use egen, tagging, and list to display the blood type, mean wait time, and median wait time of each blood type so that only one record is displayed per blood type. 

```stata
     abo      meanw    medianw  
     1=A   1.989718    1.57974  
     2=B   2.609568   2.253251  
    3=AB   1.414879   1.045859  
     4=O   2.649108   2.313484  

```

Lab 4 Part 2

6. Create a variable called `over50` which is a 1 for any recipient age >50 and 0 for everyone else. Draw a survival curve stratified by over50.     

**Q:** I have a Stata dataset with transplant_date as a string in DMY format. how may I convert it to a standard date (i.e. 0=01jan1960)?     

**chatGPT:** To convert a string variable representing dates in the "DMY" format to a standard date format in Stata, you can use the following steps:

$\vdots$

```stata
gen transplant_date_num = date(transplant_date, "DMY")
format transplant_date_std %td

```

**Q:** Danke

**chatGPT:** Gern geschehen! Wenn Sie weitere Fragen haben, stehe ich Ihnen gerne zur Verfügung.

```stata
import delimited https://raw.githubusercontent.com/jhustata/livre/main/transplants.txt, clear 
g over50=age>50 if !missing(age)
g transplant_date_num = date(transplant_date, "DMY")
format transplant_date_num %td 
format end_date %td 
order transplant_date_num end_date
stset end_date,origin(transplant_date_num) entry(transplant_date_num) fail(died) scale(365.25)
sts graph, by(over50)
graph export lab4q7.png, replace  
```

![](lab4q7.png)

7. Is the difference in post-transplant survival by over50 statistically significant (p>0.05)? Write one of the following sentences:


`There is a statistically significant difference in survival by age category (p<0.05)`

or

```stata
There is no statistically significant difference in survival by age category (p=0.x)
```

8. Run a Cox regression on over50 (command `stcox over50`). Print this sentence:

```stata
Hazard ratio: x.xx (95% CI y.yy-z.zz) 
```

`3.44 (2.50-4.76)`

Except fill in the correct values.



