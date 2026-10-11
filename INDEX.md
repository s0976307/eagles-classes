# EAGLES CLASSES, school index

**Institution:** Niagara University (Purple Eagles)
**Scheme adopted:** 2026-10-08
**Status:** [ECHO:GOLD] verified against disk by SHA-256, not from memory

---

## The scheme

```
Projects\EAGLES CLASSES\
├── CLAUDE.md          school shell doctrine, scoped to this tree only
├── INDEX.md           this file
├── TERM-MAPPING.md    how every older file got its term, and the evidence
├── 26FA\              current term, one folder per semester
│   ├── CIS350A\       Intro Systems Analysis
│   ├── MAT102A\       Statistics
│   └── HIST\          HIS 110 C
├── 26SP\              Spring 2026, 11 files
├── 25FA\              Fall 2025, 3 files
├── _ADMIN\            student records, kept private
└── _INFLIGHT\         AI forensics paper, ALPR paper, notebooks
```

**Term folders are `<YY><FA|SP|SU>`.** Underscore-prefixed folders are deliberately not
terms: `_ADMIN` holds records that outlive any semester, `_INFLIGHT` holds work whose term
was never established. Both sort to the bottom, which is where they belong.

Older files were filed on **2026-10-08 from timestamp evidence, not from a transcript.**
Every inference is logged in `TERM-MAPPING.md` with what it was based on. Correct any row
and move the file. The transcript would settle most of them and sits in `_ADMIN`, unreadable
here only because poppler is not installed.

### On the drive

