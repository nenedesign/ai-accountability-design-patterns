# AI Accountability Audit

A scorable checklist for evaluating an AI-assisted product against the 12 accountability concepts. Use in design reviews, heuristic evaluations, or pre-launch assessments.

---

## How to Score

Each item is scored 0 to 3:

- **0**: Not present
- **1**: Partially present or inconsistently applied
- **2**: Present and functional
- **3**: Present, consistent, and exemplary

**Maximum score: 192**

| Score range | Interpretation |
|---|---|
| 154–192 | Strong accountability posture |
| 115–153 | Good with notable gaps |
| 77–114 | Significant gaps requiring remediation |
| Below 77 | Foundational accountability work required |

---

## 1. Traceability

| # | Item | Score (0–3) |
|---|------|-------------|
| 1.1 | AI outputs display the source data or documents they drew from, inline with the output | |
| 1.2 | Changes to records, artifacts, or documents show who made them and when, at the point of display | |
| 1.3 | The reasoning path from input to AI conclusion is accessible to the user, not hidden in a log | |
| 1.4 | Modified records show an explicit diff: what changed, not just that something changed | |
| 1.5 | Attribution is visible without navigating away from the artifact | |
| 1.6 | AI-generated content is visually distinguished from human-generated content | |

**Section total: /18**

---

## 2. Auditability

| # | Item | Score (0–3) |
|---|------|-------------|
| 2.1 | The system maintains an append-only log: records cannot be edited or deleted after creation | |
| 2.2 | Every significant user and system action is recorded with actor, action, timestamp, and object | |
| 2.3 | Audit records are exportable in a format readable by a reviewer who was not present | |
| 2.4 | Key approvals and sign-offs carry a non-repudiation record (actor identity + timestamp + signed action) | |
| 2.5 | The audit log captures AI actions (model calls, classifications, recommendations) not only human actions | |
| 2.6 | Audit records include enough context for a reviewer to reconstruct what happened without additional information | |

**Section total: /18**

---

## 3. Provenance

| # | Item | Score (0–3) |
|---|------|-------------|
| 3.1 | Every data item or artifact displays its origin source at the point of use | |
| 3.2 | AI model documentation (model card or equivalent) is accessible from within the product | |
| 3.3 | The model card or system card includes training data, intended use cases, known limitations, and out-of-scope uses | |
| 3.4 | Artifacts from external sources are labeled with retrieval timestamp and source identifier | |
| 3.5 | Origin information persists with the artifact as it moves through the workflow | |

**Section total: /15**

---

## 4. Breadcrumbing

| # | Item | Score (0–3) |
|---|------|-------------|
| 4.1 | Users can see where they are within the product structure at all times | |
| 4.2 | Sequential workflows display the user's current step and total steps remaining | |
| 4.3 | User annotations, flags, and highlights are attached to artifacts and form a navigable trail | |
| 4.4 | Users can review a history of which artifacts they accessed and in what order during a session | |
| 4.5 | The trail distinguishes between AI-generated conclusions and human-validated ones | |

**Section total: /15**

---

## 5. Chain of Custody

| # | Item | Score (0–3) |
|---|------|-------------|
| 5.1 | Every artifact has a custody log recording who has accessed it, when, and what they did | |
| 5.2 | Each transfer of an artifact between parties is documented at the moment of transfer, not reconstructed afterward | |
| 5.3 | Evidence is displayed in a read-only mode that prevents modification during review | |
| 5.4 | Cryptographic hashes are computed at acquisition and verifiable at any point in the review process | |
| 5.5 | AI processing of an artifact is recorded in the artifact's custody log, not only in system logs | |
| 5.6 | The custody log identifies the AI model version involved in any AI-assisted processing step | |

**Section total: /18**

---

## 6. Explainability

| # | Item | Score (0–3) |
|---|------|-------------|
| 6.1 | AI outputs include a confidence level expressed in terms the domain user can interpret | |
| 6.2 | The AI provides a natural-language summary of why it reached its conclusion | |
| 6.3 | For structured data inputs, the AI surfaces which factors most influenced the output | |
| 6.4 | Every AI-generated claim is linked to the specific source it drew from | |
| 6.5 | Confidence levels are calibrated: stated confidence reflects actual accuracy | |
| 6.6 | Explanations are written in the user's domain vocabulary, not in machine learning terminology | |

