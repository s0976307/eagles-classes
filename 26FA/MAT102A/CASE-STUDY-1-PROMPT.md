# MAT 102: Excel Case Study 1 — assignment prompt

> **Provenance.** Transcribed verbatim from the handout the user pasted into session on
> 2026-10-07. The original is a 5-page PDF (the paste was headed "Page 5 of 5"). This file
> is a transcription, not an official course document — if any wording matters for a
> grading dispute, check the Canvas original. No deadline, rubric, or point allocation was
> stated in the handout, and none is invented here.

**Dataset:** `SleepStudy.csv` (filed alongside this document) — 253 observations, 27 variables.

---

## Objective

At the conclusion of this case study, the student will be able to prepare statistical plots
using Excel and answer descriptive statistical questions regarding a dataset.

## Instructions

For each question, use Excel to create appropriate graphs and perform calculations to
examine the variable or relationship indicated. Remember to:

- Copy and paste **ALL** Excel plots created. You must submit these plots as part of your report.
- Compile all of your work and your Excel plots into a **single pdf file** and submit this in
  Canvas. Note: If you work in Word or Google Docs, you can print to pdf to get a pdf file
  to submit.

## This Case Study

It is believed that stress levels, alcohol use, and sleep quality affect academic
performance. We wish to examine how the 253 college students handle these problems and will
use `SleepStudy.csv` to examine possible relationships between these variables.

### Description

Data from a study of sleep patterns for college students.

### Format

A dataset with 253 observations on 27 variables. This case study uses only the following six
variables.

| Variable | Meaning |
|---|---|
| `DASScore` | Amount of depression, anxiety, and stress on a 0 (low) to 100 (high) scale. |
| `Stress` | Amount of stress coded as Normal or High |
| `LarkOwl` | Circadian preference, as Lark, Owl, or Neither |
| `AlcoholUse` | Self-reported as Abstain, Light, Moderate, or Heavy |
| `PoorSleepQuality` | A measure of sleep quality on a 0 (good) to 20 (poor) scale. |
| `CognitionZScore` | Z-score based on several cognitive skills tests |

> Note: the actual column header in the CSV is `CognitionZscore` (lowercase `s`). The handout
> spells it two other ways across the document.

### Details

A recent study examined the relationship between sleep habits, alcohol use, academic
performance, depression and stress, and other variables in US college students. The data were
obtained from a sample of students who did skills tests to measure cognitive function,
completed a survey that asked many questions about attitudes and habits, and kept a sleep
diary to record time and quality of sleep over a two-week period.

### Source

Onyper, S., Thacher, P., Gilbert, J., Gradess, S., "Class Start Times, Sleep, and Academic
Performance in College: A Path Analysis," April 2012; 29(3): 318-335. Thanks to the authors
for supplying the data.

---

## Question 1 — Circadian preference

What is the circadian preference for college students? Are they morning larks, night owls, or
neither? Use the `LarkOwl` variable to create a relative frequency distribution.

