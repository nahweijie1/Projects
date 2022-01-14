Project 1: Standardized Test Analysis

### Overview

The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

The SAT has two sections of the test: Evidence-Based Reading and Writing and Math ([*source*](https://www.princetonreview.com/college/sat-sections)). The ACT has 4 sections: English, Mathematics, Reading, and Science, with an additional optional writing section ([*source*](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)). They have different score ranges, which you can read more about on their websites or additional outside sources (a quick Google search will help you understand the scores for each test):
* [SAT](https://collegereadiness.collegeboard.org/sat)
* [ACT](https://www.act.org/content/act/en.html)

Standardized tests have long been a controversial topic for students, administrators, and legislators. Since the 1940's, an increasing number of colleges have been using scores from sudents' performances on tests like the SAT and the ACT as a measure for college readiness and aptitude ([*source*](https://www.minotdailynews.com/news/local-news/2017/04/a-brief-history-of-the-sat-and-act/)). Supporters of these tests argue that these scores can be used as an objective measure to determine college admittance. Opponents of these tests claim that these tests are not accurate measures of students potential or ability and serve as an inequitable barrier to entry.

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**state**|*string*|All|State names for all 51 states in USA.|
|**sat_17_part**|*float*|SAT2017|Participation rate for the SAT examination in particular state in 2017.|
|**sat_17_rw**|*float*|SAT2017|Average test score for particular state in the SAT 2017 section of "Evidence-based Reading and Writing".|
|**sat_17_math**|*float*|SAT2017|Average test score for particular state in the SAT 2017 section of "Math".|
|**sat_17_total**|*float*|SAT2017|Average total test score for particular state in the SAT 2017 examination.|
|**act_17_part**|*float*|ACT2017|Participation rate for the ACT examination in particular state in 2017.|
|**act_17_el**|*float*|ACT2017|Average test score for particular state in the ACT 2017 section of "English".|
|**act_17_math**|*float*|ACT2017|Average test score for particular state in the ACT 2017 section of "Math".|
|**act_17_read**|*float*|ACT2017|Average test score for particular state in the ACT 2017 section of "Reading".|
|**act_17_sci**|*float*|ACT2017|Average test score for particular state in the ACT 2017 section of "Science".|
|**act_17_comp**|*float*|ACT2017|Average composite score (ie. the average of the four test subjects) for particular state in the ACT 2017 examination.|
|**sat_18_part**|*float*|SAT2018|Participation rate for the SAT examination in particular state in 2018.|
|**sat_18_rw**|*float*|SAT2018|Average test score for particular state in the SAT 2018 section of "Evidence-based Reading and Writing".|
|**sat_18_math**|*float*|SAT2018|Average test score for particular state in the SAT 2018 section of "Math".|
|**sat_18_total**|*float*|SAT2018|Average total test score for particular state in the SAT 2018 examination.|
|**act_18_part**|*float*|ACT2018|Participation rate for the ACT examination in particular state in 2018.|
|**act_18_el**|*float*|ACT2018|Average test score for particular state in the ACT 2018 section of "English".|
|**act_18_math**|*float*|ACT2018|Average test score for particular state in the ACT 2018 section of "Math".|
|**act_18_read**|*float*|ACT2018|Average test score for particular state in the ACT 2018 section of "Reading".|
|**act_18_sci**|*float*|ACT2018|Average test score for particular state in the ACT 2018 section of "Science".|
|**act_18_comp**|*float*|ACT2018|Average composite score (ie. the average of the four test subjects) for particular state in the ACT 2018 examination.|

### Problem Statement

Hired by the College Board - the organization that administers the SAT, our team aims to research on how to best allocate resources in order to increase participation rates on the SAT. This is done through analysis of both ACT and SAT scores from year 2017 to 2018.

The datasets used in this project are:

ACT Scores for year 2017-2018:
- [ACT_2017](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)
- [ACT_2018](https://nces.ed.gov/programs/digest/d18/tables/dt18_226.60.asp)

SAT scores for year 2017-2018:
- [SAT_2017](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/)
- [SAT_2018](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/)

### Executive Summary 

Fierce competition exists between SAT/ACT. Primary analysis exhibits an inverse relationship in the participation rates between the two tests, particularly for states that mandating participation. Across the board, states with higher test scores generally maintain their lead from previous years. High participation rates in the test results in low scores. As a result, states with mandatory testing have lower average scores than states without.

Geographical analysis shows conclusive evidence that the SAT is popular amongst coastal states, while the ACT test is popular amongst inland states. About 20 non-coastal states have mandated ACT participation , while about 10 coastal states have mandated SAT participation. Recent successes for SAT's College board includes having been awarded two new contracts for inland states, Illinois and Colorado.

### Conclusion and Recommendations

Recommended states that the College Board might consider to focus resource allocation on for increasing SAT participation rates are South Dakota, Kansas and Iowa. Reasons for choosing these states include state exhibiting mature testing environments (from high voluntary participation) and excellent test scores. With efforts to increase SAT's presence in inland states proving successful (Colorado and Illinois), South Dakota could benefit from the recent success being geographically close to Colorado and Illinois.

Resource allocation may be channeled into the following for maximal effectiveness: 
1. Provision of SAT test subsidy.
2. Setting up campaigns alongside test subsidies to highlight key strengths of SAT
3. Improving accessibility for test takers