**Section total: /18**

---

## 7. Reproducibility

| # | Item | Score (0–3) |
|---|------|-------------|
| 7.1 | AI analyses are stored with a snapshot of the exact model version, configuration, and data version used | |
| 7.2 | An analysis state can be shared or exported in a form that another person can recreate | |
| 7.3 | The system provides a step-by-step methodology disclosure for any AI-generated finding | |
| 7.4 | Users are notified when a model update may affect previously produced analyses | |
| 7.5 | The methodology disclosure is written to withstand challenge by a party with an opposing interest | |

**Section total: /15**

---

## 8. Lineage

| # | Item | Score (0–3) |
|---|------|-------------|
| 8.1 | Users can see what transformations were applied to a data item before it reached them | |
| 8.2 | Every processing step applied to an artifact is logged in sequence with timestamp and parameters | |
| 8.3 | The system can show all upstream data items that contributed to a given output | |
| 8.4 | Lineage information is presented in a form accessible to domain users, not only data engineers | |
| 8.5 | If a source data item is found to be compromised, the system can identify which outputs are affected | |

**Section total: /15**

---

## 9. Responsibility Assignment

| # | Item | Score (0–3) |
|---|------|-------------|
| 9.1 | Consequential actions require an explicit human approval before execution | |
| 9.2 | The interface displays the user's role and what they are accountable for at the moment of sign-off | |
| 9.3 | Responsibility transfers between users are recorded with both parties, timestamp, and any conditions | |
| 9.4 | When a human overrides an AI recommendation, the system prompts for and records a justification | |
| 9.5 | Approval records identify the human, not only the system or role | |
| 9.6 | Responsibility handoffs include structured context: decisions made, AI recommendations accepted and rejected, open questions | |

**Section total: /18**

---

## 10. Integrity

| # | Item | Score (0–3) |
|---|------|-------------|
| 10.1 | Cryptographic hashes are computed at acquisition and displayable at any point in the review process | |
| 10.2 | A visible alert appears when an artifact's hash does not match its original value | |
| 10.3 | Audit logs and evidence stores use append-only or WORM storage at the infrastructure level | |
| 10.4 | Artifacts are cryptographically signed at creation | |
| 10.5 | The system discloses whether AI processing preserved or modified the original artifact | |

**Section total: /15**

---

## 11. Transparency

| # | Item | Score (0–3) |
|---|------|-------------|
| 11.1 | A system card or model card is accessible from within the product, not only in external documentation | |
| 11.2 | The product communicates what the AI can and cannot do at the point of first use | |
| 11.3 | Data usage: what the AI was trained on and what it sends to third parties: is disclosed | |
| 11.4 | When the AI is operating at the edge of its reliable range, a limitation notice is displayed | |
| 11.5 | Users can access the current AI model version and its capabilities without leaving their active workflow | |

**Section total: /15**

---

## 12. Observability

| # | Item | Score (0–3) |
|---|------|-------------|
| 12.1 | AI system health is monitored and tracked over time | |
| 12.2 | Model performance metrics (accuracy, drift) are tracked and acted on | |
| 12.3 | End users receive an in-product signal when AI system reliability is degraded | |
| 12.4 | The product has an explicit degraded-mode UI state that communicates impact and guidance to users | |
| 12.5 | Observability data is reviewed regularly, not only when an incident occurs | |

**Section total: /15**

---

## Summary

| Concept | Max | Score |
|---|---|---|
| 1. Traceability | 18 | |
| 2. Auditability | 18 | |
| 3. Provenance | 15 | |
| 4. Breadcrumbing | 15 | |
| 5. Chain of Custody | 18 | |
| 6. Explainability | 18 | |
| 7. Reproducibility | 15 | |
| 8. Lineage | 15 | |
| 9. Responsibility Assignment | 18 | |
| 10. Integrity | 15 | |
| 11. Transparency | 15 | |
| 12. Observability | 15 | |
| **Total** | **192** | |
