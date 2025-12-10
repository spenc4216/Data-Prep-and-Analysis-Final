#Data Preperation and Analysis Final 
# Project Title Social Media and Mental Health for Men

## 1. Research Question

I am researching social media and mental health. I choose to evaluate the “gender” column within the dataset. I want to see if there is any difference in the happiness of social media users based on the gender the participate. Male vs others.  

## 2. Hypothesis
* Null hypothesis
	Gender has no effect on the happiness of social media users.  
* Alternative hypothesis
	Gender will have an effect on happiness. 
## 3. Data Description
Describe your data source(s):
* Where it comes from (URL, API, dataset name)
	Social Media and Mental Health Balance.
* What each observation represents (unit of analysis)
	User_ID- Nominal Unique ID for each participant in data gathering exercise.
	Age- Continuous Age of each participant.
	Gender – Categorical selection of gender.  
	Daily_Screentime(hrs) – Continuous number of hours each person uses their phone
	Sleep_Quality(1-10) – Ordinal ranking of sleep 1-10
	Stess_Level (1-10) – Ordinal ranking of stress 1-10
	Days_Without_Socia_Media -  Continuous number of days each person does not use.
	Exercise_Frequenecy(week) -  Continuous number of days each person exercise a week. 
	Social_Media_Platfom -  Categorical selection of social media used. 
	Happiness_Index(1 – 10) – Ordinal ranking of happiness 1-10
* Number of observations and key variables
	There are 10 observations and the key variables is “Happiness_INDEX(1-10)”.
* Any filtering, cleaning, or transformation steps
	No filtering or cleaning. The one transformation I did was creating a observation titled Happiness by creating Happy (10-9), Neutral (7-8), Unhappy (=<6).
## 4. Methods

Summarize how you analyzed the data:

* The test statistic for your permutation test
	Create "Happiness" column from "Happiness_Index(1=10)". Created function to get observed stat from original data subtracting number of unhappy men from happy men using the shape. Subtracted number of unhappy others from happy others using the shape. Then I subtracted the unhappy others from unhappy men to get the observed stat. The observed stat will be my test statistic for the permutation.
* How you simulated or resampled under the null hypothesis
	I generated the null distribution by shuffling the Gender column while keeping their happiness responses fixed. For each shuffle I recalculated the test statistic 1000 times.
* The metric(s) for which you created bootstrap confidence intervals
	I bootstrapped the Test_Statistic via the function and the median of the column "Happiness_Index(1-10)".
* Why the CLT does not apply to at least one metric
	Median of the column "Happiness_Index(1-10)" and CLT do not work well as median is a nonlinear statistic, where the CLT states that if you take a sample mean and grow the sample size, the distribution will normalize.

## 5. Results

Present your main findings:

* Key summary statistics and visualizations
	Fail to  reject the null hypothesis as p - value is .666 indecating that the 66 percent of permuted test_statistics were as extreme as the observed statistic. There is no real noteable difference between men's happiness and other's happiness when using socila media. 
	Visualization in repository. 
* Observed test statistic and p-value (if applicable)
	Observed statistic = -0.10000000000000009
	P - value = .666
* Bootstrap confidence intervals for relevant metrics
	Bootstrap 
	Lower CI = -.467
	Upper CI = .279
	mean = -.101
	Bootstrap Median
	Lower CI - 1
	Upper CI = 1
	mean = -.223

## 6. Uncertainty Estimation

Discuss your resampling results:

* How many resamples you used
	Permutation - 1000
	Bootstrap - 1000
	Median Bootstrap -1000
* What the bootstrap or randomization distributions looked like
	Permutation - Noraml distribution centered around 0. 
	Bootstrap - Normal distribution centered around -.1.
	Median Bootstrap -  Normal distribution centered around -.1. 
* How you interpret the interval estimates
	Bootstrap confidence intervals for the proportion and median based statistics include zero, indication that the difference between the groups is minimal. 

## 7. Limitations

* Briefly note any limitations in data, assumptions, or methods, including sources of bias or missing data.
	"Happiness_Index(1-10) min score was 4. Had to create Happiness categories from score of 4-10. 
	Unknown how the data was collected or what sample of the population they were looking at. 

## 8. References

* List all datasets, tools, libraries, or papers you cited.
	Social Media and Mental Health.CSV
	VS Code
	Juypter Notebook
	pandas 
	numpy 
	import matplotlib.pyplot	
	scipy import stats
    statsmodels.stats.proportion import proportions_ztest, proportion_confint


---

**Reminder:** Your README should be clear enough that someone unfamiliar with your work could understand what you studied, how you analyzed it, and what you found.


