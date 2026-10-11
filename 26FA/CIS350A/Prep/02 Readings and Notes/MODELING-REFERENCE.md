# Modeling reference — the lenses and the lifecycle

## The one distinction that keeps showing up on exams

- **Analysis = the WHAT.** Identifies and structures system requirements.
- **Design = the HOW.** Specifies architecture, interfaces, data storage, and
  technical implementation.

Exam-safe phrasing: *Analysis identifies and structures system requirements; design
specifies the solution's architecture, interfaces, data storage, and technical
implementation.*

## SDLC — phase by purpose

Memorize the question each phase answers, not just the name.

| Phase | Question it answers |
|---|---|
| Envision / Plan | Should we build this? |
| Analysis | What does the system need to do? |
| Design | How will we build it? |
| Construct | Can we build it? |
| Test | Does it work correctly? |
| Implement | Can users actually use it? |
| Maintain | How do we keep it working and improve it? |

## Three approaches

- **Waterfall** — plan most of it first. Plan → analyze → design → build → test → deploy.
- **Agile** — build in iterations and learn. Plan (user stories) → build → test →
  release → learn → repeat. Course names **Scrum** and **Kanban**.
- **Hybrid** — assess project characteristics (radar chart), do preliminary analysis
  (BDUF / BRUF), then iterative construction.

## The seven artifacts

Each is one lens on the *same* system, not seven unrelated diagram rituals.

| Artifact | Models | Key question |
|---|---|---|
| Activity diagram | Workflow and decisions | What happens, in what order? |
| ER diagram | Data and relationships | What information exists, how is it connected? |
| User story | User need and outcome | Who needs what, and why? |
| Use case narrative | Actor/system interaction | How does a user accomplish a goal? |
| Wireframe | Screen structure | What does the interface contain? |
| Mockup | Finished visual interface | What will the interface look like? |
| Structured logic | Business rules and decisions | What rules control this process? |

```
                    SYSTEM
                       |
       +---------------+---------------+
       |               |               |
    PROCESS           DATA            USER
       |               |               |
 Activity diagram     ERD          User story
       |
       +---------------+
       |               |
   INTERFACE         LOGIC
       |               |
   Wireframe    Structured logic
```

## Worked example — drone infrastructure inspection platform

**User story**
> As an inspector, I want to review flagged images so that I can prioritize
> structural repairs.
>
> Shape: **WHO + WANTS WHAT + WHY.**

**Activity diagram (logic before boxes)**
```
Start -> Schedule inspection -> Conduct drone flight -> Upload images
      -> Analyze images -> [Defect found?]
                             |-- No  --> Archive --------+
                             |-- Yes --> Flag finding ---+
                                                         |
                                              Inspector review
                                                         |
                                              Generate report -> End
```

**ER diagram**
```
INSPECTOR --conducts--> INSPECTION --contains--> IMAGE --produces--> FINDING
```
Inspection has many Images; an Image may have many Findings.

**Wireframe**
```
+--------------------------------------+
| Drone Inspection Dashboard           |
+--------------------------------------+
| Site: Bridge 7                       |
| Date: 08/31/2026                     |
|                                      |
| Findings: 7                          |
| Critical: 1   High: 2   Medium: 4    |
|                                      |
| [ Review Images ] [ Generate Report ]|
+--------------------------------------+
```

**Structured logic**
```
IF finding severity = Critical
    THEN notify maintenance manager
ELSE IF finding severity = High
    THEN add to priority review queue
ELSE
    add to normal inspection queue
```

## Chapter 1 vocabulary to nail down

system · information system · stakeholder · systems analyst · requirement · analysis ·
design · SDLC · Waterfall · Agile · Hybrid

Be able to explain each in plain English, not just recognize it in a multiple-choice
stem — the exams are open-book, so recognition is cheap and application is what's
actually tested.

**Covered in class 2026-08-31 / 09-02 → [CH01-NOTES.md](CH01-NOTES.md).** Adds the
professor's own framing: BA vs. SA, business analysis, technology bias, Discover →
Structure → Transform → Communicate, intelligent modeling, the three requirement
categories, elicit vs. gather, perfect technology, and optimal vs. feasible.
