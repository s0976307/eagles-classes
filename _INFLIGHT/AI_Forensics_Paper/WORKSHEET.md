# Paper Worksheet
### Artificial Intelligence in Digital Forensics: Opportunities and Challenges
**Target: 5 to 7 pages · APA 7 · Structure fixed by the assignment**

This is a worksheet, not a draft. Each section gives you the questions to answer and the sources that answer them. You write the sentences. That is deliberate, and the reason is at the bottom.

---

## Before you write a single word: start the process record

Open a plain text file called `research_log.txt` in this folder. Every time you sit down, add a dated line:

```
2026-08-21  Read Dunsin 2024 pp.1-6. Key point: field is "nascent stages."
            Surprised how cautious it is. I expected stronger claims.
2026-08-22  Searched IEEE for forensic tool validation. 3 hits, 1 useful.
            Dead end on error-rate stats, nobody publishes them.
```

Ninety seconds a day. Include the dead ends and the things that surprised you. Those are the entries that prove a human did this, because a generated log has no dead ends.

Save every PDF you open into `sources/`. Keep every draft as a separate file (`draft_v1.docx`, `draft_v2.docx`). Do not overwrite.

This log is worth more to you than any paragraph I could write.

---

## 1. Introduction (about ¾ page)

**Answer these four questions in your own words:**

1. What is digital forensics? *(Casey, 2011, definition only)*
2. Why are investigations getting harder? *(Garfinkel, 2010: data volume outpacing investigator capacity)*
3. What is AI being proposed to do about it? *(Dunsin et al., 2024)*
4. What is this paper going to argue?

**The move that makes this section good:** Garfinkel predicted the crisis in 2010. Dunsin assessed it in 2024 and still calls the field "nascent." Put those side by side. That is a real observation you can defend out loud, and it takes about three sentences.

**Your thesis.** Write it before anything else, one sentence, your own words:

> AI offers real gains in digital forensics for ________, but faces unresolved challenges in ________, meaning ________.

Fill those blanks after you read Dunsin. Not before.

---

## 2. Literature Review (about 1.5 pages)

Not a list of summaries. Group by **theme**, and for each theme say what the researchers agree on and where they diverge.

**Theme A: what AI is being used for**
Source: Dunsin et al. (2024). Their categories are data collection, evidence recovery, timeline reconstruction, big data analysis, and incident response.
→ *Which two or three matter most? Why those?*

**Theme B: what the reported gains are**
Sources: Dunsin (2024), Nayerifard et al. (2023) if usable.
→ *Efficiency, precision, pattern recognition. Be specific about what is actually demonstrated versus what is claimed.*

**Theme C: what the limits are**
Source: Dunsin (2024) on nascent stage, growing databases, adversary adaptation, research-practice gap.
→ *This theme is where your paper earns its title. Do not shortchange it.*

**Theme D: explainability and the legal problem**
Sources: *Daubert* (1993), FRE 702, Cen et al. (2026) if usable.
→ *If a model cannot explain its output, can its output be evidence?*

**Discipline rule:** cite something in every paragraph here. A Literature Review paragraph with no citation is not a literature review.

---

## 3. Findings (about 1.5 pages)

Your interpretation. No new sources here. Synthesize what section 2 established.

Three findings is the right number for this length. Suggested:

**Finding 1: the gains are real but narrow.**
AI performs well on volume reduction and triage. That is not the same as drawing forensic conclusions.

**Finding 2: the bottleneck moved, it did not disappear.**
Garfinkel's problem was too much data for humans. The current problem is verifying machine output. You have not eliminated the human review step, you have relocated it. Say that in your own words; it is the strongest sentence available in this paper.

**Finding 3: legal standards have not caught up.**
*Daubert* wants a known error rate. Most forensic AI tools do not publish one. So a tool can be operationally useful and evidentially weak at the same time.

Under each, answer: *what is the evidence, and what does it mean?*

---

## 4. Recommendations (about 1 page)

Four concrete items. For each, state what to do, who does it, and what problem it solves. Vague recommendations are where short papers die.

1. **Mandatory tool validation and published error rates.** NIST CFTT is the existing model. Solves the *Daubert* gap.
2. **Explainability requirements for evidentiary use.** A tool used in court must produce a human-readable basis for its output. Solves Finding 3.
3. **Human-in-the-loop as policy, not custom.** The examiner confirms, the machine proposes. Solves Finding 2.
4. **Investigator training in tool limitations.** Examiners must be able to testify to how the tool works and where it fails. Solves the courtroom competence problem.

*Optional fifth:* privacy and scope limits on bulk analysis. Include only if you have space.

---

## 5. Conclusion (about ½ page)

Restate the thesis in different words. Name the two or three findings. Say what comes next: hybrid human-AI examination where AI reduces volume and humans hold the conclusions.

Do not introduce anything new. Do not end on a rhetorical question.

---

## 6. References

APA 7. Alphabetical. Hanging indent.

Four verified entries are already formatted in [SOURCES_APA7.md](SOURCES_APA7.md). Copy them exactly. Get three or four more from Dunsin's bibliography.

**Verify every single one against the actual record before submission.** Two of the sample citations you were given were wrong by a decade. Assume nothing.

---

## Why I am not writing the prose

You asked me to write this paper. I am not going to, and you deserve the straight reason rather than a polite dodge.

Your professor flagged the last submission at 86% and cited the syllabus and previous meetings, which makes this a policy question rather than a detector-score question. If I write section 2 and you hand it in, one of two things happens: it flags again, or it does not and you still cannot answer questions about it in a meeting. Both are worse than a rough paper that is yours.

There is also a harder truth in the report you attached. The last paper had claims like a 5,000:1 triage ratio and 100% blockchain-AI validation. I searched for the underlying literature today and those figures are not in it. Whatever produced that paper generated numbers that sound right. That is the actual risk, not the writing style. It is the unverifiable claims. Which is why this worksheet gives you four sources I personally retrieved and read, and flags exactly which ones are preprints.

What I have done here is research assistance: finding sources, checking citations, structuring an argument. That is what a librarian or a writing center does, and it is the part I can do without putting you in a worse position than you are already in.

A rough five-page paper you can defend in a meeting beats a polished one you cannot. You are one recorded conversation away from needing to explain every sentence. Write sentences you can explain.

---

## Realistic schedule

| Block | Task | Time |
|---|---|---|
| 1 | Read Dunsin et al. (2024) properly. Take notes in your own words. | 90 min |
| 2 | Pull 3 or 4 more sources from its bibliography via NU databases. | 60 min |
| 3 | Write thesis and Introduction. | 45 min |
| 4 | Literature Review by theme. | 90 min |
| 5 | Findings and Recommendations. | 90 min |
| 6 | Conclusion, references, verify every citation. | 60 min |

About seven hours, splittable across days. Log every block.

---

## One thing to settle before you start

Get the AI-use policy in writing: the syllabus section, and anything from those prior meetings. Everything above assumes research assistance and citation help are permitted while drafting is not. If your syllabus is stricter than that, tell me and I will cut this back further. Better to ask now than to find out afterward twice.
