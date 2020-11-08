# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Testing, Statistical Summaries and Inference

 - [Problem Statement](#Problem-Statement)
 - [Executive Summary](#Executive-Summary)
 - [Data Dictionary](#Data-Dictionary)
 - [Conclusions & Recommendations](#Conclusions-&-Recommendations)
 - [References](#References)
 - [Data Sources](#Data-Sources)

## Problem Statement

The new format for the SAT was released in March 2016. The ACT, which is the alternative standardized test used for college admissions, has been steadily gaining popularity as the test of choice amongst students in recent years. We are keen to investigate the changes in statewide SAT test participation rates and the factors influencing them, and to identify recommendations that could be taken by the College Board to boost SAT participation rates in the years ahead.

---
## Executive Summary
**INTRODUCTION**

Datasets for the SAT and ACT from 2017 and 2018 were used for this analysis. The datasets included state names, mean participations rates, mean individual test scores and mean total/composite scores for each state.

**METHODOLOGY**

- The datasets were imported from the relevant .csv files that were provided into pandas DataFrames.
- The datasets were cleaned and converted to be of the appropriate types. Extraneous rows were cleaned and problematic individual values in the provided datasets were cross-referenced with the original source datasets, before being corrected appropriately. The datasets were then merged into a single DataFrame.
- Exploratory Data Analysis was performed to quickly obtain summary statistics and investigate trends in the data.
- Data visualization was carried out in the form of histograms, scatter plots, box plots and bar plots to provide useful representations of the participation and test score distributions, and to observe any trends in the spread, shape and central tendencies.

**KEY TAKEAWAYS AND FINDINGS**

- There is a strong negative correlation between SAT and ACT participation rates. This is to be expected, as most universities accept both SAT scores and ACT scores as a form of standardized score to measure college readiness, and there is little additional merit in taking both tests.
- State-mandated testing can significantly boost participation rates as shown in the case of Colorado and Illinois, however this may not be easily done in most cases - oftentimes requiring extensive effort and long periods of state lobbying.
- When tests are optional, only better students tend to take them and hence there might be selection bias in the reported mean scores. Students who are most ready for college are likely to be the ones who sit for these tests voluntarily. It is unfair to compare mean test scores across different states who may have different state policies on testing to conclude which is the better state, given the difference in participation rates. Even states that have similar participation rates may have varying student populations sitting for the tests.

---
## Data Dictionary

**Data Dictionary**

|Feature|Type|Dataset|Description|
|:-:|:-:|:-:|:--|
|**state**|*object*|ACT/SAT 2017|The name of the state where the ACT or SAT was conducted in.|
|<br>|
|**sat17_participation**|*int*|SAT 2017|The SAT participation rate for the state in 2017 (in %).|
|**sat17_readwrite**|*int*|SAT 2017|The state mean score for the SAT Evidence-Based Reading and Writing section in 2017 (from 200 to 800). |
|**sat17_math**|*int*|SAT 2017|The state mean score for the SAT Math section in 2017 (from 200 to 800).|
|**sat17_total**|*int*|SAT 2017|The state mean total score for the SAT test in 2017 (from 400 to 1600).|
|<br>|
|**sat18_participation**|*int*|SAT 2018|The SAT participation rate for the state in 2018 (in %).|
|**sat18_readwrite**|*int*|SAT 2018|The state mean score for the SAT Evidence-Based Reading and Writing section in 2018 (from 200 to 800). |
|**sat18_math**|*int*|SAT 2018|The state mean score for the SAT Math section in 2018 (from 200 to 800).|
|**sat18_total**|*int*|SAT 2018|The state mean total score for the SAT test in 2018 (from 400 to 1600).|
|<br>|
|**act17_participation**|*int*|ACT 2017|The ACT participation rate for the state in 2017 (in %).|
|**act17_english**|*float*|ACT 2017|The state mean score for the ACT English section in 2017 (from 1 to 36).|
|**act17_math**|*float*|ACT 2017|The state mean score for the ACT Math section in 2017 (from 1 to 36).|
|**act17_reading**|*float*|ACT 2017|The state mean score for the ACT Reading section in 2017 (from 1 to 36).|
|**act17_science**|*float*|ACT 2017|The state mean score for the ACT Science section in 2017 (from 1 to 36).|
|**act17_composite**|*float*|ACT 2017|The state mean average score of all 4 sections for the ACT in 2017 (from 1 to 36).|
|<br>|
|**act18_participation**|*int*|ACT 2018|The ACT participation rate for the state in 2018 (in %).|
|**act18_english**|*float*|ACT 2018|The state mean score for the ACT English section in 2018 (from 1 to 36).|
|**act18_math**|*float*|ACT 2018|The state mean score for the ACT Math section in 2018 (from 1 to 36).|
|**act18_reading**|*float*|ACT 2018|The state mean score for the ACT Reading section in 2018 (from 1 to 36).|
|**act18_science**|*float*|ACT 2018|The state mean score for the ACT Science section in 2018 (from 1 to 36).|
|**act18_composite**|*float*|ACT 2018|The state mean average score of all 4 sections for the ACT in 2018 (from 1 to 36).|

---
## Conclusions & Recommendations 

- Given that students typically take only one test or the other, there is little incentive in targetting states that already see extremely high participation rates in the ACT, unless there are contracts that are due to expire soon.
- One possible state where SAT participation could be encouraged is **West Virginia**. West Virginia saw an increase in SAT participation rate from 14 to 28%, while the ACT participation rate fell from 69% to 65%. At the moment, neither SAT nor ACT testing is made mandatory in West Virginia.
- As such, the College Board could work with the local authorities to encourage students to take the SAT, by subsidising testing fees, showcasing the merits of standardized testing to students and college advisors so that they can prepare early, or implement 'SAT School Day' programs that have been successful in increasing participation rates in other states thus far.
- However, as higher participation rates are often correlated with lower average test scores, it would also be beneficial for the College Board to provide more supplementary resources to students (e.g. free practice tests) so that they can better prepare for the test. Some states tend to underperform compared to the national average, and they may not be keen to extend testing to more students if this would further depress the state testing scores.

--- 
## References
References used in this analysis:
1. https://blog.prepscholar.com/new-sat-format-2016

2. https://sat.edu.sg/sat-vs-act

3. https://www.princetonreview.com/college-advice/5-reasons-to-take-both-sat-and-act

4. https://www.chicagotribune.com/news/ct-illinois-chooses-sat-met-20160211-story.html

5. https://magoosh.com/hs/act/2017/states-that-require-the-act-or-sat/
--- 
## Data Sources
The sources of the datasets used in this analysis: 
- [SAT 2017 dataset](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/)
- [SAT 2018 dataset](https://reports.collegeboard.org/sat-suite-program-results/state-results)
- [ACT 2017 dataset](https://www.act.org/content/dam/act/unsecured/documents/cccr2017/ACT_2017-Average_Scores_by_State.pdf)
- [ACT 2018 dataset](http://www.act.org/content/dam/act/unsecured/documents/cccr2018/Average-Scores-by-State.pdf)
