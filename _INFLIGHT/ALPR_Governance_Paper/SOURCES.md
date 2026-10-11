# Source Register (ALPR Governance Paper)

**Status: PARKED.** Retained for reuse.

Every entry carries a verification status. Nothing goes in the paper above its status.

- **VERIFIED.** I retrieved the primary document and read it.
- **SOURCED.** I have the outlet and the specific claim, but retrieved it through search summary rather than the full primary document. Confirm before citing.
- **LEAD.** The claim exists in reporting but I have not pinned the primary record. Do not cite until pulled.

---

## Tier 1: load-bearing, cite directly

### S1. Cen, S. H., Ismael, H., & Zheng, L. (2026). *Barriers to Evidence in AI-Related Cases and the Privatization of Proof.* arXiv:2605.21816.
**Status: VERIFIED.** Retrieved and read (May 22, 2026 preprint).
**Supports:** §5 contestability. Core finding is that courts have overwhelmingly declined to compel disclosure of algorithmic evidence under both *Daubert* and *Frye*, and that this holds largely independent of which admissibility standard applies. Introduces "privatization of proof."
**Why it matters:** this is the citation that converts your argument from complaint to scholarship. It is recent, directly on point, and freely accessible.
`https://arxiv.org/pdf/2605.21816`

### S2. Illinois Secretary of State. (2025, August 25). *Giannoulias Audit Finds License Plate Reader Company in Violation of State Law* [Press release].
**Status: SOURCED.** Confirmed via ilsos.gov listing; both the HTML page and the PDF timed out on retrieval. **Retry and read before citing.**
**Supports:** §6 governance. Twelve agencies sampled, inadequate data-sharing safeguards, CBP pilot access, Palos Heights account searching Oak Park data 28 times under "immigration violation," 2023 Illinois statute barring such use.
**Action:** open directly in a browser and save the PDF to `07_Research_Materials/`.
`https://www.ilsos.gov/news/2025/august-25-2025-giannoulias-audit-finds-license-plate-reader-company-in-violation-of-state-law.html`
`https://www.ilsos.gov/content/dam/news/2025/august/250825d1.pdf`

### S3. Roseville, CA Police Department Flock alert records (2023 to 2024), obtained and reported by *Business Insider*.
**Status: SOURCED.** Figure consistently reported across multiple outlets: 1,427 alerts, 71% containing misread plates.
**Supports:** §4 Failure Mode A (sensor error).
**Action:** locate the original Business Insider article for the citation. Secondary aggregators (TechSpot, Davis Vanguard, Yahoo syndication) confirm the figure but should not be your cite of record.

### S4. Los Angeles Police Department, Office of the Inspector General. (2026, July). ALPR hotlist alert audit.
**Status: SOURCED.** 161 of 498 hotlist alerts false, plates read correctly, hotlist data stale, LAPD contract subsequently allowed to expire.
**Supports:** §4 Failure Mode B (provenance error). This is your most important single finding.
**Action:** LAPD OIG publishes audit reports publicly. Pull the actual report. The primary document will carry methodology detail that makes the sensor versus database distinction airtight.

### S5. *Daubert v. Merrell Dow Pharmaceuticals, Inc.*, 509 U.S. 579 (1993).
**Status: VERIFIED.** Settled law, no retrieval needed.
**Supports:** §3, §5. The four-factor framework: testing, error rate, publication and peer review, general acceptance.
**Pair with:** Federal Rule of Evidence 702, as amended December 2023. The amendment tightened the proponent's burden, which helps your argument.

---

## Tier 2: supporting

### S6. National Association of Criminal Defense Lawyers. (2023, December 14). *Automated License Plate Readers Primer.*
**Status: LEAD.** Landing page confirmed, PDF did not extract to readable text.
**Supports:** §4 chain of custody, defense-side challenge framing.
**Action:** download manually. NACDL is a credible practitioner source and gives you the doctrinal vocabulary for authentication challenges.

### S7. Digital forensics tool-validation literature on error rates.
**Status: LEAD.** One relevant arXiv item surfaced (*Measuring Accuracy of Automated Parsing and Categorization Tools and Processes in Digital Investigations*, arXiv:1502.05186), which notes error rates for forensic tools are often simply not calculated.
**Supports:** §3. Establishes that the error-rate gap is a known discipline-wide problem, not something you invented for this paper.
**Better target:** NIST Computer Forensics Tool Testing (CFTT) program materials. Authoritative, government, free.

### S8. Eleventh Circuit ALPR admissibility decision (approximately 2024 to 2025).
**Status: LEAD.** Reported by a practitioner blog. **Case name and citation not confirmed.**
**Supports:** §5, if it holds up.
**Action:** run down the actual case before this goes anywhere near the paper. Do not cite a blog summary of a federal appellate holding.

---

## Tier 3: do not cite

Aggregator and commentary sites surfaced during search: MotorBiscuit, WebProNews, Red Banyan, AI Weekly, Slashdot, Shasta Unfiltered, ObscureIQ, Rain Intelligence, Consumer Rights Wiki. Useful for finding the primary sources. None belong in an APA reference list for this paper.

Also parked: the Toledo, Ohio misread leading to a gunpoint stop and police dog attack, and the Steven Melvin case in York County, South Carolina (2024). Both are LEAD status. They are vivid and would open the paper well, but a vivid anecdote you cannot document is a liability rather than an asset. Pull the primary reporting or leave them out.

---

## Niagara University database search strings

I cannot reach NU's proxy. Paste these into the databases directly. The peer-reviewed layer is the one gap the open web will not fill for you.

**Where to go first**

| Database | Why |
|---|---|
| HeinOnline | Law reviews. Best single source for algorithmic evidence and Daubert scholarship. |
| Nexis Uni / LexisNexis | Case law. This is how you run down S8 properly. |
| Criminal Justice Abstracts (EBSCO) | Policing technology, surveillance, ALPR studies. |
| Academic Search Complete (EBSCO) | General peer-reviewed backstop. |
| ProQuest Criminal Justice | Overlaps CJ Abstracts, catches dissertations. |

**Strings, paste verbatim**

```
("automated license plate" OR "license plate reader" OR ALPR OR "automatic number plate")
AND (admissib* OR evidentiary OR "chain of custody" OR authentication)
```

```
("algorithmic evidence" OR "machine-generated evidence" OR "automated decision")
AND ("trade secret" OR discovery OR disclosure OR contestab*)
```

```
(Daubert OR "Rule 702" OR "expert testimony")
AND ("error rate" OR validation OR reliability)
AND (algorithm* OR "digital forensic*" OR software)
```

```
(surveillance OR "predictive policing" OR "license plate")
AND (governance OR accountability OR oversight OR "due process")
AND (audit OR transparency)
```

```
"Flock Safety" OR "Vigilant Solutions" OR "hot list" OR hotlist
```

**Tactics that actually save time**

- Filter to peer-reviewed, 2020 to 2026. The doctrinal core is older but the ALPR-specific work is recent.
- In HeinOnline, find one strong law review article and mine its footnotes. Faster than more searching.
- Ask a NU librarian for an ILL on anything paywalled outside the subscription. Free, usually 24 to 72 hours, and it is the single most underused resource you have.
- When you pull a PDF, drop it in `07_Research_Materials/` and note in one line what claim it supports. That note is your process record.

---

## Standing rule

Nothing moves from LEAD to a citation without the primary document in hand. Given the subject of this paper, the sourcing has to be clean enough that the methodology is itself part of the argument.
