# SAS Introduction to Statistical Concepts

from ECSTAT0 - SAS Introduction to Statistical Concepts

---

### Topic Summaries:
Basic Statistical Concepts:
- descriptive and inferential statistics
- populations and samples
- parameters and statistics
- uses of variables: independent and dependent
- types of variables: quantitative and categorical
- scales of measurement (nominal, ordinal, interval, and ratio)
- statistical methods

Descriptive Statistics
- describing your data
- measures of location
- percentiles
- measures of variability

Picturing Your Data
- picturing your data: histogram
- normal distribution
- assessing normality
- measures of shape: skewness
- measures of shape: kurtosis
- normal probability plots
- box plots
- comparing distributions

Confidence Intervals for the Mean
- point estimators, variability, and standard error
- distribution of sample means
- interval estimators
- confidence intervals
- normality and the central limit theorem

Hypothesis Testing
- decision-making process
- steps in hypothesis testing
- types of errors and power
- the p-value, effect size, and sample size
- statistical hypothesis test
- the t statistic, t distribution, and two-sided t-test

---
### 1. Basic Statistical Concepts

**Descriptive statistics** organizes, describes, and summarizes data using numbers and graphical techniques. Inferential statistics is concerned with drawing conclusions about a population from the analysis of a random sample drawn from that population. Inferential statistics is also concerned with the precision and reliability of those inferences.

**A population** is the complete set of observations or the entire group of objects that you are researching. A sample is a subset of the population. The sample should be representative of the population. You can obtain a representative sample by collecting a simple random sample.

**Parameters** are numerical values that summarize characteristics of a population. Parameter values are typically unknown and are represented by Greek letters. Statistics summarize characteristics of a sample. You use letters from the English alphabet to represent sample statistics. You can measure characteristics of your sample and provide numerical values that summarize those characteristics. You use statistics to estimate parameters.

**Variables** are characteristics or properties of data that take on different values or amounts. A variable can be independent or dependent. In some contexts, you select the value of an independent variable, in order to determine its relationship to the dependent variable. In other contexts, the independent variable’s values are simply taken as given.

Variables are also classified according to their characteristics. They can be quantitative or categorical.

**Quantitative variables**:

Data that consists of counts or measurements is quantitative. Quantitative data can be further distinguished by two types: *discrete* and *continuous*. Discrete data takes on only a finite, or countable, number of values. Continuous data has an infinite number of values and no breaks or jumps.

**Categorical variables**:

Categorical or attribute data consists of variables that denote groupings or labels. There are two main types: *nominal* and *ordinal*. A nominal categorical variable exhibits no ordering within its groups or categories. With ordinal categorical variables, the observed levels of the variable can be ordered in a meaningful way that implies differences due to magnitude.

A variable’s classification is its scale of measurement. There are two scales of measurement for categorical variables: nominal and ordinal. There are two scales of measurement for continuous variables: interval and ratio. Data from an interval scale can be rank-ordered and has a sensible spacing of observations such that differences between measurements are meaningful. However, interval scales lack the ability to calculate ratios between numbers on the scale because there is no true zero point. Data on a ratio scale includes a true zero point and can therefore accurately indicate the ratio of difference between two spaces on the measurement scale.

The appropriate statistical method for your data also depends on the number of variables involved. *Univariate analysis* provides techniques for analyzing and describing a single variable at a time. *Bivariate analysis* describes and explains the relationship between two variables and how they change, or covary, together. *Multivariate analysis* examines two or more variables at the same time, in order to understand the relationships among them.

---
### 2.  Descriptive Statistics

A data's **distribution** tells you what values your data takes and how often it takes those values.

You can calculate descriptive statistics that measure locations in your data. Statistics that locate the center of the data are **measures of central tendency**. These include *mean (μ)*, *median*, and *mode*.

**Percentiles** are descriptive statistics that give you reference points in your data. A percentile is the value of a variable below which a certain percentage of observations fall. The most commonly reported percentiles are *quartiles*, which break the data into quarters.

There are several **descriptive statistics** that measure the variability of your data: *range*, *interquartile range (IQR)*, *variance*, *standard deviation (σ)*, and *coefficient of variation (C.V.)*.

** PROC MEANS **

To summarize and generate descriptive statistics, you use the MEANS procedure. PROC MEANS calculates a standard set of statistics, including the minimum, maximum, and mean data values, as well as standard deviation and n. The PRINTALLTYPES option displays statistics for all requested combinations of class variables


