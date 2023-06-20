<<dd_version: 2>>

How to embed your Stata results in a .html file 

Abimereki Muzaale

**Background:** 
A user downloads and installs a system of program files, mostly ado-files, which form the foundation of most of the commands 
used in Stata Programming. Using those commands and additional syntax written out sequentially in a do-file, the user creates 
well-formed instruction to Stata called a do-file script. Once the user runs this script, results are generated and displayed
in the results window, in a graph, or in a file (.xlsx, .log, .dta, .docx, .md, .html, etc). The .html file format is of specific 
interest since its the pathway to self-publication. To illustrate how this may be achieved in Stata, we hereby introduce the `dyndoc`
command. 

**Methods:** 
We created a do-file and populated it with this abstract using [markdown](https://en.wikipedia.org/wiki/Markdown) language. Anything 
in this document that is not ordinary text including <<dd_version: 2>>, <<dd_do:nooutput>>, <</dd_do>>, **text**, <<dd_display: c(N)>> is a 
[markup](https://en.wikipedia.org/wiki/Markup_language#:~:text=A%20markup%20language%20is%20a,content%20to%20facilitate%20automated%20processing.). 
Results that might be numeric, string, alphanumeric, or formatted as macros are embeded at these markedup points. We then saved this 
document using the file extension .do; however, any text file extension will work (.txt, .md, .do, etc). To the `pwd` where we saved
this text file, we adeded a cascading style sheet (stmarkdown.css) to enhance the aesthetic of our .html file. Finally, we typed the 
following command into the Stata command window: `dyndoc filename.txt, saving(filename.html)`. 

```
<<dd_do:nooutput>>
webuse lifeexp, clear 
encode country, gen(Country)
twoway scatter lexp Country, xscale(off)
graph export lexp_bycountry.png, replace 
<</dd_do>>
```

<<dd_graph>>

```
<<dd_do>>
display c(N) 
display c(k)    
<</dd_do>>
```

**Results:** 
We identified the newly created .html file in our folder and openned it to compare its format to this markdown file. And we saw all that
we had made, and behold, it was very good. Ghastly looking macros in the original markdown language now appeared as neatly formatted
results. For instance, there were  <<dd_display: c(N)>> observations and <<dd_display: c(k) >> in the analyzed dataset. 

**Conclusions:** 
In walking you through syntax, do-file creation, queued commands, generated results, through to embedding neatly formatted output in
.html, we believe you now have a solid sense of all that Stata has to offer you. These ideas can be generalized to embedding results 
in .xlsx, .log, .dta, .docx, etc. 



