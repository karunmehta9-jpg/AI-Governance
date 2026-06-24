# Document 02: Risk Management Summary

> **⚠️ Disclaimer:** This is a fictional case study created for portfolio and educational purposes only. The organisation, all systems, vendors, and personnel referenced are entirely fictional. No real entity is described, referenced, or disclosed.

**System:** TalentBridge Screener (ORG-AI-011)
**EU AI Act Reference:** Article 9 (Risk Management System)
**Document Type:** Deployer — with provider inputs
**Version:** 1.0 — October 2026

---

## 1. Risk Management System Overview

Article 9 of the EU AI Act requires that high-risk AI systems be subject to a risk management system that operates as a continuous, iterative process across the system's entire lifecycle. This document summarises the risk management approach for TalentBridge Screener.

This document is deliberately structured to show its relationship to Project 2's risk assessment of the predecessor system (ORG-AI-002): every risk identified below either directly addresses a finding from that earlier assessment, or represents a new risk consideration specific to procuring and deploying a replacement system correctly the second time.

---

## 2. Risk Identification

### R1 — Discriminatory Shortlisting Outcomes

**Description:** The model may produce shortlists that systematically disadvantage candidates from protected groups due to proxy discrimination, training data bias, or feature encoding — the same fundamental risk category as RISK-001 in Project 2's assessment of the predecessor system.

**Likelihood:** Medium — bias risk is inherent to NLP-based CV processing generally; the vendor has conducted pre-contractual bias testing (see Document 03)
**Impact:** High — employment access denied; legal and regulatory consequence
**Risk level:** High

**Mitigation measures:**
- Vendor-supplied bias audit against relevant protected characteristics, completed pre-contract
- Independent validation by the organisation on a representative candidate dataset, before go-live
- Ongoing monitoring of shortlisting rates by demographic proxy indicator
- Mandatory human oversight of all shortlisting decisions (Document 04)

**Residual risk:** Medium — mitigations reduce but do not eliminate bias risk; ongoing monitoring remains essential, not a one-time clearance

---

### R2 — Over-Reliance by HR Users

**Description:** HR coordinators may defer to AI recommendations without exercising genuine independent judgement, effectively making the system's output the decision rather than a recommendation — the precise failure mode that RISK-003 of Project 2 identified as Critical for the predecessor system, where no human checkpoint existed at all. Here, a checkpoint exists by design; this risk concerns whether it remains genuine under operational pressure.

**Likelihood:** Medium — a well-documented phenomenon in human-AI teaming generally
**Impact:** Medium — undermines human oversight; increases downstream exposure to R1
**Risk level:** Medium