---
### 3.  Picturing Your Data

A **histogram** is a visual representation of the frequency distribution of your data. The frequencies are represented by bars.

The **normal distribution** is a common theoretical distribution in statistics. It is bell-shaped, with values concentrated near the **mean (μ)**, and it is symmetric around the mean. The **standard deviation (σ)** determines how variable the distribution is. Underlying the normal distribution is a mathematical function named the probability density function.

To check the assumption that your random sample has a normal distribution, you can plot a histogram. You can also look at statistical summaries of your data. The closer **skewness** and **kurtosis** are to 0, the closer your data is shaped like the normal distribution.

**Skewness** measures the tendency of your data to be more spread out on one side of the mean than on the other. It measures the asymmetry of the distribution. The direction of skewness is the direction to which the data is trailing off. The closer the skewness is to 0, the more normal or symmetric the data.

**Kurtosis** measures the tendency of data to be concentrated toward the center or toward the tails of the distribution. The closer kurtosis is to 0, the closer the tails of the data resemble the tail thickness of the normal distribution. Kurtosis can be difficult to assess visually.

A negative kurtosis statistic means that the data has lighter tails than in a normal distribution and is less heavily concentrated about the mean. This is a platykurtic distribution.
A positive kurtosis statistic means that the data has heavier tails and is more concentrated about the mean than a normal distribution. This is a leptokurtic distribution, which is often referred to as heavy-tailed and also as an outlier-prone distribution.

A **normal probability plot** is another way to visualize and assess the distribution of your data. The vertical axis represents the actual data values. The horizontal axis displays the expected percentiles from a standard normal distribution. The normal reference line along the diagonal indicates where the data would fall if it were perfectly normal.

A **box plot** makes it easy to see how spread out the data is and if there are any outliers.

**PROC UNIVARIATE**

You can use PROC UNIVARIATE to generate descriptive statistics, histograms, and normal probability plots.

In the ID statement, you list the variable or variables that SAS should label in the table of extreme observations and identify as outliers in the graphs.

You can add additional options to the HISTOGRAM and PROBPLOT statements. The NORMAL option uses estimates of the population mean and standard deviation to add a normal curve overlay to the histogram and a diagonal reference line to the normal probability plot.

You can use the INSET statement to create a box of summary statistics directly on the graphs.

** PROC SGSCATTER, PROC SGPLOT, PROC SGPANEL, and PROC SGRENDER **

In addition to the statistical graphics available to you with PROC UNIVARIATE, you might want to use PROC SGSCATTER, PROC SGPLOT, PROC SGPANEL, and PROC SGRENDER to produce a wide variety of additional plot types.

You can use PROC SGPLOT to generate dot plots, horizontal and vertical bar charts, histograms, box plots, density curves, scatter plots, series plots, band plots, needle plots, and vector plots. The REG statement generates a fitted regression line or curve. You use a REFLINE statement to create a horizontal or vertical reference line on the plot.

**ODS Graphics**

ODS Graphics is an extension of the SAS Output Delivery System. With ODS Graphics, statistical procedures produce graphs as automatically as they produce tables, and graphs are integrated with tables in the ODS output. You can find a list of the graphs available for each SAS procedure in the SAS documentation.

---
### 4.  Confidence Intervals for the Mean

A **point estimator** is a sample statistic used to estimate a population parameter. A statistic that measures the variability of your estimator is the standard error.

The **standard error** of the mean measures the variability of your sample mean. It’s an estimate of how much you can expect the sample mean to vary from sample to sample.

The **distribution of sample mean** is the distribution of all possible sample means from the population. The distribution of the mean is always less variable than the data.

An **interval estimator** is another way to estimate a population parameter. It incorporates the uncertainty that arises from random variability.

**Confidence intervals** are a type of interval estimator used to estimate the population mean, while taking into account the variability of the sample mean.

The **central limit theorem** states that the distribution of sample means is approximately normal, regardless of the population distribution's shape, if the sample size is large enough.

**PROC MEANS**

You can use the MEANS procedure to generate a 95% confidence interval for the mean.
You can use the CLM option in the PROC MEANS statement to calculate the confidence limits for the mean.
You can add the ALPHA= option to the PROC MEANS statement in order to construct confidence intervals with a different confidence level.

---
### 5.  Hypothesis Testing

A **hypothesis test** uses sample data to evaluate a question about a population. It provides a way to make inferences about a population, based on sample data.

