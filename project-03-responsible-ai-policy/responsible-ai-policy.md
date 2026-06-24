# Responsible AI Policy

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**Organisation:** The organisation
**Policy Owner:** Chief Risk Officer
**Version:** 1.0
**Effective Date:** May 2026
**Next Review Date:** May 2027
**Classification:** Internal

---

## 1. Purpose

This policy sets out the organisation's commitments and requirements for the responsible development, procurement, deployment, and operation of artificial intelligence systems.

Artificial intelligence creates real opportunity for the organisation — better-informed risk decisions, faster and more consistent customer service, more efficient operations. It also creates real risk: to the fairness of outcomes for individuals, to customer and employee trust, to regulatory standing, and to the organisation's reputation if that trust is broken.

This policy exists so that the organisation captures the first kind of value without absorbing the second kind of risk unmanaged. It is written on the premise that a principle which does not change a real decision is not a governance control — it is a sentence. Every commitment below is paired with the specific practice that makes it operational.

## 2. Scope

This policy applies to:

- All AI systems developed internally by the organisation's teams
- All AI systems procured from external vendors and deployed by the organisation
- All employees, contractors, and third parties involved in developing, procuring, deploying, or operating AI systems on the organisation's behalf
- All jurisdictions in which the organisation operates

For the purposes of this policy, an **AI system** is any machine-based system that generates outputs — predictions, recommendations, decisions, classifications, or content — that influence a real-world or virtual outcome, based on objectives defined at design or training time. This includes, but is not limited to: machine learning models, large language models and other generative systems, automated or semi-automated decision-making systems, recommendation engines, biometric identification or verification systems, and computer vision systems. A tool's marketing label is irrelevant to whether this policy applies — a system described as "advanced analytics" or "smart automation" is in scope if it meets this definition in substance.

## 3. Principles

The organisation's responsible AI programme rests on five principles. Each is paired immediately with the practices that operationalise it — the test for whether a principle belongs in this policy is whether a specific, checkable practice can be written underneath it.

### 3.1 Fairness

**Commitment:** AI systems used by the organisation will not unlawfully discriminate against individuals on the basis of protected characteristics, and will be designed, tested, and monitored to identify and mitigate bias throughout their operational life, not only at the point of initial deployment.

**What this means in practice:**
- Before deployment, any AI system whose output affects an individual must be assessed for potential bias across the protected characteristics relevant to its context and jurisdiction
- High-risk AI systems must undergo a documented, independent bias evaluation before go-live, and at intervals defined in the system's approval conditions thereafter — "independent" means conducted or verified by a function other than the one that built or procured the system
- A bias evaluation that has not yet been completed is not a deferred formality; until it is complete, the system's fairness properties are unknown, not presumed acceptable, and this status must be reflected honestly in the system's risk rating
- Where a system is found to produce discriminatory outcomes, the default response is suspension or constrained operation until the issue is remediated and re-validated — continued operation pending a fix requires an explicit, documented risk acceptance by the AI Governance Committee, not a default assumption that the system may keep running while the fix is developed
- Any scoring, ranking, or shortlisting output that affects an individual must be reviewed by a qualified human before that output is acted upon in a way that is materially adverse to that individual

### 3.2 Transparency

**Commitment:** The organisation will be open about its use of AI where that use affects individuals, and will ensure that AI-influenced decisions affecting individuals can be explained in terms a layperson can understand.

**What this means in practice:**
- Customers, employees, and external applicants will be informed when an AI system plays a material role in a decision affecting them, using language that does not require technical literacy to understand
- AI systems that make or materially inform decisions about individuals must be capable of producing a human-interpretable explanation for an adverse outcome — a numeric score alone, without an accompanying explanation of what drove it, does not satisfy this requirement
- Internal users acting on AI-generated outputs must be informed of the system's known limitations, error rates, and the categories of cases in which the system is known to perform less reliably
- The organisation will maintain a current AI system inventory, structured along the lines established in Project 1 of this portfolio, available to the Board, regulators, and auditors on request
- Disclosure obligations are treated as a continuing state, not a one-time notice — a disclosure mechanism implemented at launch but allowed to lapse or degrade over time (for example, present on one channel but not a newer one) is treated as a compliance gap, not a historical fact to note and move past

### 3.3 Accountability

**Commitment:** Every AI system used by the organisation will have a single named individual accountable for its governance, and that accountability will not be diluted by the involvement of a vendor, a committee, or a development team.

