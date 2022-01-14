### Content
- [Background](#Background)
- [Problem Statement](#Problem-Statement)
- [Data Dictionary](#Data-Dictionary)
- [Summary of Analysis](#Summary-of-Analysis)
- [Conclusions](#Conclusions)
- [Recommendations](#Recommendations)


### Background
The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

<br>

The SAT has 2 compulsory sections which cover the following content and skills ([*source*](https://www.studypoint.com/ed/the-sat/)) and the total score is the sum of the sections scores ([*source*](https://collegereadiness.collegeboard.org/sat/scores/understanding-scores/interpreting)).

|Section|Content & Skills|Section Score|
|:---|:---|:---:|
|Evidence-Based Reading and Writing|Reading - Reading and vocabulary in context<br>Writing - Grammer and usage|200 - 800|
|Math|Heart of algebra<br>Problem solving<br>Data analysis Passport to advanced math<br>Additional topics (geometry, trigonometry and pre-calculus)|200 - 800|

<br>


The ACT on the other hand has 4 compulsory sections convering the following content and skills ([*source*](https://www.studypoint.com/ed/the-act-test/)) and the composite score is the average of the 4 compulsory sections ([*source*](https://blog.prepscholar.com/how-is-the-act-scored)).


|Section|Content & Skills|Section Score|
|:---|:---|:---:|
|English|Grammar & usage<br>Punctuation<br>Sentence structure<br>Strategy<br>Organization<br>Style|1 - 36|
|Reading|Reading comprehension of what is directly stated or implied|1 - 36|
|Math|Pre-algebra<br>Elementary algebra<br>Intermediate algebra<br>Coordinate geometry<br>Plane geometry<br>Trigonometry|1 - 36|
|Science|Interpretation<br>Analysis<br>Evaluation<br>Reasoning<br>Problem solving|1 - 36|

<br>

Note: Both SAT and ACT have optional essay/writing which is not mentioned above.

<br>

However in 2016, SAT underwent a major restructuring in its format and scoring system ([*source*](https://www.studypoint.com/ed/sat-history/)). Few examples of the changes made are:-
- Decrease number of sections from 3 to 2
    - Combined reading and writing into one section called “Evidence-Based Reading and Writing”
- Total maximum score is decreased from 2400 to 1600
- No penalty for guessing the answer

<br>

### Problem Statement
With the SAT major restructing in its format and scoring system in 2016, the ACT management team are concerned that the ACT participation rate and reputation might have been negatively affected. Being an analyst working in ACT, you are tasked by your supervisor to conduct a study to find out the following and make recommendations based on your findings:-

- How has the ACT and SAT participation rate changed between 2017 to 2019?
- Which states are pro ACT or SAT?
- Are students scoring higher for SAT compared to ACT?

<br>

### Data Dictionary
Below are the data dictionary of the features used in the analysis.

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|act_2017<br>act_2018<br>act_2019|Name of state where the data is collected from|
|participation_act|float|act_2017<br>act_2018<br>act_2019|State participation rate in ACT|
|composite|float|act_2017<br>act_2018<br>act_2019|ACT composite score|
|year|int|act_2017<br>act_2018<br>act_2019|Year which the test was held|
|participation_sat|float|sat_2017<br>sat_2018<br>sat_2019|State participation rate in SAT|
|ebrw_sat|int|sat_2017<br>sat_2018<br>sat_2019|Score from evidence based reading<br> and writing component of SAT|
|math_sat|int|sat_2017<br>sat_2018<br>sat_2019|Score from math component of SAT|
|total_sat|int|sat_2017<br>sat_2018<br>sat_2019|SAT Total Score|
|composite_act_normalized|float|Derived from composite_act|Normalised score of ACT|
|total_sat_normalized|float|Derived from total_sat|Normalised score of SAT|
|avg_score|float|Derived from<br> composite_act_normalized <br> & total_sat_normalized|Average normalised score of ACT and SAT|

<br>

### Summary of Analysis

#### How has the ACT and SAT participation rate changed between 2017 to 2019?
<img src="img/act_and_sat_participation_rate_by_year.png">
The ACT participation rate had decreased by ~8% from 2017 to 2019 while SAT participation rate had increased by ~10% during the same period. However, during these 3 years, both ACT and SAT were seeing a larger spread in their participation rates where ACT were seeing more states with lower participation rate, whereas SAT were seeing more states with higher participation rate.


<br>
<br>
<img src='img\state_participation_rate_by_year.png'>
During the 3 years, 18 states had very high ACT participation rate (greater than 90%) as compared to 10 states for SAT. For the majority of the remaining states, they did not show overwhelming bias for either of the tests.


<br>
<br>

#### Which states are pro ACT or SAT?
<img src="img/top_25_states_act_participation.png">
ACT has 13 states with average of 100% participation rate from 2017 to 2019. Example of the top 5 states with 100% participation rate are Alabama, Kentucky, Wisconsin, Utah and Tennessee.

<br>
<br>

<img src="img/top_25_states_sat_participation.png">
SAT only had 3 states with average of 100% participation rate from 2017 to 2019. Example of the top 5 states are Michigan, Connecticut and Delaware with 100% participation rate followed by Idaho and Maine with average of 97% participation rate.

<br>
<br>

#### Are students scoring higher for SAT compared to ACT?
As it is not possible to directly compare ACT score to SAT, both ACT and SAT scores were normalized by dividing the scores with their maximum possible score (36 for ACT and 1600 for SAT). For example, ACT score of 20 would be 0.55 after normalization while SAT score of 1400 would be 0.875 where 1 is the full score in both instances.
<br>
<br>
<img src='img/normalized_act_and_sat_score_by_year.png'>
In all 3 years, the normalized scores for ACT and SAT have remained fairly stable where SAT has higher normalized score than ACT (ACT: ~0.6 vs SAT: ~0.7).
<br>
<br>
<img src='img/state score by year.png'>
Comparing ACT and SAT normalized score trend across the 3 years, most states' ACT and SAT score have remained fairly stable. Among the 51 states, only less than 10 states have ACT score consistently higher than SAT score.

<br>
<br>


### Conclusions
In summary, with the change in SAT format in 2016, ACT was adversely affected as their yearly average participation rate had decline from 2017 to 2019. This is evident as some states had clearly opted for SAT over ACT given the sharp decline in ACT participation rate in 4 states, namely Colorado, Illinois, South Carolina and West Virginia. However, despite the declining participation rate, ACT still had overwhelming support from more states as compared to SAT.

On the other hand, when comparing the normalized scores of ACT and SAT, it is evident that students were scoring less points on ACT as compared to SAT.



### Recommendations

Given that the goal of the students is to score as high as possible in the standard test coupled with the average participation rate for ACT declining from 2017 to 2019 and examinees scoring worst in ACT for most states, it would be advisable for the management team to consider restructuring the format to remain competitive with SAT.

In the short term, they could encourage states with low to mid SAT participation rate like Alaska, Arizona, California, Oregon and etc, to have their students participate in ACT tests as those states do not exhibit a preference for either test and should be easier to persuade.