There are four steps in conducting a hypothesis test.

The first step is to **identify the population of interest and determine the null and alternative hypotheses**. The **null hypothesis, H0**, is what you assume to be true, unless proven otherwise. It is usually a hypothesis of equality. The **alternative hypothesis, Ha or H1**, is typically what you suspect, or are attempting to demonstrate. It is usually a hypothesis of inequality.

The second step in hypothesis testing is to **select the significance level (α)**. This is the amount of evidence needed to reject the null hypothesis. A common significance level is α = 0.05 (1 chance in 20).

The third step is to **collect the data**.

The fourth step is to **use a decision rule to evaluate the data**. You decide whether or not there is enough evidence to reject the null hypothesis.

If you reject the null hypothesis when it's actually true, you've made a **Type I error**. The probability of committing a Type I error is α. **α is the significance level of a test**.

If you fail to reject the null hypothesis and it's actually false, you've made a **Type II error**. The probability of committing a Type II error is **β**. Type I and II errors are inversely related. The **power of a statistical test** is equal to 1 minus beta **(1 – β)**,

The difference between the observed statistic and the hypothesized value is the **effect size**. A **p-value** measures the probability of observing a value as extreme as the one observed or more extreme. A p-value is not only affected by the effect size, but also by the sample size.

The **t statistic** measures how far X-bar, the sample mean, is from the hypothesized mean, μ0.

If the t statistic is much higher or lower than 0 and has a small corresponding p-value, this indicates that the sample mean is quite different from the hypothesized mean, and you would **reject the null hypothesis**.

**PROC UNIVARIATE**

You can use PROC UNIVARIATE to perform a statistical hypothesis test. You use the MU0= option to specify the value of the hypothesized mean, μ0. You can use the ALPHA= option to change the significance level.

---
### SAS Syntax

To go to the movie where you learned a statement or option, select a link.

PROC MEANS DATA=SAS-data-set <options>;       
CLASS variables;
VAR variables;
RUN;
 
PROC UNIVARIATE DATA=SAS-data-set <options>;      
VAR variables;
ID variables;
HISTOGRAM variables </options>;
PROBPPLOT variables </options>;
INSET keywords </options>;
RUN;
 
PROC SGPLOT DATA=SAS-data-set<options>;
DOT category-variable </option(s)>;
HBAR category-variable </option(s)>;
VBAR category-variable </option(s)>;
HBOX response-variable </option(s)>;
VBOX response-variable </option(s)>;
HISTOGRAM response-variable </option(s)>;
SCATTER X=variable Y=variable </option(s)>;
NEEDLE X=variable Y=numeric-variable </option(s)>;
REG X=numeric-variable Y=numeric-variable </option(s)>;
REFLINE variable | value-1 <... value-n> </option(s)>;
RUN;
ODS GRAPHICS ON <options>;
statistical procedure code
ODS GRAPHICS OFF;

---
### Sample SAS Programs

- Using PROC MEANS to Generate Descriptive Statistics

```{sas}
proc means data=statdata.testscores maxdec=2 fw=10 printalltypes
           n mean median std var q1 q3;
   class Gender;
   var SATScore;
   title 'Selected Descriptive Statistics for SAT Scores';
run;
title;
```

- Using SAS to Picture Your Data

```{sas}
proc univariate data=statdata.testscores;
   var SATScore;
   id idnumber;
   histogram SATScore / normal(mu=est sigma=est);
   inset skewness kurtosis / position=ne;
   probplot SATScore / normal(mu=est sigma=est);
   inset skewness kurtosis;
   title 'Descriptive Statistics Using PROC UNIVARIATE';
run;
title;

proc sgplot data=statdata.testscores;
   refline 1200 / axis=y lineattrs=(color=blue);
   vbox SATScore / datalabel=IDNumber;
   format IDNumber 8.;
   title "Box Plots of SAT Scores";
run;
title;
```

- Calculating a 95% Confidence Interval

```{sas}
proc means data=statdata.testscores maxdec=4
           n mean stderr clm;
   var SATScore;
   title '95% Confidence Interval for SAT';
run;
title;
```

- Using PROC UNIVARIATE to Perform a Hypothesis Test

```{sas}
ods select testsforlocation;
proc univariate data=statdata.testscores mu0=1200;
   var SATScore;
   title 'Testing Whether the Mean of SAT Scores = 1200';
run;
title;
```
