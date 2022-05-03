# Commodity Prices

This is a website to showcase our final project for FIN 377 - Data Science for Finance course at Lehigh University.

To see the complete analysis file(s) click [here](https://github.com/julioveracruz/testwebsite/blob/main/notebooks/example.ipynb).

Maybe you want a different website them for the project? Consider `minimal-mistakes`:
1. [Go here](https://github.com/mmistakes/mm-github-pages-starter/generate).
2. In the resulting repo, click Settings, then Pages, then make sure the source is the main branch.
3. [The doc site is here](https://mmistakes.github.io/minimal-mistakes/docs/structure/) and will help you customize layouts and figure out how to use it.

## Table of contents
1. [Introduction](#introduction)
2. [Methodology](#meth)
3. [Section 2](#section2)
    1. [Subsection](#subsec2-1)
    2. [Subsection](#subsec2-2)
4. [Analysis Section](#section3)
5. [Summary](#summary)

## Introduction  <a name="introduction"></a>

The main goal of this project is to explore whether it is possible to predict the price of various agricultural commodities (corn, wheat, and soybeans) by using machine learning techniques on macroeconomic, weather, and financial datasets.  

## Methodology <a name="meth"></a>

Here is some code that we used to develop our analysis. Blah Blah. [More details are provided in the Appendix](page2).
 
Note that for the purposes of the website, you have to copy this code into the markdown file and  
put the code inside trip backticks with the keyword `python`.

```python
import seaborn as sns 
iris = sns.load_dataset('iris') 

print(iris.head(),  '\n---')
print(iris.tail(),  '\n---')
print(iris.columns, '\n---')
print("The shape is: ",iris.shape, '\n---')
print("Info:",iris.info(), '\n---') # memory usage, name, dtype, and # of non-null obs (--> # of missing obs) per variable
print(iris.describe(), '\n---') # summary stats, and you can customize the list!
print(iris['species'].value_counts()[:10], '\n---')
print(iris['species'].nunique(), '\n---')
```

Notice that the output does NOT show! **You have to copy in figures and tables from the notebooks.**

## Section <a name="section2"></a>
Blah blah

### Subsection 1 <a name="subsec2-1"></a>
This is a subsection, formatted in heading 3 style

### Subsection 2 <a name="subsec2-2"></a>
This is a subsection, formatted in heading 3 style

## Analysis Section <a name="section3"></a>

Here are some graphs that we created in our analysis. We saved them to the `pics/` subfolder and include them via the usual markdown syntax for pictures.

![](pics/plot1.png)
<br><br>
Some analysis here
<br><br>
![](pics/plot2.png)
<br><br>
More analysis here.
<br><br>
![](pics/plot3.png)
<br><br>
More analysis.

## Summary <a name="summary"></a>

Blah blah 



## About the team

<img src="pics/alex.jpg" alt="Alex Outkou" width="300"/>
<br>
Alex Outkou is a Finance and Business Information Systems double major at Lehigh University. He can be reached at ado323@lehigh.edu.
<br><br><br>
<img src="pics/mike.jpg" alt="Michael Rich" width="300"/>
<br>
Michael Rich is a Financial Engineering major in Lehigh University's IBE program. He can be reached at mbr223@lehigh.edu.
<br><br><br>
<img src="pics/pics/lukec.jpg" alt="Luke Costello" width="300"/>
<br>
Luke Costello is pursuing a degree in Finance at Lehigh University. He can be reached at lrc224@lehigh.edu
<br><br><br>
<img src="pics/harry.jpg" alt="Harry Herman" width="300"/>
<br>
Harry Herman is a Finance major at Lehigh University. He can be reached at hsh423@lehigh.edu.


## More 

To view the GitHub repo for this website, click [here](https://github.com/donbowen/teamproject).