- In an empty column (which for example I'll here call AG), click on cell AG1 and type
  **Circadian Preference**. Then in AG2, AG3, and AG4, type the three categories for circadian
  preference: Lark, Owl, Neither, and then in AG5 type **Total**.
- In the next column (here AH), click on cell AH1 and type **Frequency**. In AH2, type
  `=countif(C$2:C$254,AG2)`. Copy and paste this column for AH3 and AH4. The countif, counts
  how many cells from A2 to A254 are equal to AG2. The `$` locks the row index so that it does
  not change when the cell is copied and pasted. You can also click on the square in the bottom
  right corner of the cell AG2 and drag it down to cell AG4 and it will copy and paste the
  commands into AG3 and AG4 for you.
- In cell AH5, type `=sum(AH2:AH4)`. You should now see a completed frequency distribution.
- In the next column (here AI), click on cell AI1 and type **Relative Frequency**. In cell AI2,
  type `=AH2/AH5`. In AI3, type `=AH3/AH5`, and in AI4, type `=AH4/AH5`. In AI5, find the sum
  of AI2, AI3, and AI4, using the sum command. You should now see a completed relative frequency
  distribution.

> Handout error: the second bullet says "from A2 to A254." The formula it supplies
> (`C$2:C$254`) is correct; the prose is not.

**a.** Copy and paste the entire relative frequency distribution into your report.
**b.** How many students were in this study?
**c.** In this sample of students, what proportion are Larks?
**d.** In this sample of students, what proportion are Owls?
**e.** In this sample of students, what proportion said they are Neither?
**f.** What is the sum of your relative frequencies?
**g.** Make a bar graph of the circadian preference of college students. Highlight your entire
frequency distribution by selecting AG1 through AH4. Do not highlight the total row or the
relative frequency column. Go to insert recommended charts and select the clustered column
chart. Click on the title and give it an appropriate title. Copy and paste the bar graph into
your report.
**h.** Highlight the entire frequency distribution and insert a pie chart. Click on the title
and give it an appropriate title. Copy and paste the pie chart into your report.

> Part h is ambiguous as written. Use AG1:AH4 as in part g — including the Total row makes the
> total its own pie slice.

**Context given in the handout after Q1:**

> Past studies indicate that about 10% of us are morning people (Larks) while 20% are evening
> people (Owls) and the rest aren't specifically classified as either. Studies also indicate
> that this circadian preference may not be settled until 22 years of age or later.

## Question 2 — Depression, anxiety, stress

How depressed, anxious, or stressed are college students? Use the `DASScore` data to create a
histogram. Select the DASScore column, then go to Insert Recommended Charts and click on the
Histogram. Click on the title and give it an appropriate title.

**a.** Copy and paste the histogram into your report.
**b.** What is the minimum value?
**c.** What is the maximum value?
**d.** Does the histogram look symmetric, skewed left, or skewed right?

## Question 3 — Sleep quality

How poor is the quality of students' sleep? Use the variable `PoorSleepQuality` to study this.

**a.** Find the mean using the command `average`.
**b.** Find the median using the command `median`.
**c.** Find the mode using the command `mode`.
**d.** Find the sample standard deviation using the command `stdev.s`.
**e.** Find the maximum using the command `max`.
**f.** Find the minimum using the command `min`.
**g.** Find the range.
**h.** Find Q1 and Q3 using the command `quartile`, and then find the interquartile range.
**i.** Using the formal rule for outliers discussed in class, find the lower fence for outliers.
**j.** Using the formal rule for outliers discussed in class, find the upper fence for outliers.
**k.** Are there any outliers? If so, what are they?
**l.** Draw a boxplot. Highlight the column with the data. Go to insert and find the box and
whiskers plot as one of the chart options. Cut and paste the boxplot into your report. Is this
consistent with what you found in parts a through k?

> Parts i and j reference a rule "discussed in class." No MAT 102A class notes are in this
> workspace, so the fence rule is not verified here.

## Question 4 — Stress levels and circadian preference

What is the relationship between stress levels and circadian preference? Use the variables
`Stress` and `LarkOwl` to create a side-by-side bar chart. To count rows that meet two
criteria, we can use the `countifs` (note the s at the end) function, which has syntax
`=countifs(range1, criteria1, range2, criteria2)`. We can use this to construct a two-way
table, from which we can get a side-by-side bar chart.

**a.** Copy and paste the side-by-side bar chart into your report.
**b.** What proportion of all students in the sample report a high level of stress?
**c.** What proportion of those with high stress are Larks?
**d.** Give the proportion reporting a high level of stress in each of the three circadian
preference groups.
**e.** Which group has the lowest proportion reporting a high level of stress?

## Question 5 — Alcohol use and cognition

What is the relationship between alcohol use and cognition? Use the variables
`CognitionZScores` and `AlcoholUse` to create side-by-side boxplots.

**a.** Copy and paste the side-by-side boxplots into your report.
**b.** What proportion of these students are heavy drinkers?
**c.** Which alcohol group, if any, has an outlier?
**d.** Which alcohol use group has the highest mean cognitive score?
**e.** Which group has the lowest mean cognitive score?
**f.** Can we conclude that heavy drinking causes a reduction in cognitive skills? Why or why not?
**g.** Does there appear to be a strong association between the two variables? Discuss.

## Question 6 — Summarize your findings

A key skill in statistical analysis is summarizing your findings. Go back and look at the above
questions and pick out the most important/interesting result from each. Create a properly
formatted paragraph or two reporting on your work.

---

## Source abstract (reproduced in the handout)

**Chronobiol Int.** 2012 Apr;29(3):318-35. doi: 10.3109/07420528.2012.655868.
**Class start times, sleep, and academic performance in college: a path analysis.**
Onyper SV, Thacher PV, Gilbert JW, Gradess SG.

Path analysis was used to examine the relationship between class start times, sleep, circadian
preference, and academic performance in college-aged adults.

- Consistent with observations in middle and high school students, college students with later
  class start times slept longer, experienced less daytime sleepiness, and were less likely to
  miss class.
- Chronotype was an important moderator of sleep schedules and daytime functioning; those with
  morning preference went to bed and woke up earlier and functioned better throughout the day.
- The benefits of taking later classes did not extend to academic performance, however; grades
  were somewhat lower in students with predominantly late class schedules.
- Furthermore, students taking later classes were at greater risk for increased alcohol
  consumption, and among all the factors affecting academic performance, alcohol misuse exerted
  the strongest effect.

Thus, these results indicate that later class start times in college, while allowing for more
sleep, also increase the likelihood of alcohol misuse, ultimately impeding academic success.

> This abstract is the intended source for Q5f. It names a confounder — later class start times
> raise both alcohol misuse and other outcomes — which is the specific mechanism that makes the
> causal claim in 5f unsupportable.

---

## Companion files in this folder

| File | Holds |
|---|---|
| `SleepStudy.csv` | Source data, 253 rows × 27 columns |
| `SleepStudy-CaseStudy1.xlsx` | Structural skeleton — staging blocks, labels, empty formula cells |
| `CASE-STUDY-1-SCAFFOLD.html` | Visual scaffold: formulas, reasoning, traps, chart checklist |
| `CASE-STUDY-1-SCAFFOLD.md` | Same content as plain markdown |

## Not stated in the handout — do not assume

- Due date and time.
- Late penalty.
- Point allocation or rubric weighting.
- Whether AI assistance is permitted in MAT 102A. (A verbal allowance was given in **CIS 350A**
  by Prof. Inomoto on 2026-10-07. That does not transfer to this course.)
