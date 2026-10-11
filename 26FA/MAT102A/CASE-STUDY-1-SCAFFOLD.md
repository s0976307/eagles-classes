# MAT 102A — Excel Case Study 1: Scaffold & Reasoning

**Dataset:** `SleepStudy.csv` — 253 data rows (rows 2–254), 27 columns (A–AA). Verified 2026-09-30.
**Deliverable:** single PDF, all plots pasted in, submitted in Canvas.

> This file is a **blueprint**. It gives you the cell layout, the formulas, and the
> reasoning each question is testing. It does not contain the answers — you run Excel,
> you read the output, you write the interpretation. Bring your numbers back for a check.

---

## 0. Setup

### Column map (you need these; the handout only gives you C)

| Variable | Column | Type |
|---|---|---|
| LarkOwl | **C** | categorical (Lark / Owl / Neither) |
| CognitionZscore | **H** | quantitative (z-score) |
| PoorSleepQuality | **I** | quantitative (0–20, integer) |
| Stress | **O** | categorical (`normal` / `high`) |
| DASScore | **P** | quantitative (0–100) |
| AlcoholUse | **R** | categorical, **ordinal** (Abstain < Light < Moderate < Heavy) |

Last data column is `AA`. Everything from `AC` rightward is free staging space.

### Staging-block plan (keeps the five questions from colliding)

| Block | Columns | Holds |
|---|---|---|
| Q1 | AG:AI | circadian frequency + relative frequency |
| Q2 | AK:AL | DASScore min/max/mean/median |
| Q3 | AN:AO | PoorSleepQuality descriptive battery |
| Q4 | AQ:AU | Stress × LarkOwl two-way table + proportions |
| Q5 | AW:AX, BB:BE | boxplot staging + group stats |

### Two data notes before you start

1. **Case.** The `Stress` column contains `normal` and `high` in **lowercase**. `COUNTIF`
   and `COUNTIFS` are case-insensitive, so typing `High` in your table label still matches.
   No problem — just don't be surprised when the spellings differ.
2. **Handout typo.** Q1 bullet 2 says the formula "counts how many cells from A2 to A254."
   Wrong — the formula it gives you (`C$2:C$254`) is correct. Trust the formula.

---

## Q1 — Circadian preference (relative frequency distribution)

### Reasoning first

`LarkOwl` is **categorical**. You cannot take a mean of "Lark." The only meaningful
summaries are **counts** and **proportions**, which is exactly why the question asks for a
frequency distribution rather than a mean.

The two paragraphs the handout drops *after* Q1 are not decoration — they're the
interpretive setup:

- Past studies: ~10% Lark, ~20% Owl, ~70% Neither.
- Circadian preference "may not be settled until 22 years of age or later."

So when you compare your sample proportions to those benchmarks, the second fact is your
explanation for any excess of "Neither" in a college-age sample. **That comparison is one
of your strongest candidates for the Q6 summary.** Q1 by itself is just counting; the
comparison is the statistics.

### Scaffold

| Cell | Content |
|---|---|
| AG1 | `Circadian Preference` |
| AG2 | `Lark` |
| AG3 | `Owl` |
| AG4 | `Neither` |
| AG5 | `Total` |
| AH1 | `Frequency` |
| AH2 | `=COUNTIF($C$2:$C$254,AG2)` |
| AH3:AH4 | fill AH2 down |
| AH5 | `=SUM(AH2:AH4)` |
| AI1 | `Relative Frequency` |
| AI2 | `=AH2/$AH$5` |
| AI3:AI4 | fill AI2 down |
| AI5 | `=SUM(AI2:AI4)` |

**Why the `$` in `$AH$5`:** the handout has you retype `=AH3/AH5` and `=AH4/AH5` by hand.
Anchoring the denominator with `$AH$5` lets you fill down instead, and it's the habit that
prevents errors later in Q4 where you fill in two directions at once.

