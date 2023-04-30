Download Link: https://assignmentchef.com/product/solved-gu4206-gr5206-homework2-iris
<br>



<h1>Part 1 (Iris)</h1>

<strong>Background</strong>

The R data description follows:

This famous (Fisher’s or Anderson’s) iris data set gives the measurements in centimeters of the variables sepal length and width and petal length and width, respectively, for 50 flowers from each of 3 species of iris. The species are Iris setosa, versicolor, and virginica.

<h1>Task</h1>

1) Using ggplot, as apposed to Base R, produce the same plot constructed by the following code. That is, plot <strong>Petal Length </strong>versus <strong>Sepal Length </strong>split by <strong>Species</strong>. The colors of the points should be split according to <strong>Species</strong>. Also overlay three regression lines on the plot, one for each <strong>Species </strong>level. Make sure to include an appropriate legend and labels to the plot. Note: The function <strong>coef() </strong>extracts the intercept and the slope of an estimated line.

<table width="632">

 <tbody>

  <tr>

   <td width="632"><em># Base plot</em><strong>plot</strong>(iris<strong><sub>$</sub></strong>Sepal.Length,iris<strong><sub>$</sub></strong>Petal.Length,col=iris<strong><sub>$</sub></strong>Species,xlab=”Sepal”,ylab=”Petal”,main=<em># loop to construct each LOBF</em><strong>for </strong>(i <strong>in </strong>1<strong>:</strong><strong>length</strong>(<strong>levels</strong>(iris<strong>$</strong>Species))) { extract &lt;- iris<strong>$</strong>Species<strong>==</strong><strong><sub>levels</sub></strong>(iris<strong>$</strong>Species)[i]<strong>abline</strong>(<strong>lm</strong>(iris<strong>$</strong>Petal.Length[extract]<strong>~</strong>iris<strong>$</strong>Sepal.Length[extract]),col=i) }<em># Legend</em><strong>legend</strong>(“right”,legend=<strong>levels</strong>(iris<strong>$</strong>Species),fill = 1<strong>:</strong><strong><sub>length</sub></strong>(<strong>levels</strong>(iris<strong>$</strong>Species)), cex =</td>

  </tr>

 </tbody>

</table>

“Gabriel’s Plot

.75)

<em># Add points and text</em>

<strong>points</strong>(iris<strong>$</strong>Sepal.Length[15],iris<strong>$</strong>Petal.Length[15], pch = “*”, col = “black”) <strong>text</strong>(iris<strong><sub>$</sub></strong>Sepal.Length[15]<strong><sub>+</sub></strong>.4,iris<strong><sub>$</sub></strong>Petal.Length[15],”(5.8,1.2)”,col=”black”) <strong>points</strong>(iris<strong>$</strong>Sepal.Length[99],iris<strong>$</strong>Petal.Length[99], pch = “*”, col = “red”) <strong>text</strong>(iris<strong><sub>$</sub></strong>Sepal.Length[99]<strong><sub>+</sub></strong>.35,iris<strong><sub>$</sub></strong>Petal.Length[99],”(5.1,3)”,col = “red”) <strong>points</strong>(iris<strong>$</strong>Sepal.Length[107],iris<strong>$</strong>Petal.Length[107],pch = “*”, col = “green”) <strong>text</strong>(iris<strong><sub>$</sub></strong>Sepal.Length[107],iris<strong><sub>$</sub></strong>Petal.Length[107]<strong><sub>+</sub></strong>.35,”(4.9,4.5)”,col = “green”)

<h2>Gabriel’s Plot</h2>

Sepal

<strong>Solution goes below:</strong>

<strong>library</strong>(ggplot2) <em>## Plot.</em>

<strong>Part 2 (World’s Richest)</strong>

<h1>Background</h1>