**What this means in practice:**
- A system owner must be designated before any AI system is approved for deployment, and that designation is recorded in the AI system inventory, not merely in an email or a meeting note
- The system owner is accountable for the system operating within its approved scope and within the bounds of this policy — accountability is personal, not organisational; "the team" is not an acceptable answer to who is responsible when something goes wrong
- System owners are responsible for escalating material issues to the AI Governance Programme Office promptly, and the definition of "material" is set out in the AI Use Case Review and Approval Process, not left to individual judgement alone
- Where AI is procured from a vendor, the organisation's system owner retains full accountability for how the system is used internally — a vendor's own assurances about its product's safety or fairness reduce the system owner's diligence burden, but never transfer their accountability
- The AI Governance Committee is, in turn, accountable to the Board for the programme as a whole — accountability runs in an unbroken chain from individual system owner to Board, with no link in that chain permitted to be informal or undocumented

### 3.4 Safety and Robustness

**Commitment:** AI systems will be designed, tested, and monitored to perform reliably, including under adverse, adversarial, or simply unexpected conditions that differ from the conditions under which the system was originally validated.

**What this means in practice:**
- AI systems must be tested against adversarial inputs and realistic edge cases before deployment, with the scope and depth of testing scaled to the system's risk tier
- Performance thresholds — accuracy, error rate, or another metric appropriate to the system — must be defined explicitly at the point of approval, not derived informally after the system is already live
- Performance degradation below an approved threshold triggers a formal review automatically; it is not left to a system owner's discretion to decide whether a breach of a defined threshold warrants attention
- AI systems must not be deployed in safety-critical contexts without specific, named Board approval and a documented safety analysis covering foreseeable failure modes
- A human override capability must exist and be operationally tested — not merely theoretically present in a system's design documentation — for every AI system whose output affects an individual

### 3.5 Human Oversight

**Commitment:** The organisation will maintain human oversight of AI systems that is meaningful in substance, not merely present in form, particularly where AI outputs affect individuals' rights, opportunities, employment, or access to services.

**What this means in practice:**
- AI outputs that inform a consequential decision about an individual must be reviewed by a qualified human before that decision is communicated, and that review must be capable of changing the outcome — a workflow in which a human technically sees the output before it is acted on, but has no realistic opportunity, time, or authority to alter it, does not satisfy this commitment
- A specific and recurring governance failure mode — addressed directly because it is easy to overlook — is **oversight capacity erosion**: a human review control that was genuinely meaningful at launch can quietly become a rubber stamp as system volume grows faster than review headcount or review time per case shrinks under operational pressure. System owners are required to monitor review throughput (volume per reviewer, time per review) as a standing control, not only the existence of the review step itself
- High-risk AI systems must have a documented human oversight procedure that specifies, concretely, the criteria under which a reviewer is expected to override the system's output, not merely state that override is "possible"
- Employees responsible for human oversight of an AI system must receive role-specific training on that system before assuming review responsibility, and that training must be refreshed if the system's behaviour changes materially

## 4. AI Lifecycle Governance Requirements

This section sets out the governance requirements that apply at each stage of an AI system's life, from first idea to retirement.

### 4.1 Ideation and Use Case Submission

Before any AI system is developed or procured, the relevant business owner must submit an AI Use Case Request to the AI Governance Programme Office, in line with the AI Use Case Review and Approval Process. The request must capture, at minimum, the system's business purpose, its intended internal users, the individuals it will affect externally, the data it will process, and the human oversight mechanism proposed for it.

No development or procurement activity that assumes approval — including signing a vendor contract, beginning model training on production data, or announcing the system internally as a confirmed initiative — may proceed before triage of the submission is complete.

### 4.2 Risk Assessment and Classification

Every AI system is assessed and classified before deployment along three dimensions:

- **EU AI Act risk tier** (Unacceptable / High / Limited / Minimal), determined with reference to Annex III and the relevant transparency articles
- **NIST AI RMF maturity baseline**, to identify governance gaps independent of legal risk tier, consistent with the methodology used in Project 1
- **Organisational risk rating**, combining the regulatory classification with business-specific factors such as the scale of affected individuals and the system's centrality to a core compliance control

High-risk systems require Enhanced Review under the AI Use Case Review and Approval Process, including, where appropriate, an external or independent assessor for fairness evaluation.

### 4.3 Approval and Go-Live

No AI system may be deployed to a production environment without formal, documented approval. Approval authority scales with risk tier:

| Risk Tier | Approver |
|---|---|
| Minimal Risk | AI Governance Programme Office |
| Limited Risk | AI Governance Programme Office, with System Owner sign-off |
| High Risk | AI Governance Committee |
| Unacceptable Risk | Prohibited — no approval pathway exists |

