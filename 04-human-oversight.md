# Document 04: Human Oversight Mechanisms

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**System:** TalentBridge Screener (ORG-AI-011)
**EU AI Act Reference:** Article 14 (Human Oversight)
**Document Type:** Deployer
**Version:** 1.0 — October 2026

---

## 1. Purpose

Article 14 of the EU AI Act requires high-risk AI systems to be designed to enable effective human oversight. This document describes how the organisation implements that requirement for TalentBridge Screener, building directly on the specific human oversight model recommended in Project 2's risk assessment of the predecessor system, and on the "oversight capacity erosion" concept named explicitly in Project 3's Responsible AI Policy.

---

## 2. Oversight Design Principles

This system's oversight model rests on three principles, the first of which is a direct, named correction of the predecessor system's most severe finding:

**1. The predecessor system's core failure must be structurally impossible to repeat.** Project 2's risk assessment found that ORG-AI-002 allowed automated rejection communications to be sent without any human checkpoint. TalentBridge Screener is built so that this is not a policy that staff are asked to follow, but a technical constraint: the system has no capability to trigger a candidate communication directly. Every communication is sent through a separate workflow step that requires an authenticated human action.

**2. A reviewer's disagreement with the AI should be the expected, ordinary case some of the time — not a rare exception.** A review process that almost never produces a different outcome than the AI recommended is itself a warning sign, not a sign of a well-functioning model, because it suggests the review may have become passive.

**3. Oversight quality should be measured the same way the model's own performance is measured** — with defined metrics, defined thresholds, and a defined escalation response — rather than treated as a soft cultural matter that resists measurement.

---

## 3. Oversight Roles and Responsibilities

### HR Coordinator (Primary Reviewer)

**Oversight responsibilities:**
- Review the full AI-generated shortlist, including candidates the system ranked lower, not only the highest-ranked subset
- Read the explanation text for each candidate under serious consideration
- Confirm, modify, or substantially rebuild the shortlist based on independent judgement
- Record the specific reason for any modification in a structured field, not free text alone, to enable pattern analysis across many decisions over time
- Escalate any suspected systemic issue with the system's behaviour to the relevant Functional AI Champion

**Authority:** full authority to override the AI shortlist for any documented reason, without requiring upward justification for the override itself — only the documentation of it.

---

### Hiring Manager (Secondary Review for Senior Roles)

**Oversight responsibilities:**
- Review and approve the coordinator-reviewed shortlist for roles above a defined seniority threshold
- May request further modification before any candidate invitation is issued
- Is shown, explicitly, that the shortlist passed through AI-assisted initial screening, rather than this being an implicit fact the manager might not otherwise register

---

### HR Director (Governance Oversight)

**Oversight responsibilities:**
- Monthly review of override patterns across all active hiring processes, looking specifically for any individual coordinator or business unit with an anomalously low override rate
- Quarterly review of shortlisting statistics by available demographic proxy
- Serves as the named escalation point if a coordinator suspects the system is behaving inconsistently or unfairly
- Annual attestation of the system's continued compliance with the Responsible AI Policy and this oversight procedure

---

## 4. Oversight Workflow

```
[1] CANDIDATE APPLIES
      |
      v
[2] CV ingested by TalentBridge Screener
      |
      v
[3] AI generates ranked shortlist, fit scores, and explanation text
      |
      v
[4] HR COORDINATOR REVIEW
      - Reviews the full shortlist, not only top-ranked candidates
      - Reads explanation text and weighs it against any context
        the CV does not capture
      - Accepts / modifies / substantially rebuilds the shortlist
      - Records a structured reason for any modification
      |
      v
[5] SENIOR-ROLE GATE (roles above seniority threshold only)
      - Hiring manager reviews coordinator-approved shortlist
      - May request further modification
      |
      v
[6] CANDIDATE COMMUNICATIONS
      - System has no technical capability to send these directly
      - A coordinator must trigger the communication step manually,
        after the review above is recorded as complete
      |
      v
[7] OUTCOME LOGGING
      - AI recommendation, coordinator decision, and any divergence
        recorded for the full retention period
```

