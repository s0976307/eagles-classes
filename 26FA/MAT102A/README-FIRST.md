# MAT 102A — transfer payload

Staged 2026-10-07 from `%USERPROFILE%\Desktop\MAT 102A\` on the school machine.
Destination: `<Desktop>\MAT 102A\` on the Beelink.

## Run order — this matters

```
1.  E:\CIS350A-TRANSFER\SETUP-BEELINK.ps1 -DryRun   then without -DryRun
2.  E:\MAT102A-TRANSFER\SETUP-MAT102A.ps1 -DryRun   then without -DryRun
```

**Why that order.** This payload carries **coursework only** — no doctrine, no skills, no
project memory. The MAT 102A operating context (`mat102a-second-course.md`,
`skill-assignments-user-does-the-work.md`) lives inside the **CIS 350A `Prep` project
memory**, because that is the shell these sessions ran in. `SETUP-BEELINK.ps1` is what
places it, and it reslugs the memory folder for the Beelink's own path — the step that
silently breaks when done by hand.

Run this one first and you get seven files with no MAE context attached to them.

`SETUP-MAT102A.ps1` checks for both of those prerequisites and warns rather than failing,
so you can still install the files if you only want the files.

## Why this is a sibling of CIS350A-TRANSFER, not inside it

MAT 102A is a separate course and lives outside the CIS 350A folder on the source machine
(`Desktop\MAT 102A\`, not `Desktop\Intro Systm Analysis 26FA-CIS350A\`). Filing it under
`CIS350A-TRANSFER\course\` would put stats material inside a tree named for a different
course and would blur the two shells. The layout here mirrors the source machine.

**No memory snapshot is duplicated into this folder on purpose.** A second copy of the
`Prep` memory on the same drive would be a second source of truth, and the stale one always
wins by accident.

## Payload

| File | What it is |
|---|---|
| `coursework\SleepStudy.csv` | Source data — 253 observations, 27 variables |
| `coursework\SleepStudy-CaseStudy1.xlsx` | **Structural skeleton.** Staging blocks, labels, empty yellow formula cells. No formulas, no charts |
| `coursework\CASE-STUDY-1-PROMPT.md` | Assignment prompt, transcribed from the handout 2026-10-07 |
| `coursework\CASE-STUDY-1-SCAFFOLD.html` | Visual scaffold — formulas, reasoning, traps, chart checklist |
| `coursework\CASE-STUDY-1-SCAFFOLD.md` | Same content, plain markdown |
| `coursework\MAT-102A-TEST-1-AID.html` | Test 1 study aid (pre-existing, not reviewed this session) |
| `coursework\case study one notes.txt` | **Not authored or read this session.** Copied as found, 85 KB |

## The workbook is deliberately incomplete

`SleepStudy-CaseStudy1.xlsx` has **zero formulas and zero charts**. That is not an export
failure. The case study's stated objective is *"the student will be able to prepare
statistical plots using Excel and perform calculations"* — the Excel work is the graded
skill, so the structure travels and the work does not. Formulas are documented in
`CASE-STUDY-1-SCAFFOLD.html` (click-to-copy); you join the two.

Confirmed by the user 2026-10-07 as a learning-goal preference, not a policy limit. It holds
even where a course permits AI assistance.

## Not known for MAT 102A — do not assume

- Due date, time, late penalty.
- Rubric or point allocation.
- Whether AI assistance is permitted. A verbal allowance was given in **CIS 350A** by
  Prof. Inomoto on 2026-10-07. **It does not transfer to this course.**
- The outlier-fence rule "discussed in class." The scaffold assumes 1.5×IQR and labels it
  as an assumption in both the HTML and in cell `AN24` of the workbook.

## Drive note

`E:\MAE\` is the offline MAE Bunker — model weights, llama.cpp engine, its own doctrine
tree. **Unrelated to this payload and untouched.** Do not point `SETUP-MAT102A.ps1` at it.

The drive is exFAT, so file timestamps round to the nearest two seconds. A one- or
two-second difference between source and drive is granularity, not drift — the setup
script verifies by SHA256 hash rather than by timestamp for that reason.
