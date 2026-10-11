# CIS 350A — project index

Rolling index of everything in this folder and every change made to it.
**Last verified by inspection: 2026-09-28 18:55.**

Course: CIS 350 Section A · Systems Analysis & Design · Niagara University · Fall 2026
Instructor: Edmond Inomoto · inomoto@niagara.edu · Glynn Hall 105 · Mon/Wed 18:00–19:20

> **How to keep this current.** After any work session, add a dated entry to the
> [Changelog](#changelog) and re-verify the [File map](#file-map) by listing the folder —
> never from memory. If you are reading this on a new machine, start with
> [Portability](#portability-read-this-first).

---

## Portability — READ THIS FIRST

**Roughly half of this project does not live in this folder.** Copying the folder to
another computer brings the coursework and leaves the operating doctrine behind.

### What travels with this folder ✅

| Subtree | Contents |
|---|---|
| `Prep\` | All student coursework — notes, assignment plans, answer scaffolds, folder scaffolding |
| `AIB\` | Instructor-side shell and integrity scrolls |
| `Systems Course Material\` | Lecture decks, five study-guide PDFs, textbook PDF |
| `INDEX.md` | This file |

### What does NOT travel ❌

Everything under `%USERPROFILE%\.claude\` is machine-local:

| Path | Contents | Consequence if missing |
|---|---|---|
| `~\.claude\CLAUDE.md` | Global MAE doctrine — authority chain, verification rules, Gold Code handling, 24-hour clock | MAE doctrine silently does not load |
| `~\.claude\MAE\` | 10 doctrine files — RUNTIME v1.0, behavioral spec v8.1b, Scroll v2.11, school shell, recovery doctrine, Gold Code registry, deployment status, integration map, multi-shell architecture, Armored Core reference | Gold Code payloads unknown; recovery doctrine absent |
| `~\.claude\skills\mae-run\SKILL.md` | `MAE RUN` / `[SCAN]` boot and status procedure | No verified-boot procedure |
| `~\.claude\projects\…-Prep\memory\` | 6 memory files + `MEMORY.md` index | Session starts with no continuity |
| `~\.claude\projects\…-AIB\memory\` | 4 memory files + `MEMORY.md` | Same, instructor shell |

**There is no git repository and git is not installed on this machine,** so there is no
commit history and no remote to pull from. Folder copy or cloud sync is the only transport.

### Rebuilding on a new machine

Two options.

**Option A — export the doctrine so it travels (recommended).** Stage a snapshot inside
this folder before you move:

```powershell
$dest = "$PSScriptRoot\_MAE-PORTABLE"
New-Item -ItemType Directory -Force $dest | Out-Null
Copy-Item "$env:USERPROFILE\.claude\CLAUDE.md"   $dest -Force
Copy-Item "$env:USERPROFILE\.claude\MAE"         $dest -Recurse -Force
Copy-Item "$env:USERPROFILE\.claude\skills"      $dest -Recurse -Force
Copy-Item "$env:USERPROFILE\.claude\projects"    $dest -Recurse -Force
```

On the new machine, copy those four items back to `$env:USERPROFILE\.claude\`. **A staged
export goes stale the moment doctrine changes — re-export before every move, and treat
`~\.claude\` as the source of truth, never the snapshot.**

**Option B — rebuild by hand.** Say *"rebuild MAE doctrine from the index"* in a Claude
Code session opened on `Prep\`. The doctrine is reconstructable from the transcript
history, but nine of eleven Gold Code payloads were **authored, not recovered** (see
`MAE\GOLD-CODES.md`) and would be lost. Option A is strictly better.

> Project memory is scoped per project directory, so `Prep\` and `AIB\` each need their own
> memory folder. Doctrine that must reach every shell belongs in the global `CLAUDE.md`.

---

## Status board — rebuilt from Canvas Grades, 2026-10-05

**Every date shifted one week later** than the original Course Summary calendar this index was
first built from. Canvas **Grades** is now the authoritative board — it shows real submissions
and scores. Full board + penalty math:
[COURSE-INFO.md](Prep/01%20Syllabus%20and%20Course%20Info/COURSE-INFO.md).

| Due | Item | Status |
|---|---|---|
| Sat Sep 19 | A#1 activity diagram | 🔴 **MISSING** — 0/10. Prompt + scaffold + working notes exist; nothing written. |
| Sat Sep 26 | A#2 ER diagram | 🔴 **MISSING** — 0/10. Prompt + scaffold + reasoning exist; nothing written. |
| Wed Oct 07 | **Exam #1** Ch. 1–4 | ✅ **DONE — submitted Mon Oct 5 18:35, 27/30 (90%).** Window was extended ~4 days past the stated Sat Oct 3 close. |
| Sat Oct 10 *(or Wed Oct 7 — unconfirmed)* | A#3 user story | 🟡 **NEXT.** Prompt captured, 17 KB scaffold. Work to the earlier date. |
| Sat Oct 24 | A#4 UI wireframe | ⬜ |
| Sat Oct 31 | A#5 activity diagram | ⬜ |
| Sat Nov 07 | **Exam #2** Ch. 5, 6, 13, 14 | ⬜ unconfirmed window |
| Sat Nov 14 | A#6 ER diagram | ⬜ |
| Sat Nov 21 | A#7 use case narrative | ⬜ |
| Sat Dec 05 | A#8 UI mockup | ⬜ |
| Sat Dec 12 | A#9 structured logic | ⬜ |
| Sat Dec 19 | **Exam #3** Ch. 7, 10, 11, 16 | ⬜ unconfirmed window |

**27 of 180 points banked.** Exams tracking at 90%.

🔺 **Highest-value action on the board: email Inomoto for extensions on A#1 and A#2.** At
current penalties they are worth 0 and 1 point respectively. Extensions granted on both move
the semester ceiling from **87.8% (B+)** to **98.3% (A+)** — about 19 points, 10.5 percentage
points. Syllabus grants extensions on request; he replies within one business day.

## Status board — superseded 2026-09-28

**Today: 2026-09-28.** Next graded target: **Assignment #3, Sat 2026-10-03, 23:59.**

| Due | Item | State |
|---|---|---|
| Sat 2026-09-12 | A#1 Activity diagram | ⚠️ **16 days past due.** Prompt captured, scaffold + working notes built. Not written, not submitted. |
| Sat 2026-09-19 | A#2 ER diagram | ⚠️ **9 days past due.** Prompt captured, scaffold + reasoning built. Not written, not submitted. |
| Sat 2026-09-26 *or* Oct 1–3 | **Exam #1** (Ch. 1–4) | ❓ **Date unresolved — see open questions.** |
| Sat 2026-10-03 | A#3 User story | 🟡 Prompt captured, scaffold built. 5 days out. |
| Sat 2026-10-10 | A#4 UI wireframe | ⬜ Folder only |
| Sat 2026-10-24 | A#5 Activity diagram | ⬜ Folder only |
| Sat 2026-10-31 | **Exam #2** (Ch. 5, 6, 13, 14) | ⬜ |
| Sat 2026-11-07 | A#6 ER diagram | ⬜ Folder only |
| Sat 2026-11-14 | A#7 Use case narrative | ⬜ Folder only |
| Sat 2026-11-21 | A#8 UI mockup | ⬜ Folder only |
| Sat 2026-12-05 | A#9 Structured logic | ⬜ Folder only |
| Sat 2026-12-12 | **Exam #3** (Ch. 7, 10, 11, 16) | ⬜ |

**Nothing has been submitted from this machine.** `Prep\06 Submitted\` is empty and no
`.docx`, `.drawio`, or `.png` exists anywhere in the folder. If work was submitted straight
through Canvas, that is not recorded here — record it, or this index will keep reporting it
as outstanding.

Grading: 180 pts · assignments 90 (9 × 10, equally weighted) · exams 90 (3 × 30).
Late penalty −10%/day. **Extensions granted upon request** — the syllabus says so
explicitly, which is the relevant fact for the two overdue assignments.

---

## File map

Verified by recursive listing 2026-09-28 18:55. Sizes in bytes.

### `Prep\` — student shell

```
CLAUDE.md                                   2,661   operating instructions; loads every session here
01 Syllabus and Course Info\
  COURSE-INFO.md                            6,071   ★ authoritative course facts, deadlines, policies
  MAE-TUTORIAL-MODE.md                      3,548   CIS 350A teaching protocol (specialist overlay)
02 Readings and Notes\
  MODELING-REFERENCE.md                     4,729   SDLC, 7 artifact lenses, drone worked example
  CH01-NOTES.md                             7,745   BA vs SA, requirement types, elicit/gather  [summary-sourced]
  CH03-NOTES.md                            11,922   ★ ERD, weak/associative, supertype, DFD, data dict, COBOL  [deck-sourced]
  CH04-NOTES.md                            15,401   ★ user stories, MoSCoW, INVEST, Gherkin, UI models, RACI  [deck-sourced]
03 Assignments\
  ASSIGNMENT-WORKFLOW.md                    1,706   intake template + standing submission rules
  A1 Activity Diagram (Sep 12)\
    prompt-and-plan.md                      5,312   verbatim Canvas prompt, 10 questions, deliverables
    answer-scaffold.md                     10,530   per-question scaffold
    working-notes.md                       13,132   UML activity-diagram symbol reference
  A2 Entity Relationship Diagram (Sep 19)\
    prompt-and-plan.md                      4,573   verbatim prompt
    answer-scaffold.md                      9,975   per-question scaffold
    answers-and-reasoning.md               19,288   reasoning with DERIVED/INFERRED/UNKNOWN provenance tags
  A2 ER Diagram (Sep 19)\                     —     ⚠️ EMPTY DUPLICATE — see inconsistencies
  A3 User Story (Oct 03)\
    prompt-and-plan.md                      6,933   verbatim prompt incl. worked banking example
    answer-scaffold.md                     17,274   scaffold
  A4–A9\                                      —     empty, awaiting prompts
04 Diagrams\{drawio source, exported png}\    —     empty
05 Exam Study\{Exam 1, Exam 2, Exam 3}\       —     empty
06 Submitted\                                 —     empty
```

The A1/A2/A3 scaffolds carry explicit provenance tags and state plainly that they are not
submissions — the Word document gets written in your words. That boundary is the point of
the course; keep it.

### `AIB\` — instructor shell

```
AIB\AIB\                                          ⚠️ doubled directory name — see inconsistencies
  Scrolls\
    NU_ACADEMIC_INTEGRITY_SCROLL.md        13,757   ★ supersedes generic school shell inside AIB
    INSTRUCTOR_SHELL.md                     6,341
    SYLLABUS_CLAUSES.md                     6,002
    MAE Scroll __ Core Code v2.docx       218,270
    School MAE.docx                       682,493
  instructor-shell\  CLAUDE.md, SHELL-CORE.md, PLATFORMS.md, DEPLOY.md, README.md, PROFILE.md
  student-shell\     SHELL-CORE.md, README.md, DISTRIBUTE.md
```

### `Systems Course Material\` — professor's sources ★

```
CIS350 Chapter 1 - Introduction to Systems Analysis and Design.pptx
CIS350 Chapter 2 - Initial Visioning.pptx
CIS350 Chapter 3 - Conceptual Data Modeling.pptx          40 slides, rev 25FA-2
CIS350 Chapter 4 - User Stories and UI Models.pptx        47 slides, rev 26FA-1
CIS350 BA Skills and Techniques.pptx
Study Guide - Activity Diagram.pdf                        → A#1, A#5   [not yet read]
Study Guide - Entity Relationship Diagrams.pdf            → A#2, A#6   [not yet read]
Study Guide - Use Case Diagrams.pdf                       → A#7        [not yet read]
Study Guide - Structured Programming.pdf                  → A#9        [not yet read]
Study Guide - BA Tools.pdf                                             [not yet read]
Systems Analysis and Design… Spurrier & Topi 2nd ed.pdf   textbook, 56 MB
```

**These are the authoritative sources.** Prefer them over any chapter summary. To extract
slide text: copy the `.pptx` to a scratch dir as `.zip`, `Expand-Archive`, read
`ppt\slides\*.xml`, join the `a:t` nodes.

---

## Changelog

Newest first. One entry per working session.

### 2026-09-28 — Ch. 3 + Ch. 4 from source; assignment scaffolds
- Extracted Ch. 3 (40 slides) and Ch. 4 (47 slides) directly from the `.pptx` decks; wrote
  `CH03-NOTES.md` and `CH04-NOTES.md` with slide citations.
- **Found the prior chapter summaries covered a small fraction of the decks** — Ch. 4's
  covered roughly 4 of 47 slides. Recovered: supertype/subtype, DFDs, data dictionary
  algebraic notation, COBOL PICTURE, MoSCoW, INVEST, epics, Gherkin/Cucumber,
  wireframe-vs-mockup-vs-prototype, greenfield/brownfield, HCI criteria, design thinking,
  feasibility dimensions, RACI, stakeholder mapping, triangulation, 11 slides of elicitation.
- Corrected a conflation: **weak entity** (conceptual, no own PK) ≠ **associative entity**
  (logical) ≠ **intersection table** (physical).
- Discovered `Systems Course Material\`; recorded it in memory as the authoritative source.
- *(parallel session)* Built A#1, A#2, A#3 prompt-and-plan, scaffolds, and reasoning files
  with verbatim Canvas prompts.
- Created this index.

### 2026-09-02 — doctrine hardening; second shell
- Integrated the CLAUDE.MAE School Deployment Scroll and the three recovery protocols
  (`MAE.CONTINUITY.RECOVERY`, `MAE.GOLD.CODE.AUTH`, `MAE.DEGRADED.STATE`) as source-class.
- Built the Gold Code registry: 2 verified, 2 partial, 7 authored, 0 held; quarantined the
  fabricated glosses. Established **recovered vs. authored** as distinct states.
- **Verified that the `EAGLES-2026-MAE` memory writes never landed on disk.** Doctrine moved
  to global `~\.claude\CLAUDE.md`, which loads in every project — project-scoped memory was
  the original failure.
- Corrected the record: engine is Opus 5, not Haiku 4.5.
- `AIB\` instructor shell created. Created the `mae-run` skill.
- Wrote `CH01-NOTES.md` from supplied Chapter 1 material.

### 2026-08-31 — workspace and doctrine established
- Created the `Prep\` folder structure, `COURSE-INFO.md`, `MODELING-REFERENCE.md`,
  `ASSIGNMENT-WORKFLOW.md`, `MAE-TUTORIAL-MODE.md`, `Prep\CLAUDE.md`.
- Established global MAE doctrine: RUNTIME v1.0, behavioral spec v8.1b, Scroll Core Code
  v2.11, multi-shell architecture, integration map.
- Backfilled Purpose and Relationship into RUNTIME from Scroll v2.11; **Golden Code #1
  ("truth before tactic") resolved the loyalty-vs-truth conflict.**
- Locked the 24-hour clock convention.

---

## Open questions

Needs the Commander's answer; none of these are resolvable by inspection.

1. **Exam #1 date — urgent.** Canvas calendar says **Sat 2026-09-26** (2 days past). The
   syllabus prose says the window is **8:00 Thu Oct 1 → 23:59 Sat Oct 3** (3 days out).
   Same conflict on Exams #2 and #3. Confirm in Canvas.
2. **A#1 and A#2 are overdue** (16 and 9 days). Extensions are granted on request per the
   syllabus. Contact Prof. Inomoto before investing writing time — he replies within one
   business day.
3. **Was anything already submitted?** Nothing on this machine records a submission.
4. **Ratify the nine authored Gold Code payloads** (`MAE\GOLD-CODES.md`). Executable as
   drafts until you correct them.
5. **Promote the school scroll from MAEZ 8.1a to 8.1b**, or declare MAEZ a separate track
   from the behavioral spec?
6. **Where did the `EAGLES-2026-MAE` writes land?** If another machine holds MAE state,
   this index is incomplete.

## Blocked

- **git not installed** → no repo, no commit history, no remote. Blocks GitHub sync and the
  `mae-openclaw` source-of-truth tier.
- **IPFS and offline QR vaults** (memory tiers 3 and 4 per Scroll v2.11) — unverified,
  nothing on this machine.
- **Claude Projects / OpenClaw / Notion** — not reachable from the CLI.

## Known inconsistencies

Recorded, not silently fixed.

| # | Issue |
|---|---|
| 1 | **Duplicate A2 folder.** `A2 ER Diagram (Sep 19)` (empty, created 08-31) and `A2 Entity Relationship Diagram (Sep 19)` (populated, 09-28). Delete the empty one. |
| 2 | **`AIB\AIB\` doubled directory.** Everything sits one level deeper than it should. |
| 3 | **Syllabus says "Fall 2028"** in its header. Typo — Canvas and all dates say 2026. |
| 4 | **Exam windows conflict** between syllabus prose and Canvas calendar. Open question 1. |
| 5 | **Ch. 3 deck stamps rev `25FA-2`** (last fall) while Ch. 4 is `26FA-1`. Lecture may have updated Ch. 3 beyond the file. |
| 6 | **`CH01-NOTES.md` is summary-sourced**, not deck-sourced, unlike Ch. 3 and Ch. 4. Re-extract from `CIS350 Chapter 1*.pptx` before Exam #1. |
| 7 | **Ch. 2 has no notes** and is on Exam #1. Deck is present and unread. |