The single structural difference from the predecessor system's workflow, worth stating plainly: in the predecessor system, step 6 could be triggered automatically once a score crossed a threshold. In this system, step 6 has no automated trigger path at all — it is a deliberate design constraint, not merely a procedural instruction that staff are trusted to follow correctly every time.

---

## 5. Override and Challenge Mechanism

### Internal override

A coordinator overrides the AI recommendation by selecting a structured reason category (for example: "explanation text does not reflect relevant unlisted experience known to the coordinator," "candidate flagged by the special category data filter requires full manual assessment," "role requirements changed after the job description was finalised") and may add free-text detail beyond the category if useful. The structured category is mandatory; the free text is optional. This is a deliberate design choice: structured categories are what make override patterns analysable in aggregate over time, while free text alone, though useful for an individual case, does not scale into a meaningful trend analysis.

### Candidate challenge mechanism

Candidates who receive a rejection are informed of their right to request a human review, with a named internal contact route for doing so. Challenges are triaged by the HR Director, and any challenge that raises a plausible concern about systemic unfairness — rather than a dispute about a single candidate's individual qualifications — is reviewed by a senior HR manager who had no role in the original decision, to avoid the reviewer marking their own work.

---

## 6. System Features Supporting Oversight

| Feature | Purpose |
|---|---|
| Full-shortlist visibility, not threshold-gated | Ensures reviewers can consider candidates the model ranked lower, rather than only ever seeing a pre-filtered "top N" |
| Structured override-reason categories | Enables aggregate pattern analysis of why and when humans disagree with the AI, not just individual case records |
| No direct communication-trigger capability | Makes the predecessor system's core failure structurally, not just procedurally, impossible to repeat |
| Confidence-band display | Distinguishes candidates the model scored with high confidence from those near a decision boundary, prompting closer reviewer attention to the latter |
| Override-rate and review-time dashboards | Give the HR Director the same kind of standing visibility into oversight health that a performance dashboard gives into model health |

---

## 7. Training Programme

**Module 1 — How TalentBridge Screener works:** what the model does and does not do, how scores are generated, and what the explanation text does and does not capture about a candidate.

**Module 2 — Why this system is different from its predecessor:** a direct briefing on the governance findings from Projects 1 and 2 that led to this system's procurement, so reviewers understand the override expectation is not arbitrary process but a response to a documented prior failure.

**Module 3 — Practical override scenarios:** structured exercises using realistic but fictional CV examples, asking trainees to decide whether and how to override, with facilitator discussion of the reasoning.

**Module 4 — Candidate rights and challenge handling:** how to recognise and route a candidate challenge, and the standard the organisation expects reviewers to hold themselves to when explaining decisions if asked.

**Completion requirement:** 100% of coordinators and relevant hiring managers complete training before system access is granted; access provisioning is technically gated on training completion (Document 02, R2 mitigation), not left to a manual check a manager could bypass under time pressure.

---

## 8. Oversight Effectiveness Monitoring

| Metric | Frequency | Trigger for Investigation |
|---|---|---|
| Override rate (shortlist modifications) | Monthly | A rate below the established normal range for two consecutive months, suggesting passive acceptance |
| Median review time per shortlist | Monthly | A sustained drop below the level established as adequate during acceptance testing |
| Distribution of override-reason categories | Quarterly | A category distribution that shifts suddenly, which may indicate either a genuine emerging issue with the model or a change in reviewer behaviour worth understanding |
| Candidate challenge rate | Quarterly | A rate materially above the organisation's established baseline for this kind of process |
| Training completion currency | Ongoing | Any drop below 100% triggers automatic access suspension for the relevant individual |

---

*This oversight procedure is a live document. Material changes require AI Governance Programme Office review and approval, consistent with the change-control requirements established in Project 3.*