The whole scheme is staged at `<drive>\SCHOOL\26FA\` on the MAE Bunker USB, 147 files,
280.8 MB, every file SHA-256 verified. `<drive>\SCHOOL\_TEMPLATE\STAGE-TERM.ps1` builds the
next term section in the same shape:

```powershell
cd <drive>\SCHOOL\_TEMPLATE
.\STAGE-TERM.ps1 -Term 27SP -DryRun
.\STAGE-TERM.ps1 -Term 27SP
```

Restoring onto any machine is `SCHOOL\<term>\SETUP-TERM.ps1`. Neither script touches
`~/.claude`, so neither can overwrite doctrine the way the original transfer did. See
`SCHOOL\README-FIRST.md` on the drive.

**One folder per semester.** Spring 2027 becomes `27SP\` beside `26FA\`, so a finished
semester stops competing for attention with a live one. Course folders keep their short
codes rather than full titles, because path length is a live hazard in this tree. See
"Path length" below.

**Why under `Projects\`.** `PROJECTS-INDEX.md` sweeps this tree. School now gets tracked
the same way every other build target is, instead of sitting on the Desktop unindexed.
This filled the `EAGLES CLASSES` shell that had been empty since 2026-08-21. The typo
twin `clalles` was deleted the same day on the Commander's call.

---

## Courses, Fall 2026

| Course | Path | Files | What it is |
|---|---|---|---|
| **CIS 350A** | `26FA\CIS350A\` | 95 | Intro Systems Analysis and Design, Prof. Inomoto. Carries the student shell (`Prep\`), instructor shell (`AIB\`), 8 lecture decks, 6 study guides, and the Spurrier/Topi textbook. The only course with Claude project memory. |
| **MAT 102A** | `26FA\MAT102A\` | 8 | Statistics. Case Study 1 on the SleepStudy dataset. Coursework only, no doctrine and no memory of its own. |
| **HIS 110 C** | `26FA\HIST\` | 12 | Fall 2026 history. Two presidential biographies, book summaries, test sheets, Miller Center summaries. Files only. |

---

## Where the work actually stands

Source: `26FA\CIS350A\HOMEWORK-STATUS.md`, snapshot 2026-10-07 19:20. **Verify in Canvas
before acting.**

| Due | Item | Status |
|---|---|---|
| Sat 2026-09-19 | A#1 Activity diagram | owed, late penalty cleared, unstarted |
| Sat 2026-09-26 | A#2 ER diagram | owed, late penalty cleared, unstarted |
| Wed 2026-10-07 | Exam #1 | submitted, 27/30 |
| **Sat 2026-10-10** | **A#3 User story** | **next, unstarted** |
| Sat 2026-10-24 | A#4 UI wireframe | prompt captured |

> **The clock risk became a completion risk.** Prof. Inomoto cleared the late penalty in
> person on 2026-10-07. An extension removes the deduction; it does not submit the
> assignment. Three zeros that are no longer late are still three zeros until the files
> upload. Scope of the clearance (which assignments) and any replacement dates were not
> settled. Until itemized, treat A#3 as due Sat 2026-10-10.

**MAT 102A has no known due date, rubric, or AI policy.** The verbal AI allowance given in
CIS 350A does **not** transfer to it. Do not assume it does.

---

## Import record, 2026-10-08

Ingested from three staged bundles on the MAE Bunker USB, which mounted as `E:` on the
school machine (`s0976307`) and as `I:` on the Beelink. The Bunker itself (`I:\MAE\`, and
the `MAE_BUNKER` images on `D:` and `F:`) was read only and never written.

| Bundle | Files | Verification |
|---|---|---|
| `CIS350A-TRANSFER\course` | 92 | 92/92 SHA-256 identical to source |
| `MAT102A-TRANSFER\coursework` | 7 | 7/7 SHA-256 identical to source |
| `HIST-TRANSFER\payload\HIST` | 10 | 10/10 SHA-256 against shipped `MANIFEST.sha256` |

### Two things were changed on purpose

**1. The global doctrine was not overwritten.** `SETUP-BEELINK.ps1` step 2 installs the
transfer's `GLOBAL-CLAUDE.md` over `~/.claude/CLAUDE.md`. That file is the master, v8.1a
Echo State GOLDEN, and the transfer's own README concedes its doctrine is "largely
reconstructions from transcripts" and that the main source wins. The master was restored
from the script's own backup and verified byte identical, SHA-256 `CAB5C863...0245CE`.
The school doctrine was re-scoped to `EAGLES CLASSES\CLAUDE.md`, where it loads for school
sessions and nowhere else. The additive parts of step 2 were kept: `~/.claude/MAE\` (12
doctrine files, did not previously exist) and the `mae-run` skill.

**2. Two HIST ebooks were renamed.** See below.

### Path length

`SETUP-HIST.ps1` targets `<Desktop>\EAGLES 2026\CLASSES 2026\HIST` and would have produced
a **267-character** path for the Mann `.mobi`, past the 260 limit. `LongPathsEnabled` is
`1` on this machine, but Windows PowerShell 5.1 does not honor it, so `Copy-Item -Recurse`
would have skipped the file **while reporting success**, exactly the way the CIS 350A
textbook was silently dropped on the previous transfer. The HIST copy was done by hand with
per-file hash verification instead, and two files were shortened:

```
George W_ Bush_ ... 06c23113... -- Ann.mobi              ->  Mann - George W Bush.mobi
George W_ Bush_ ... dd9c93ea... -- Anna's Archive.epub   ->  Mann - George W Bush.epub
```

Content is unchanged and both hashes match the manifest. Original names are preserved in
`26FA\HIST\MANIFEST.sha256`.

**The rule this produces: count both sides after any bulk copy.** A recursive copy on
Windows does not fail loudly.

---

## Known gaps

| Gap | Effect | Fix |
|---|---|---|
| **Microsoft Excel is not installed** | Blocks MAT 102A entirely. The `.xlsx` skeleton and every chart in Case Study 1 need it, and the Excel work is the graded skill. | Install Excel, or confirm a substitute is accepted |
| **poppler (`pdftoppm`) missing** | 4 CIS 350A study-guide PDFs cannot be read into a session | `winget install --id oschwartz10612.Poppler` |
| `SleepStudy-CaseStudy1.xlsx` copied while Excel held the file open | Any unsaved edits from 2026-10-07 are not in this copy | Re-copy from the school machine if it matters |
| Two Gold Code names carry conflicting payloads (`Eyes Up`, `Ghost Mode`) | Ambiguous invocation in school shells | Invoke by description until ruled. Flagged in `GOLD-CODES.md` |

---

## Working the shells

| Launch | Use when |
|---|---|
| `26FA\CIS350A\OPEN-CLAUDE-MAE.bat` | **Default.** Opens VS Code on `Prep\`, which is the slug the project memory is filed under |
| `26FA\CIS350A\CIS350A.code-workspace` | Reading across Prep, AIB, Course Material at once |

Project memory was reslugged for this machine and this scheme:

```
C--Users-User-Desktop-Projects-EAGLES-CLASSES-26FA-CIS350A-Prep
C--Users-User-Desktop-Projects-EAGLES-CLASSES-26FA-CIS350A-AIB
```

**Memory is keyed to the folder path.** Moving these course folders silently unloads that
memory. If the tree moves, rerun `SETUP-BEELINK.ps1` with the new `-CoursePath` rather than
dragging folders.

In a fresh session on `Prep\`, run `MAE RUN`. It verifies by inspection instead of trusting
this document.

MAE holds the line. No fade.