We consider a data set containing information about the world’s richest people. The data set us taken form the World Top Incomes Database (WTID) hosted by the Paris School of Economics <a href="http://top-incomes.g-mond.parisschoolofeconomics.eu/">[http://top-incomes.g</a><a href="http://top-incomes.g-mond.parisschoolofeconomics.eu/">mond.parisschoolofeconomics.eu]</a>. This is derived from income tax reports, and compiles information about the very highest incomes in various countries over time, trying as hard as possible to produce numbers that are comparable across time and space.

<h1>Tasks</h1>

<ul>

 <li>Open the file and make a new variable (dataframe) containing only the year, “P99”, “P99.5” and “P99.9” variables; these are the income levels which put someone at the 99th, 99.5th, and 99.9th, percentile of income. What was P99 in 1993? P99.5 in 1942? You must identify these using your code rather than looking up the values manually. The code for this part is given below.</li>

</ul>

<strong>Solution goes below:</strong>

<table width="632">

 <tbody>

  <tr>

   <td width="632">wtid &lt;- <strong>read.csv</strong>(“wtid-report.csv”, as.is = TRUE)wtid &lt;- wtid[, <strong><sub>c</sub></strong>(“Year”, “P99.income.threshold”,”P99.5.income.threshold”, <strong>names</strong>(wtid) &lt;- <strong>c</strong>(“Year”, “P99”, “P99.5”, “P99.9”)</td>

  </tr>

 </tbody>

</table>

“P99.9.income.threshold”)]

<ul>

 <li>Using ggplot, display three line plots on the same graph showing the income threshold amount against time for each group, P99, P99.5 and P99.9. Make sure the axes are labeled appropriately, and in particular that the horizontal axis is labeled with years between 1913 and 2012, not just numbers from 1 to 100. Also make sure a legend is displayed that describes the multiple time series plot. Write one or two sentences describing how income inequality has changed throughout time.</li>

</ul>

<strong>Solution goes below:</strong>

<em>## Plot</em>

<strong>Part 3 (Titanic)</strong>

<h1>Background</h1>

In this part we’ll be studying a data set which provides information on the survival rates of passengers on the fatal voyage of the ocean liner <em>Titanic</em>. The dataset provides information on each passenger including, for example, economic status, sex, age, cabin, name, and survival status. This is a training dataset taken from the Kaggle competition website; for more information on Kaggle competitions, please refer to <a href="https://www.kaggle.com/">https://www.kaggle.com.</a> Students should download the data set on Canvas.

<h1>Tasks</h1>

4) Run the following code and describe what the two plots are producing

<em># Read in data</em>

titanic &lt;- <strong><sub>read.table</sub></strong>(“Titanic.txt”, header = TRUE, as.is = TRUE) <strong>head</strong>(titanic)

##              PassengerId Survived Pclass

## 1        1              0              3 ## 2     2                1              1 ## 3     3              1                3

## 4                            4                   1              1

## 5                            5                   0              3

## 6                            6                   0              3

##                                                                                                                    Name             Sex Age SibSp Parch

## 1                                                                          Braund, Mr. Owen Harris             male 22              1            0

## 2 Cumings, Mrs. John Bradley (Florence Briggs Thayer) female 38                                             1            0

## 3                                                                                 Heikkinen, Miss. Laina female 26                    0            0

## 4                                    Futrelle, Mrs. Jacques Heath (Lily May Peel) female 35                           1            0

## 5 Allen, Mr. William Henry male 35 0 0 ## 6 Moran, Mr. James male NA 0 0

##                                Ticket              Fare Cabin Embarked

## 1        A/5 21171 7.2500               S ## 2     PC 17599 71.2833 C85         C ## 3 STON/O2. 3101282 7.9250   S ## 4        113803 53.1000 C123        S ## 5     373450 8.0500   S

## 6                              330877 8.4583                                   Q

<strong>library</strong>(ggplot2)

<em># Plot 1 </em><strong>ggplot</strong>(data=titanic) <strong><sub>+ </sub></strong><strong>geom_bar</strong>(<strong>aes</strong>(x=Sex,fill=<strong>factor</strong>(Survived)))<strong>+ </strong><strong>labs</strong>(title = “Title”,fill=”Survived”)

Title

<table width="632">

 <tbody>

  <tr>

   <td width="632"><em># plot 2</em><strong>ggplot</strong>(data=titanic) <strong>+ </strong><strong>geom_bar</strong>(<strong>aes</strong>(x=<strong>factor</strong>(Survived),fill=<strong>factor</strong>(Survived)))<strong>+ </strong><strong>facet_grid</strong>(<strong>~</strong>Sex)<strong>+</strong><strong>labs</strong>(title = “Title”,fill=”Survived”,x=””)</td>

  </tr>

 </tbody>

</table>

Title

<ul>

 <li>Create a similar plot with the variable <strong>Pclass</strong>. The easiest way to produce this plot is to <strong>facet </strong>by <strong>Pclass</strong>. Make sure to include appropriate labels and titles. Describe your</li>

</ul>

<strong>Solution goes below:</strong>

<em># Plots</em>

<ul>

 <li>Create one more plot of your choice related to the <strong>titanic </strong>data set. Describe what information your plot is conveying.</li>

</ul>

<strong>Solution goes below:</strong>

<em># Plots</em>

<h1>Part 4 (Simulating and Graphing Probability Density)</h1>

7) Simulate a <em>n </em>= 1000 random draws from a beta distribution with parameters <em>α </em>= 3 and <em>β </em>= 1. Plot a histogram of the simulated cases using <strong>ggplot</strong>. Also overlay the beta density on the histogram. Hint: look up the beta distribution using <strong>?rbeta</strong>.

<strong>Solution goes below:</strong>

<em># Sim and plots</em>