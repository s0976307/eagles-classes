# When the Machine Makes the Call
### Error Rates, Chain of Custody, and Contestability in Automated License Plate Reader Evidence

**Research prospectus, undergraduate research project**
Author: Caquan Palmer
Date: August 21, 2026

**Status: PARKED.** Superseded by the AI in Digital Forensics paper. Preserved because the audit findings in §4 are genuinely original and worth returning to.

---

## 1. The research problem

Automated License Plate Reader (ALPR) systems, most prominently those operated by Flock Safety, generate probabilistic machine assessments that are routinely treated by police as actionable fact. A camera reads a plate, software matches it against a hotlist, and an alert reaches an officer. The officer acts. Traffic stops, felony stops at gunpoint, arrests, and jail time follow.

The assessment is probabilistic. The consequence is not.

**Core research question:**

> When an automated system produces a probabilistic assessment that triggers consequential state action, what evidentiary and procedural conditions must be satisfied before that assessment is entitled to authority, and do current ALPR deployments satisfy them?

This is deliberately not "are ALPRs accurate?" and not "should police use AI?" Both are weaker questions. The first is empirical trivia; the second is unanswerable in ten pages. The question above is about the allocation of authority between a machine output and a human decision, and it is answerable with public evidence.

## 2. Thesis

ALPR evidence fails on all three of the criteria that digital forensics uses to decide whether machine-generated output can bear evidentiary weight (documented error rate, intact chain of custody, and contestability by the affected party) yet it is granted operational authority as though it satisfied all three. The failure is not that the technology is bad. The failure is that the governance around it never established the conditions under which its output could be trusted, and the legal system has so far declined to compel the disclosure that would let anyone find out.

## 3. Why this framing works

The three-part structure comes straight from digital forensics doctrine, which means the paper is grounded in the discipline rather than in opinion:

| Forensic requirement | Origin | ALPR status |
|---|---|---|
| Known or testable error rate | *Daubert v. Merrell Dow* (1993), FRE 702 | Vendor-claimed; independently audited rates diverge sharply |
| Chain of custody | Standard evidentiary practice | Two distinct break points (see §4) |
| Contestability and discovery | Due process; FRE 702 testability prong | Trade secret claims routinely block disclosure |

Each row is one body section. The paper writes itself once the frame is set.

## 4. The finding that carries the paper

The two largest public audits fail **for different reasons**, and that distinction is the paper's original contribution.

**Failure mode A: sensor error (the plate was read wrong).**
Roseville, California PD records obtained by *Business Insider* show that of 1,427 Flock alerts flagging vehicles as stolen or felony-connected across 2023 and 2024, **71% contained a misread plate.** This is an optical character recognition failure. The machine did not see what was there.

**Failure mode B: provenance error (the plate was read right, the database was wrong).**
A July 2026 LAPD Inspector General audit found **161 of 498 hotlist alerts were false**, roughly one in three. Critically, the cameras read the plates *correctly.* The hotlist was stale: recovered vehicles never cleared, outdated theft reports, uncorrected data entry. LAPD let its Flock contract expire following the audit.

**Why this matters.** These are not two data points about one problem. They are two separate links in the chain of custody, and they fail independently. A vendor can drive Failure A to zero with perfect OCR and Failure B remains untouched, because it lives in government databases the vendor does not control. Conversely, every accuracy statistic Flock publishes about plate-read precision is non-responsive to Failure B by construction. The company's claimed 93% capture rate across roughly 20 billion monthly scans is not a defense against the LAPD finding. It is a measurement of a different link in the chain.

This is the paper's sharpest move: *the industry's accuracy metric and the audits' error rate are not measuring the same thing, and the conflation is what allows the authority claim to survive.*

## 5. The contestability problem

Even where error is suspected, the affected person generally cannot inspect the system that flagged them. Cen, Ismael, and Zheng (2026) document that courts have overwhelmingly declined to compel disclosure of algorithmic evidence under both *Daubert* and *Frye*, producing what they term the **privatization of proof**: the evidence of how a system behaved remains corporate property, unavailable to the party it was used against.

Note the circularity, which the paper should state plainly:

> *Daubert* asks for a known error rate. The error rate is a trade secret. The trade secret claim is upheld. The evidence is admitted anyway.

The testability prong is satisfied in principle and defeated in practice.

## 6. The governance layer

Illinois provides the clearest case that the problem is structural rather than technical. An August 25, 2025 audit by Secretary of State Alexi Giannoulias found Flock Safety in violation of Illinois law. Sampling 12 local agencies, the audit found Flock lacked proper data-sharing safeguards and had run a pilot granting U.S. Customs and Border Protection access to Illinois ALPR data, a pilot Flock leadership itself was reportedly unaware of. A Palos Heights PD-associated account searched Oak Park data 28 times citing "immigration violation" as purpose, contrary to a 2023 Illinois statute barring exactly that use.

The governance reading: the system's own operator could not account for who was querying it or why. If the vendor cannot audit its own access logs, no defendant can meaningfully contest a query result derived from them, and the chain of custody is broken at the access layer rather than merely the sensor layer.

## 7. Method

Doctrinal and documentary analysis. No human subjects, no IRB requirement.

1. Establish the forensic admissibility standard from *Daubert*, FRE 702, and digital forensics literature on tool validation.
2. Assemble the public audit record (Roseville, LAPD OIG, Illinois SOS) and separate findings by failure mode.
3. Analyze the discovery and contestability gap using the algorithmic-evidence legal literature.
4. Derive a governance criteria set (provenance, auditability, contestability, human override authority, preserved record) and assess ALPR deployments against it.

## 8. Structure (target: 10 to 12 pages)

1. **Introduction.** The probabilistic assessment versus non-probabilistic consequence gap (1p)
2. **The forensic standard.** Daubert, FRE 702, error rate as admissibility condition (2p)
3. **Error rate in practice.** Roseville versus LAPD, the two failure modes (2 to 3p)
4. **Chain of custody.** Where ALPR evidence breaks: sensor, database, access log (2p)
5. **Contestability.** Privatization of proof, the Daubert circularity (2p)
6. **Governance criteria.** The five conditions, ALPR assessed against them (1 to 2p)
7. **Conclusion.** When does assisting become deciding? (1p)

## 9. Scope discipline

The Turnitin incident does not appear in this paper. It motivated the question; it is not evidence for the answer. ALPR carries the argument entirely on public record, which makes the paper harder to dismiss and removes any appearance of grievance. If a motivation line is ever needed, one neutral sentence suffices, but the current structure does not require it.

## 10. Stated assumptions

Set by me, not by you. Correct any that are wrong:

- Undergraduate research paper, roughly 10 to 12 pages
- APA 7th edition citation style
- Peer-reviewed source minimum unknown; source list is built to survive a strict requirement
- No IRB needed (documentary analysis only)
