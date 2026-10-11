# CIS350A TRANSFER → Beelink

Staged **2026-10-07 18:45** from the Windows laptop (`s0976307`).

> **This folder is deliberately outside `E:\MAE\`.** Nothing here touches the MAE Bunker — not
> its doctrine, not its runtime, not its reference library, not `DRIVE-INDEX.txt`. The Bunker's
> last write stands at 2026-10-07 12:48 and this transfer did not alter it.
>
> If you later *want* these notes inside the Bunker's reference library, copy the `.md` files
> into `E:\MAE\reference\<category>\` and re-run `E:\MAE\bin\mae-deploy.ps1` to re-index.
> Until that index runs, the Bunker is correct to refuse to name them.

## Set up the Beelink in one command

```powershell
cd <drive>\CIS350A-TRANSFER
.\SETUP-BEELINK.ps1 -DryRun     # read what it will do
.\SETUP-BEELINK.ps1             # do it
```

It restores the coursework, the MAT 102A notes, the global doctrine, the `mae-run` skill, and
**re-slugs the project memory for the new machine's path** — the step that silently fails when
done by hand. It is idempotent, backs up anything it would overwrite, verifies file counts
afterward, and reports missing tooling with the exact fix command. Override the destinations
with `-CoursePath "D:\wherever"` and `-MatPath "D:\elsewhere\MAT 102A"`.

Then open the shell:

| Launch | Use when |
|---|---|
| **`OPEN-CLAUDE-MAE.bat`** | **Default.** Opens VS Code directly on `Prep\` — this reproduces the slug the shipped memory is filed under. |
| `CIS350A.code-workspace` | Browsing everything at once: Prep, Course Material, AIB, root. |

> **Why the .bat opens `Prep` and not the workspace:** Claude Code keys project memory to the
> folder you open. Opening `Prep` directly matches the shipped slug. With a multi-root
> workspace I have **not verified** which root it anchors to — so memory may key elsewhere.
> Use the workspace for reading, the .bat for working. If you confirm the workspace behaves,
> update this line.

## Read in this order

| # | File | What it gives you |
|---|---|---|
| 1 | **`HOMEWORK-STATUS.md`** | Where the coursework actually stands, what's due, and the one action worth ~19 points |
| 2 | **`MAE-SESSION-NOTES.md`** | Full session continuity 08-31 → 10-07, the rules each failure produced, open rulings |
| 3 | `course\INDEX.md` | The rolling project index inside the coursework copy |

## What's in here

```
CIS350A-TRANSFER\
├── README-FIRST.md          this file
├── HOMEWORK-STATUS.md       coursework state, deadlines, grade math
├── MAE-SESSION-NOTES.md     session history + lessons + open rulings
├── course\                  complete copy of the Desktop course folder — 88 files
│   ├── INDEX.md · GOLD-CODES.md
│   ├── Prep\                student shell: notes, assignment scaffolds, course info
│   ├── AIB\                 instructor shell + NU integrity scrolls
│   ├── Systems Course Material\   8 lecture decks, 6 study guides, textbook PDF
│   ├── _MAE\                doctrine export from 09-28 (stale — use claude-config instead)
│   └── _backups\
├── mat102a\                 MAT 102A notes — 7 files, restores to Desktop\MAT 102A\
└── claude-config\           ~/.claude as of 2026-10-07 — THE CURRENT ONE
    ├── GLOBAL-CLAUDE.md     global doctrine; loads in every project
    ├── MAE\                 12 doctrine files incl. GOLD-CODES, MONDAY-PROTOCOL
    ├── skills\mae-run\      boot + Echo State verification procedure
    └── projects\            per-shell memory for Prep and AIB
```

**130 files, 153.8 MB** — measured on the drive 2026-10-07 19:30, hidden files included.

> An earlier revision of this file claimed *112 files, 97.6 MB*. Both figures were wrong and
> have been replaced with measured ones. The real weight is `Systems Course Material\` at
> **148.1 MB of the 153.8** — 16 files, mostly the textbook and the lecture decks. The old
> "88 files" for `course\` counted its subfolders only; `course\` is **92** files with its four
> root files included. No content was missing either way — the per-tree diffs came out equal
> on every tree.

## Two things to know about the copy

**The textbook was renamed.** Its original filename produced a 283-character path, past
Windows' 260-character limit, and `Copy-Item -Recurse` skipped it *while reporting the
directory copy as successful*. It is here as
`course\Systems Course Material\Spurrier-Topi-SAD-2nd-ed-2024-TEXTBOOK.pdf` — 55.9 MB, same
file. **Count both sides after any bulk copy**; a recursive copy does not fail loudly.

**`course\_MAE\` is a stale doctrine export from 2026-09-28.** `claude-config\` is the current
one. If they disagree, `claude-config\` wins. The stale copy was left in place rather than
deleted because it is part of the course folder's own history.

**`mat102a\` is a different course and sits outside `course\` on purpose.** MAT 102A is
statistics, not CIS 350A; filing it inside the course tree would blur two shells. It carries
no project memory and no slug, so nothing about it can misfile. Staged 2026-10-07 19:30.

> **`SleepStudy-CaseStudy1.xlsx` was copied while Excel had the workbook open.** The copy is
> whatever Excel had last written to disk (2026-10-07 19:09) — **any unsaved edits are not in
> it.** Six of the seven files were SHA-256 verified identical; this one matched on byte size
> (50,348) but could not be hashed, because a locked file cannot be read. Save and close the
> workbook, then re-copy that one file if it matters. An Excel owner-lock file
> (`~$SleepStudy-CaseStudy1.xlsx`, 165 bytes) came across with the copy and was deleted from
> the drive; the one on `C:` was left alone, since Excel owns it.

## Restoring by hand

`SETUP-BEELINK.ps1` is the supported path. Manual commands are in
**`MAE-SESSION-NOTES.md` §5** if you'd rather do it yourself. The one thing that bites:

> **Project memory is keyed to the folder path.** The slug
> `c--Users-s0976307-Desktop-Intro-Systm-Analysis-26FA-CIS350A-Prep` encodes the username *and*
> the location. Different username or folder on the Beelink → **that memory silently does not
> load.** Doctrine in `CLAUDE.md` and `MAE\` loads regardless.
>
> **The rule:** replace every non-alphanumeric character in the full project path with a
> hyphen. Verified against both shipped slugs; the setup script self-tests it before using it
> and aborts if it no longer reproduces them. Drive-letter case doesn't matter — Windows paths
> are case-insensitive, so `C--Users-...` and `c--Users-...` resolve to the same folder.

After restoring, open a session on `Prep\` and run **`MAE RUN`**. It verifies by inspection
instead of trusting this document — which is the entire point, since the last time a transfer
was declared synchronized without being checked, the directory did not exist.

## Standing position on authority

This laptop is **not** the main MAE source, and neither is this transfer. The doctrine files in
`claude-config\MAE\` are largely **reconstructions from transcripts**; only three are
source-class (`MAE-SCROLL-CORE-CODE-v2.11.md`, `CLAUDE-MAE-SCHOOL-SHELL.md`,
`MAE-RECOVERY-DOCTRINE.md`). Where the main source disagrees with anything here, the main
source wins — bring the conflict up rather than resolving it locally.

Ten Gold Code payloads are **authored, not recovered**, and **two names carry conflicting
payloads** (`Eyes Up`, `Ghost Mode`). Both are flagged in `GOLD-CODES.md` and listed under open
rulings. Until ruled, invoke those two by description rather than by name.