Approval, including any conditions attached to it, is documented and recorded in the AI system inventory before go-live, not retrospectively.

### 4.4 Monitoring and Review

Deployed AI systems remain subject to ongoing monitoring for the duration of their operational life:

- Performance metrics — accuracy, fairness indicators, error rates, and any other metric specified at approval — are tracked at the interval set at approval, not at whatever cadence proves administratively convenient
- Material performance degradation or an AI-related incident triggers a formal out-of-cycle review automatically
- All high-risk systems receive, at minimum, an annual formal review by the AI Governance Programme Office, in addition to any event-driven review
- System owners attest annually, in writing, to continued compliance with the system's approved scope and with this policy

### 4.5 Decommissioning

When an AI system is retired, the system owner is responsible for: ensuring data retention and deletion proceed in accordance with the organisation's broader data governance policy; updating the AI system inventory to reflect the retirement; notifying the AI Governance Programme Office formally; and documenting any lessons learned that should inform the governance programme's future practice, including any near-miss that did not become a full incident but revealed a control weakness worth recording.

## 5. Vendor and Third-Party AI

Where the organisation deploys AI systems developed by external vendors:

- The procurement process must include a structured AI governance assessment before contract signature, not as an optional add-on
- Vendor contracts must include provisions requiring the vendor to comply with applicable AI regulation (including the EU AI Act where applicable), to provide adequate technical documentation, to notify the organisation of material model changes — including retraining — with sufficient advance notice for the organisation to validate the change before it takes effect in production, and to support the organisation's audit rights
- The organisation's system owner remains fully accountable for the governance of a vendor-supplied AI system in exactly the same way as for an internally developed one; vendor accountability under a contract and the organisation's own regulatory accountability as a deployer are separate obligations that do not substitute for one another
- The AI Governance Programme Office maintains a vendor AI register as a component of the broader AI system inventory, recording, at minimum, each vendor's contractual AI governance commitments and the status of any outstanding information requests made to that vendor

## 6. Roles and Responsibilities

| Role | Responsibility |
|---|---|
| **Board Risk & Audit Committee** | Strategic oversight of the AI governance programme; approval authority for high-risk systems escalated to Board level; annual review of the AI governance programme report |
| **Chief Risk Officer** | Policy owner; chairs the AI Governance Committee |
| **AI Governance Committee** | Cross-functional governance body; approves high-risk system deployments; reviews material incidents; oversees programme-wide compliance |
| **AI Governance Programme Office** | Day-to-day programme coordination; use case triage; documentation; training delivery; regulatory monitoring; reporting |
| **System Owners** | Personal accountability for an individual system; day-to-day oversight; escalation of material issues |
| **Data Protection Officer** | GDPR and AI Act data governance interface; co-reviews assessments involving personal data |
| **Legal / Compliance** | Regulatory interpretation; contract review; incident escalation advice |
| **Information Security** | Cybersecurity and adversarial robustness assessment for AI systems |
| **ML Engineering / Data Science** | Technical implementation of governance controls; model and technical documentation |

## 7. Training

All employees involved in developing, procuring, deploying, or overseeing AI systems must complete:

- **AI Governance Fundamentals** (all employees in scope) — completed annually
- **Human Oversight of AI Systems** (employees responsible for reviewing AI outputs) — completed at onboarding to the role and refreshed annually, or sooner if the relevant system's behaviour changes materially
- **AI Risk Assessment** (AI Governance Programme Office staff and system owners) — completed at appointment to the role

## 8. Policy Breach

A breach of this policy — including deploying an AI system without approval, failing to implement a required human oversight control, allowing a meaningful oversight control to degrade into a rubber stamp without escalating that fact, or misrepresenting a system's risk classification — is treated as a conduct matter and may result in disciplinary action.

Where a breach has caused or risked harm to individuals, or created regulatory non-compliance, the Chief Compliance Officer must be notified without delay and a formal incident response initiated under the organisation's AI Incident Response Procedure.

## 9. Review and Updates

This policy will be reviewed annually, or sooner upon any material change in: applicable law or regulation, including the EU AI Act or its national implementing measures; the organisation's AI portfolio or governance operating model; or a material AI incident, internal or industry-wide, that reveals a gap this policy should address.

The Chief Risk Officer is responsible for initiating each review.

---

*Version history available from the AI Governance Programme Office.*
*Queries: ai-governance@example-organisation.test*
