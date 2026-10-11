# Verified Source Register: AI in Digital Forensics
**APA 7th edition. Verification status on every entry.**

---

## READ THIS FIRST: both example citations in the plan were wrong

The outline you pasted offered two sample references. I checked both.

| Given in the plan | Actual record |
|---|---|
| Garfinkel, S. (2020). Digital forensics research: The next 10 years. *Digital Investigation, 34.* | **2010**, *Digital Investigation, 7*(Suppl.), **S64–S73** |
| Casey, E. (2019). *Digital evidence and computer crime.* Academic Press. | 3rd ed., **2011**, Academic Press |

Garfinkel is off by ten years and the wrong volume. Casey is off by eight.

This is the exact failure signature that got the last paper flagged: citations that are structurally perfect, plausible on sight, and factually wrong. A real reference list is messy, full of odd page ranges, supplement markers, and inconsistent editions. Fabricated ones are clean and round.

**If you submit a paper where the professor checks two references and both are wrong, the AI score stops being the argument.** Verify every entry against the actual record before it goes in.

---

## Tier 1: peer-reviewed, verified, use these

### A1. Your spine source
**Dunsin, D., Ghanem, M. C., Ouazzane, K., & Vassilev, V. (2024). A comprehensive analysis of the role of artificial intelligence and machine learning in modern digital forensics and incident response. *Forensic Science International: Digital Investigation, 48*, 301675. https://doi.org/10.1016/j.fsidi.2023.301675**

**Status: VERIFIED.** Retrieved and read.
**Peer-reviewed:** Yes. Elsevier journal, the leading venue in the field.

Covers both halves of your title in one paper. Opportunities it identifies: efficiency and precision gains, pattern recognition, large-scale dataset handling, cybercrime timeline reconstruction, chain-of-custody support. Challenges: the field is explicitly "in its nascent stages," growing database sizes, adversary adaptation, and a gap between research capability and practical need.

*Use it in:* Literature Review (anchor), Findings, Recommendations. If you read one source completely, read this one.
Free preprint if the journal is paywalled: `https://arxiv.org/abs/2309.07064`

### A2. Historical framing
**Garfinkel, S. L. (2010). Digital forensics research: The next 10 years. *Digital Investigation, 7*(Suppl.), S64–S73. https://doi.org/10.1016/j.diin.2010.05.009**

**Status: VERIFIED.** **Peer-reviewed:** Yes (DFRWS 2010).

The field-defining "coming crisis" paper on data volume growth outpacing investigator capacity. Written before modern ML, which is what makes it useful: it names the problem AI is now proposed to solve. Opening your Introduction by pairing Garfinkel's 2010 prediction against Dunsin's 2024 assessment is a clean, genuinely academic move.

### A3. Foundational text
**Casey, E. (2011). *Digital evidence and computer crime: Forensic science, computers, and the Internet* (3rd ed.). Academic Press.**

**Status: VERIFIED.** **Peer-reviewed:** No, this is an academic textbook. Fine for definitions, not for claims.

*Use it in:* Introduction only, to define digital forensics and chain of custody. Do not lean on it for anything current.

### A4. Legal standard
**Daubert v. Merrell Dow Pharmaceuticals, Inc., 509 U.S. 579 (1993).**

**Status: VERIFIED.** Settled law.

The four-factor admissibility test: testing, known error rate, peer review and publication, general acceptance. The error-rate prong is where AI forensic tools get interesting, because most do not publish one. Pair with **Federal Rule of Evidence 702**, amended December 2023 to tighten the proponent's burden.

*Use it in:* Findings and Recommendations. This is what separates a real forensics paper from a technology summary.

---

## Tier 2: verified but preprints, handle with care

These are real papers by real authors, but they are arXiv preprints. If your assignment says peer-reviewed, a preprint may not count.

### B1
**Nayerifard, T., Amintoosi, H., Bafghi, A. G., & Dehghantanha, A. (2023). *Machine learning in digital forensics: A systematic literature review.* arXiv. https://arxiv.org/abs/2306.04965**

**Status: VERIFIED as a preprint.** Systematic review of ML in digital forensics, January 2010 to December 2021.
**Before citing:** search the title in Google Scholar to see whether it landed in a journal. If it did, cite the journal version. Dehghantanha is a well-published forensics researcher, so a published version is plausible.

### B2
**Cen, S. H., Ismael, H., & Zheng, L. (2026). *Barriers to evidence in AI-related cases and the privatization of proof.* arXiv. https://arxiv.org/abs/2605.21816**

**Status: VERIFIED as a preprint.** I read it.
Finds that courts overwhelmingly decline to compel disclosure of algorithmic evidence under both *Daubert* and *Frye*. Directly relevant to the "challenges" half of your title: if a forensic AI tool's error rate is a trade secret, the *Daubert* error-rate prong cannot actually be tested.
**Same caution:** preprint. Strong material, verify acceptability.

---

## Tier 3: leads worth chasing in the NU databases

- **DFRWS EU 10-year review (2024)**, *FSI: Digital Investigation, 48*. Reviews all 135 peer-reviewed DFRWS EU papers, 2014–2023. Excellent Literature Review scaffolding. Direct download returned 403, so pull it through the library.
- **NIST Computer Forensics Tool Testing (CFTT)** program materials. Government, authoritative, free. This is your best hard evidence on tool validation and error rates for the Recommendations section.
- **Springer (2025), *AI and ML in Digital Forensics: A Survey***, `10.1007/978-981-96-8793-0_46`. Confirm authors and full details before citing.

---

## Do not cite

Vendor pages (Magnet, Cellebrite, Exterro), law-firm blogs, ResearchGate as a *source* (it hosts copies, so cite the journal), Wikipedia, and news aggregators. The report you attached specifically flags this as a defect in the last submission. Fixing it is measurable, provable progress you can point to.

**ResearchGate note:** fine for *getting* a PDF, never the citation. Cite the journal it came from.

---

## Niagara database search strings

I cannot reach NU's proxy. Those need your login. Paste these in directly.

**Best databases for this topic:** IEEE Xplore, ACM Digital Library, ScienceDirect (for *FSI: Digital Investigation*), Academic Search Complete, Criminal Justice Abstracts.

```
("digital forensic*" OR "computer forensic*")
AND ("machine learning" OR "artificial intelligence" OR "deep learning")
AND (challenge* OR limitation* OR validation)
```

```
("forensic tool" OR "forensic software") AND (validation OR "error rate" OR reliability)
```

```
("digital evidence") AND (admissib* OR Daubert OR "expert testimony") AND (algorithm* OR "machine learning")
```

```
("triage" OR "evidence prioriti*") AND "digital forensic*" AND automat*
```

**Two tactics that save hours**

1. Open Dunsin et al. (A1) and mine its reference list. A 2024 comprehensive review has already done your literature search. That is what reviews are *for*, and following a review's citations is legitimate scholarly practice, not shortcutting.
2. In ScienceDirect, set the journal filter to *Forensic Science International: Digital Investigation* and sort by date. Everything there is peer-reviewed and on-topic by construction.

Five to eight sources is your target. You have four verified right now (A1 through A4). You need three or four more, and Dunsin's bibliography will hand them to you.