**Self-check:** `AH5` must read **253**. `AI5` must read **1** (or 100% — it may display
0.999999 before formatting; that's floating point, not an error).

### Charts

- **1g bar chart** — select `AG1:AH4`. Insert → Recommended Charts → Clustered Column.
  *Not* the Total row, *not* the relative-frequency column.
- **1h pie chart** — select `AG1:AH4` again. **The handout says "the entire frequency
  distribution" here, which is ambiguous and will bite you.** If you include `AG5:AH5`, the
  Total becomes its own slice and eats half the pie. Same range as 1g.
- Retitle both. "Chart Title" left as-is costs points on any rubric.

### Answering a–f

Read them straight off the table. For c/d/e, give the **proportion** (decimal or %),
not the count — the question says proportion.

---

## Q2 — DASScore histogram

### Reasoning first

`DASScore` is quantitative, so now shape, center, and spread are all on the table. A
histogram answers **shape**.

Predict before you plot: DASScore is bounded below at 0 and most college students are not
severely distressed. A hard floor with room to run upward almost always produces a
**right skew** (long tail toward high values). Plot it and see whether that holds.

**Skew vocabulary trap:** skew is named for the direction of the *tail*, not where the
bulk of the data sits. A pile-up on the left with a tail stretching right is skewed
**right**, even though it "leans left" visually.

### Scaffold

| Cell | Content |
|---|---|
| AK1 | `DASScore` |
| AK2 | `Minimum` → AL2 `=MIN($P$2:$P$254)` |
| AK3 | `Maximum` → AL3 `=MAX($P$2:$P$254)` |
| AK4 | `Mean` → AL4 `=AVERAGE($P$2:$P$254)` |
| AK5 | `Median` → AL5 `=MEDIAN($P$2:$P$254)` |

**Get 2b/2c from `MIN`/`MAX`, not from the histogram's axis.** Excel picks round bin edges,
so the leftmost bin might start at 0 when your true minimum is something else, and the
rightmost bin will overshoot your true maximum. The chart is for shape; the formulas are
for values.

**Mean vs. median is your skew confirmation** (rows AL4/AL5):

- mean > median → pulled right by a long right tail → **skewed right**
- mean ≈ median → **roughly symmetric**
- mean < median → **skewed left**

This is a cross-check on your eyeball reading of 2d, not a replacement for it. If the
chart and the mean/median disagree, something is wrong — tell me.

### Chart

Select column P (header included) → Insert → Recommended Charts → Histogram. Retitle.

---

## Q3 — PoorSleepQuality descriptive battery

### Reasoning first

This is the full toolkit on one variable: **center** (mean, median, mode), **spread**
(SD, range, IQR), **position** (quartiles), **unusual values** (fences, outliers), and then
a boxplot that should visually reproduce everything you just computed. Part (l) — "is this
consistent with a–k" — is the actual point of the question. You are being asked to verify
that a picture and a table tell the same story.

### Scaffold

Labels in AN, formulas in AO.

| Row | AN (label) | AO (formula) |
|---|---|---|
| 1 | `PoorSleepQuality` | `Value` |
| 2 | `Mean` | `=AVERAGE($I$2:$I$254)` |
| 3 | `Median` | `=MEDIAN($I$2:$I$254)` |
| 4 | `Mode` | `=MODE($I$2:$I$254)` |
| 5 | `StDev (sample)` | `=STDEV.S($I$2:$I$254)` |
| 6 | `Maximum` | `=MAX($I$2:$I$254)` |
| 7 | `Minimum` | `=MIN($I$2:$I$254)` |
| 8 | `Range` | `=AO6-AO7` |
| 9 | `Q1` | `=QUARTILE($I$2:$I$254,1)` |
| 10 | `Q3` | `=QUARTILE($I$2:$I$254,3)` |
| 11 | `IQR` | `=AO10-AO9` |
| 12 | `Lower fence` | `=AO9-1.5*AO11` |
| 13 | `Upper fence` | `=AO10+1.5*AO11` |
| 14 | `# below lower fence` | `=COUNTIF($I$2:$I$254,"<"&AO12)` |
| 15 | `# above upper fence` | `=COUNTIF($I$2:$I$254,">"&AO13)` |

For **3k — "if so, what are they"** you need the actual values, not just a count. Pull the
largest values down and compare each to your upper fence:

| Cell | Content |
|---|---|
| AN17 | `Largest values` |
| AO17 | `=LARGE($I$2:$I$254,1)` |
| AO18 | `=LARGE($I$2:$I$254,2)` |
| AO19 | `=LARGE($I$2:$I$254,3)` |

Fill down until a value drops below your upper fence — everything above the fence is an
outlier, and you list those. Mirror with `SMALL(...)` if `AO14` is nonzero.

### Four traps in this block

1. **`STDEV.S` vs `STDEV.P`.** The question says *sample* standard deviation. `STDEV.S`
   divides by n−1. `STDEV.P` divides by n and is the wrong answer here.
2. **`MODE` returns only one value.** If two values tie for most frequent, Excel silently
   reports whichever appears first in the column. Worth a sentence in your writeup if you
   suspect a tie. (If nothing repeated at all, `MODE` would return `#N/A` — not an issue
   with 253 integer scores on a 0–20 scale, but that's what the error would mean.)
3. **`QUARTILE` may not match your hand calculation.** Excel's `QUARTILE` (= `QUARTILE.INC`)
   interpolates between data points. Many intro courses teach "median of the lower half,"
   which is `QUARTILE.EXC`-like and can give a different number. **The assignment tells you
   to use `QUARTILE`, so use `QUARTILE`** — but if your class notes define quartiles the
   other way, say so in one line so the grader knows you noticed rather than blundered.
4. **The fence rule.** *Inference, not verified for this course:* the standard formal rule
   is `Q1 − 1.5×IQR` and `Q3 + 1.5×IQR`, which is what the scaffold above uses. Confirm
   against your class notes before you commit — the question says "the formal rule
   discussed in class," and I have no MAT 102A notes to verify against.

### Boxplot (3l)

Select column I (header included) → Insert → Charts → Statistical → Box and Whisker.

**Turn on the outlier points.** Right-click the box → Format Data Series → check
**Show outlier points** (and **Show mean markers**, which lets you see mean vs. median
in one glance). Excel does not always enable these by default, and without them you
cannot answer 3l honestly.

**What "consistent" means for your writeup — check all four:**

- Box bottom = your `Q1`, box top = your `Q3`, line inside = your `Median`.
- Whisker ends stop at the most extreme values *inside* the fences — not at min/max.
- The plotted outlier dots match exactly the values you listed in 3k.
- Mean marker sits above the median line if the data is right-skewed. Compare to `AO2`/`AO3`.

---

## Q4 — Stress × Circadian preference (two-way table)

### Reasoning first

Two categorical variables. The question "is there a relationship" becomes: **does the
proportion reporting high stress change depending on circadian group?** If all three groups
report high stress at about the same rate, there's no association. If they differ
substantially, there is.

**This is the question students lose points on, and here is exactly why.** Parts b, c, and
d all ask for "a proportion" but use three different denominators:

| Part | Numerator | Denominator | Name |
|---|---|---|---|
| **4b** | all high-stress students | **253** (everyone) | marginal proportion |
| **4c** | Lark **and** high stress | all **high-stress** students | conditional on *stress* |
| **4d** | Lark **and** high stress | all **Larks** | conditional on *circadian group* |

4c and 4d have the *same numerator* and different denominators, so they give different
numbers. If you can say out loud why "the proportion of high-stress students who are Larks"
and "the proportion of Larks who are high-stress" are different questions, you have the
skill this question tests. Only **4d** answers "is there a relationship" — it holds the
group fixed and compares stress rates across groups.

### Scaffold — the table

|  | AQ | AR | AS | AT | AU |
|---|---|---|---|---|---|
| **1** | *(leave blank)* | `Lark` | `Owl` | `Neither` | `Total` |
| **2** | `high` | formula ↓ | | | `=SUM(AR2:AT2)` |
| **3** | `normal` | | | | `=SUM(AR3:AT3)` |
| **4** | `Total` | `=SUM(AR2:AR3)` | | | `=SUM(AR4:AT4)` |

`AR2` = `=COUNTIFS($O$2:$O$254,$AQ2,$C$2:$C$254,AR$1)`

Then fill `AR2` right to `AT2` and down to row 3 — all four count cells come from that one
formula.

**The mixed references are the lesson here.** `$AQ2` locks the *column* (row labels always
come from AQ) but lets the row float. `AR$1` locks the *row* (column headers always come
from row 1) but lets the column float. That's what makes one formula fill in two directions.
Get this and two-way tables stop being tedious.

**Self-check:** `AU4` must be **253**. Also confirm `=SUM(AU2:AU3)` equals `=SUM(AR4:AT4)` —
summing the margins two different ways is a free error check.

### Scaffold — the three proportions

| Cell | Content | Answers |
|---|---|---|
| AQ6 | `4b: P(high stress)` → AR6 `=AU2/$AU$4` | 4b |
| AQ7 | `4c: P(Lark given high)` → AR7 `=AR2/$AU$2` | 4c |
| AQ8 | `4d: P(high given group)` → AR8 `=AR2/AR$4`, fill right to AT8 | 4d, 4e |

For **4e**, read the smallest of the three values in `AR8:AT8`.

### Chart (4a)

Select `AQ1:AT3` — the counts only, no Total row, no Total column. Insert → Clustered Column.

- **"Side-by-side" means clustered, not stacked.** If your bars sit on top of each other,
  you picked the wrong subtype.
- Excel guesses which variable becomes the category axis and which becomes the series.
  If it guesses wrong, use **Chart Design → Switch Row/Column**. For answering 4d, you
  want **circadian group on the axis** with high/normal as the two series, so the three
  groups sit side by side for comparison.
- Retitle. Add a legend if Excel dropped it.

### One caution worth writing down

Check your `AR4` (number of Larks) before you lean on 4e. If that group is small, its high-
stress proportion is computed from few students and is unstable — a couple of different
students would move it noticeably. Naming that limitation is a better answer than stating
the winner with false confidence. The handout's own "~10% are Larks" benchmark should tell
you what to expect here.

---

## Q5 — Alcohol use vs. cognition

### Reasoning first

One categorical variable (`AlcoholUse`, and note it's **ordinal** — the categories have a
natural order) against one quantitative variable (`CognitionZscore`). Side-by-side boxplots
are the right display: one box per alcohol group, compared on a shared axis.

`CognitionZscore` is a **z-score**, which is doing you a favor: it's already standardized,
so 0 is roughly average cognitive performance and the units are standard deviations. A
difference of 0.1 between group means is small. A difference of 0.8 is large. You don't
need extra context to judge magnitude.

**5f is the most important question on the page.** The answer is no, and the reason has a
name. This is an **observational study** — students self-reported their drinking; nobody
randomly assigned anyone to drink heavily. So the groups differ in many ways besides
alcohol, and any of those could produce a cognition difference. That's **confounding**.

The abstract printed at the bottom of your handout hands you a concrete confounder: students
with later class start times were *both* more likely to misuse alcohol *and* different in
sleep and academic outcomes. Class schedule is a plausible common cause sitting behind both
variables. Naming a specific mechanism beats reciting "correlation is not causation."

There's a second point worth a clause: **reverse causation** is not ruled out either.
Nothing in this design establishes that drinking came before the cognitive difference.

### Scaffold — boxplot staging (AW:AX)

Excel's Box and Whisker chart will group for you **if** you hand it a category column
immediately left of a value column. `AlcoholUse` (R) and `CognitionZscore` (H) are not
adjacent and are in the wrong order, so copy them into a clean two-column block:

| Cell | Content |
|---|---|
| AW1 | `AlcoholUse` |
| AX1 | `CognitionZscore` |
| AW2 | `=$R2` |
| AX2 | `=$H2` |
| AW2:AX254 | fill both down to row 254 |

Then select `AW1:AX254` → Insert → Charts → Statistical → Box and Whisker.

**Again: Format Data Series → Show outlier points.** Question 5c asks which group has an
outlier. Without that checkbox on, the plot cannot answer it.

*Optional polish:* Excel will order the four boxes alphabetically (Abstain, Heavy, Light,
Moderate), which scrambles the natural Abstain → Light → Moderate → Heavy progression. If
you want them in order, paste `AW:AX` as values, add a helper column numbering the groups
1–4, and sort by it. Not required, but an ordinal variable displayed out of order slightly
undercuts the trend you're describing in 5g.

### Scaffold — group statistics (BB:BE)

| Row | BB (group) | BC (`n`) | BD (proportion) | BE (mean z) |
|---|---|---|---|---|
| 1 | `AlcoholUse` | `n` | `Proportion` | `Mean CognitionZscore` |
| 2 | `Abstain` | `=COUNTIF($R$2:$R$254,BB2)` | `=BC2/$BC$6` | `=AVERAGEIF($R$2:$R$254,BB2,$H$2:$H$254)` |
| 3 | `Light` | fill down | fill down | fill down |
| 4 | `Moderate` | | | |
| 5 | `Heavy` | | | |
| 6 | `Total` | `=SUM(BC2:BC5)` | `=SUM(BD2:BD5)` | — |

**Self-check:** `BC6` = 253, `BD6` = 1. If `BC6` is short of 253, a category label is
misspelled or there's a fifth category you didn't account for.

- **5b** → the `Heavy` row of column BD.
- **5c** → read the boxplot (outlier points must be enabled).
- **5d / 5e** → highest and lowest values in `BE2:BE5`.

### 5g — "strong association?" How to judge it

Don't guess. Use two comparisons:

1. **Spread of the group means vs. the spread within groups.** Your four means live in
   `BE2:BE5`. If the gap between the highest and lowest is small compared to the height of
   a typical box on your chart, the association is weak — alcohol group barely moves
   cognition relative to how much students within a single group already differ.
2. **Box overlap.** If all four boxes overlap heavily on the vertical axis, knowing a
   student's alcohol group tells you almost nothing about their cognition score. Clear
   separation would mean a strong association.

Then connect it back: **a weak association makes the 5f answer even easier.** You can't
claim causation from an observational study regardless — but it's especially unwarranted
when the association itself is small. Note also that `Heavy` is likely the smallest group
(check `BC5`), so whatever you observed about it in 5c/5d rests on few students.

---

## Q6 — Summary paragraph

The instruction is one important finding per question. **Don't re-narrate the whole case
study** — this is a results paragraph, not a walkthrough. What to pull:

| From | The finding worth reporting |
|---|---|
| Q1 | Sample circadian breakdown **compared to** the 10%/20% benchmark, with the age explanation |
| Q2 | Shape of the distress distribution and what it implies about typical vs. extreme students |
| Q3 | Center and spread of sleep quality, plus whether outliers exist and what they represent |
| Q4 | Whether high-stress rates differ by circadian group — the **4d** numbers, with the small-group caution |
| Q5 | Direction and **size** of the cognition difference across alcohol groups, plus the explicit no-causation statement |

Rules for the prose:

- Every claim carries its number. "Most students were Neither" is weak; the proportion is the finding.
- **Association language only.** "Higher alcohol use was associated with lower mean cognition
  scores" — never "led to," "caused," "reduced," or "affected."
- Name a limitation. Observational design, self-reported drinking and stress, single
  institution, small subgroups. One sentence is enough and it reads as competence.
- Past tense, third person, no "I clicked Insert → Chart."

---

## Execution order (so you don't rework)

1. Open the CSV, immediately **Save As `.xlsx`** — `.csv` will not retain your charts or formulas.
2. Build all five staging blocks and confirm every self-check total (253 three times, 1 twice).
3. Only then build charts. A chart pointed at a broken table has to be rebuilt from scratch.
4. Enable **Show outlier points** on both boxplots (Q3 and Q5) before screenshotting.
5. Retitle every one of the six charts.
6. Paste into Word, answer a–g under each, write Q6 last.
7. Print to PDF. Confirm all six charts actually rendered in the PDF — pasted-as-object
   charts sometimes drop.

## Chart inventory (6 total — verify before submitting)

- [ ] Q1g clustered column — circadian frequency
- [ ] Q1h pie — circadian frequency
- [ ] Q2a histogram — DASScore
- [ ] Q3l box and whisker — PoorSleepQuality
- [ ] Q4a clustered column — stress × circadian
- [ ] Q5a box and whisker — cognition by alcohol group

## Unverified for this course

- The exact outlier-fence rule "discussed in class" (scaffold assumes 1.5×IQR).
- Quartile convention taught (scaffold uses Excel's `QUARTILE` per the handout's instruction).
- Rubric weighting and late policy — no MAT 102A syllabus in this workspace.

Confirm the first two against your notes before you finalize Q3.
