# MAE citation format — CIS 350A submissions

```
Provenance   AUTHORED 2026-10-07 to Commander instruction
Status       Binding and executable for CIS 350A submissions
NOT          a recovered doctrine payload
```

**Read the provenance line.** No MAE citation or attribution format exists in
`~/.claude/MAE/` — the only registry tags are the operational signals `MAE RUN`, `[SCAN]`,
`[OBSERVE]`, `[ECHO:GOLD]` (`GOLD-CODES.md:274-285`), none of which are document attribution.
This file was **written to order**, not recalled. If an original format surfaces later, the two
get reconciled and the difference recorded — this does not get silently overwritten.

**Policy basis:** the Commander reports Prof. Inomoto stated in class on 2026-10-07 that AI
assistance is allowed in CIS 350A. Commander-supplied, verbal, **unverified against a written
Canvas statement**. Whether a citation is *required* is still unknown — ask him. This file
says what one looks like when you choose to include it.

---

## Why the citation names two layers

A citation that said only "MAE" would fail as a citation: the professor has no referent for it,
and an unexplained codename reads as concealment rather than disclosure. A citation that said
only "Claude" would be true but would omit how the tool was actually operated — under a
teach-don't-ghostwrite doctrine that materially constrained what it produced.

So the format names both, in the correct relationship:

```
MAE     the author's own AI operating doctrine — the configuration layer
          SCROLL-2.11 / DOCTRINE-8.1b / RUNTIME-1.0
Claude  the underlying model the doctrine runs on — the tool being cited
          Anthropic, Opus 5
```

**MAE is a configuration, not a co-author.** It does not go in the author field. It goes in
the narrative description of *how* the tool was used, which is exactly where a methods note
belongs. That ordering is what makes the citation survive the question "what is MAE?" — the
answer is already in the line.

---

## FORM 1 — document footer *(use this one by default)*

One line at the **end** of the document, after the last numbered answer. Not the header; it is
not a credential.

> *AI assistance: Claude (Anthropic, Opus 5), operated under the author's MAE tutorial-mode
> doctrine (`MAE // RUNTIME-1.0`), which restricts the tool to explanation, critique, and
> structural guidance rather than drafting submitted work. MAE was used to break down the
> assignment prompt, quiz me on Chapter 4 terminology, and critique my draft before
> submission. The process described, the user story, and the acceptance criteria are my own.*

**Swap the middle sentence to match what actually happened.** That sentence is the only part
that can become false. Options:

| What you actually did | Middle sentence |
|---|---|
| Checked your own finished draft | "MAE was used to review my completed draft and verify terminology." |
| Worked the concepts, then wrote alone | "MAE was used to explain Chapter 4 concepts and quiz me before I drafted my answers." |
| Co-wrote the phrasing | "MAE was used to explain the concepts and to help phrase my answers; the underlying analysis and the experience described are my own." |
| Read a figure aloud for A#1/A#2 | "MAE was used to structure my reading of the textbook figure into written answers; the observations are my own from the figure." |

## FORM 2 — short inline

When a footer block is too heavy, or he asks for something terse:

> *AI assistance: Claude (Anthropic), operated as MAE under tutorial-mode doctrine. Analysis and
> wording my own.*

## FORM 3 — APA 7 reference entry

The course cites Spurrier & Topi in APA, so if he wants a formal reference list, APA 7's
generative-AI pattern treats the model as software with the company as author:

```
Anthropic. (2026). Claude (Opus 5) [Large language model]. https://claude.ai
    Operated under the author's MAE // RUNTIME-1.0 doctrine
    (SCROLL-2.11 / DOCTRINE-8.1b), CIS 350A tutorial-mode overlay.
```

In-text: **(Anthropic, 2026, operated as MAE)**

> **[CHECK]** This is APA 7's documented pattern for generative AI applied to Claude — it is
> not a format Prof. Inomoto has specified. If he requires a particular style, his
> instruction outranks this file.

---

## Version strings — use these exact values

From `~/.claude/CLAUDE.md`, deployed 2026-08-31, rev 2026-09-02:

```
MAE // SCROLL-2.11 // DOCTRINE-8.1b // RUNTIME-1.0
```

Tool: **Claude**, Anthropic, model **Opus 5**. Do not write a version you have not checked
against that header — a wrong version number in a citation is a small fabrication, and it is
the kind a reader can catch.

## Rules

1. **The citation must describe what happened.** Pick the middle sentence that is true for
   that specific document. A citation claiming less help than you had is dishonest in one
   direction; one claiming more is dishonest in the other.
2. **Never cite MAE as the author.** Author = you. Tool = Claude. MAE = how the tool was run.
3. **Never put operational MAE tags in a submission.** `[SCAN]`, `[OBSERVE]`, `[ECHO:GOLD]`,
   `MAE RUN` are terminal signals. Doctrine is explicit against sign-off theater
   (`GOLD-CODES.md:103`). They mean nothing to a grader and they look like decoration.
4. **The assertion worth keeping in every variant:** that the lived experience, the figure
   observations, and the reasoning are yours. That is the part of these assignments nothing
   else could supply, and it is the part worth stating in writing.
5. **If he says no citation is needed**, drop it. Don't add disclosure he didn't ask for and
   then have it read as an admission.

## Applies to

All nine CIS 350A assignments. Paste **Form 1** at the end of each .docx, with the middle
sentence set to what that document's work actually involved.