**Mitigation measures:**
- Mandatory oversight training before system access is granted
- Interface design requiring active review of explanation text, not passive approval
- Override rate monitoring — unusually low override rates trigger coaching, on the principle (established in Project 2's companion governance memo) that meaningful oversight should show a normal, non-trivial rate of human disagreement with the AI
- Annual oversight effectiveness assessment

**Residual risk:** Low

---

### R3 — Scope Creep Beyond Intended Purpose

**Description:** The system is used beyond the approved CV screening and shortlisting function — for example, for interview scoring or internal mobility decisions — the same risk category as RISK-005 in Project 2's assessment.

**Likelihood:** Low — strong access controls and a clear policy prohibition are in place from launch, rather than added retroactively
**Impact:** Medium — different use cases may carry materially different risk profiles requiring separate assessment
**Risk level:** Low

**Mitigation measures:**
- Technical access controls limiting available system functions to the approved use case
- Policy prohibition documented and communicated at onboarding
- Annual scope attestation by the system owner, per the Responsible AI Policy

**Residual risk:** Low

---

### R4 — Data Minimisation Failure

**Description:** The system processes more candidate personal data than is necessary for its stated purpose.

**Likelihood:** Low — the system is designed to process CV content only
**Impact:** Medium — data protection compliance; candidate trust
**Risk level:** Low

**Mitigation measures:**
- Data flows documented and validated against the data minimisation principle
- Vendor data processing agreement in place before go-live
- Data Protection Officer review completed pre-contract, not deferred to post-launch

**Residual risk:** Low

---

### R5 — Vendor Model Changes Without Notification

**Description:** Vendor G updates the underlying model without adequate notification, introducing changes that affect performance, fairness, or compliance — directly addressing RISK-003 of Project 2's assessment of a different system, where undisclosed vendor retraining was identified as a governance gap, and applying the lesson proactively here at contract stage rather than discovering the same gap after the fact.

**Likelihood:** Medium — SaaS vendors update models on a regular cycle as standard practice
**Impact:** High — a material model change could re-introduce risks the organisation believed were already controlled
**Risk level:** High

**Mitigation measures:**
- Contract requires a minimum 60 days' notice of any material model change
- "Material change" is defined explicitly in the contract: any update affecting model architecture, training data, or feature set
- The organisation retains the right to conduct its own validation testing before accepting any update into production
- The organisation retains the right to delay a model update pending its own validation

**Residual risk:** Low — this is a clear example of a risk being substantially better controlled the second time, precisely because the relevant lesson had already been learned elsewhere in the portfolio before this contract was negotiated

---

### R6 — Candidate Rights and Transparency Failure

**Description:** Candidates are not informed that AI is used in the recruitment process, or cannot exercise rights to explanation or challenge.

**Likelihood:** Low — controls are designed in from the outset, rather than retrofitted
**Impact:** Medium to High — legal non-compliance; regulatory consequence; candidate harm
**Risk level:** Medium

**Mitigation measures:**
- Candidate-facing disclosure at the application stage: AI is used for initial CV screening
- Explanation capability built into the system: a human-readable score rationale for every candidate
- A defined challenge mechanism: candidates who receive a rejection can request human review
- Legal review of all candidate-facing communications completed before go-live

**Residual risk:** Low

---

## 3. Pre-Deployment Risk Evaluation

| Evaluation | Owner | Standard | Status |
|---|---|---|---|
| Vendor bias audit | Vendor G | Demographic parity across available proxy characteristics | Completed — results reviewed |
| Independent fairness validation | AI Governance Programme Office + external evaluator | Demographic parity ratio of at least 0.80 | In progress |
| Data protection impact assessment | Data Protection Officer | Standard DPIA requirements | Completed |
| Technical documentation review | AI Governance Programme Office + Legal | Annex IV completeness | In progress |
| Adversarial and robustness testing | Information Security | Adversarial input testing protocol | Scheduled |
| User acceptance testing with oversight training | HR Director + AI Governance Programme Office | 100% of system users trained and UAT complete | Scheduled |

**Go-live gate:** every evaluation above must be complete, with formal sign-off from the AI Governance Programme Office, the Data Protection Officer, Legal, and the HR Director, before production deployment — consistent with Stage 5 of Project 3's AI Use Case Review and Approval Process.

---

## 4. Foreseeable Misuse Scenarios

| Scenario | Risk | Mitigation |
|---|---|---|
| A hiring manager under time pressure asks a coordinator to "just send the top 3" without the coordinator reviewing the explanation text for any of them | Review step is technically performed but not genuinely exercised, converting recommendation into de facto decision | Minimum review-time monitoring per candidate (Document 06); coaching escalation triggered below threshold |
| A business unit attempts to repurpose shortlist output as an input to a separate internal succession-planning exercise | Use of the system's output outside its approved purpose, for a decision category that was never assessed for this system | Technical export controls on shortlist data; any cross-functional data request requires a fresh AUCR per Project 3's process |
| A candidate, aware that certain keywords are known to score well, pads their CV with role-irrelevant buzzwords drawn from the published job description | Score inflation unrelated to genuine candidate suitability, degrading the model's practical usefulness | Explanation text exposes which specific elements drove a high score, allowing a human reviewer to discount keyword-stuffing that does not reflect genuine substantiated experience |
| A new hiring manager, unfamiliar with the organisation's policy, asks IT to grant them direct system access without completing the mandatory oversight training | Untrained reviewer exercising oversight authority without the knowledge needed to do so meaningfully | Access provisioning is gated technically on training-completion status, not left to a manual checklist a manager could bypass |

---

## 5. Residual Risk Acceptance

Following implementation of all mitigation measures above, the overall residual risk position is assessed as **Medium**.

The residual Medium rating reflects that:
- AI-based CV processing carries an inherent bias risk that ongoing monitoring can detect but never entirely eliminate
- Human oversight remains a continuing dependency — if oversight quality degrades over time (the "oversight capacity erosion" risk named explicitly in Project 3's Responsible AI Policy), residual risk increases correspondingly

The AI Governance Committee has reviewed and accepted this residual risk position as consistent with the organisation's risk appetite for operational AI risk, the requirement under Article 9 to reduce risk to an acceptable level rather than to an unachievable zero, and the understanding that ongoing monitoring (Document 06) is what keeps this acceptance valid over time rather than a one-time judgement made at launch and never revisited.

**Acceptance recorded:** AI Governance Committee, pending formal approval date ahead of the targeted go-live.

---

*Risk management is a continuous process. This document will be updated following any material incident, any material system change, or at the system's annual review, consistent with the lifecycle requirements set out in Project 3.*
