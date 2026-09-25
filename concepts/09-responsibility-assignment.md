# Concept 09: Responsibility Assignment

## Definition

Responsibility assignment is the explicit identification and recording of which human is accountable for an AI-assisted decision. When AI contributes to a recommendation, classification, or action, a human must own the outcome. Responsibility assignment is the design mechanism that makes that ownership visible, captured, and non-repudiable.

## Why It Matters for AI-Assisted Products

AI systems produce outputs. Humans bear responsibility for what is done with them. Without explicit responsibility assignment, accountability diffuses across the system: the AI produced it, the analyst accepted it, the supervisor approved it, but no one is on record as the decision-maker. In regulated industries, investigative contexts, and high-stakes environments, diffused accountability is not accountability.

Responsibility assignment is the design property that ensures a human is always on record as the decision-maker, regardless of how much the AI contributed.

## Established Patterns

### Approval Signature [Established]
Before a consequential action is taken, a named human provides an explicit sign-off. The approval is recorded with actor identity, timestamp, and the specific action approved. DocuSign, legal workflow platforms, and clinical order entry systems implement this. In AI-assisted systems: any AI recommendation that triggers a high-stakes action requires an approval signature before execution.

### Role Display at Point of Action [Established]
At the moment a user takes a consequential action, the interface displays their role and what they are accountable for by taking it. Implemented in compliance workflow tools and clinical sign-off flows. The display makes the responsibility explicit at the moment of decision, not after.

### Delegation Trail [Established]
When responsibility is transferred from one person to another (a case assigned, a review escalated, an approval delegated), the transfer is recorded with both parties, the timestamp, and any conditions. Case management platforms and workflow tools implement this. The trail shows how responsibility moved through an organization, not just who holds it at a given moment.

## Proposed Patterns

### Override Justification Capture [Proposed]
When a human overrides an AI recommendation: accepting a finding the AI rejected, rejecting a finding the AI accepted, or modifying an AI-generated output: the system prompts the human to record why. The justification is captured at the moment of override and attached to the artifact as a permanent record. Currently, overrides are common in AI-assisted tools but rarely documented. In regulated contexts, an undocumented override is a gap: it shows the human deviated from the AI's recommendation without explanation.

### Responsibility Handoff Package [Proposed]
When responsibility for a case, investigation, or review transfers from one human to another (shift change, escalation, peer review), the system generates a structured handoff package: current state, decisions made, AI recommendations accepted and rejected, open questions, and explicit responsibility transfer. Designed so the receiving party has enough context to make decisions without reconstructing the entire history.

## Connections

- **Auditability**: responsibility assignment creates the records that auditability preserves
- **Chain of Custody**: each custody entry assigns responsibility to a specific actor
- **Breadcrumbing**: the responsibility trail is a specific type of breadcrumb
- **Transparency**: users must understand what they are responsible for; transparency provides this context

## Sources

Kroll, J., Huey, J., Barocas, S., et al. (2017). Accountable Algorithms. University of Pennsylvania Law Review, 165(3). https://scholarship.law.upenn.edu/penn_law_review/vol165/iss3/3/

Raji, I.D., Smart, A., White, R.N., et al. (2020). Closing the AI Accountability Gap: Defining an End-to-End Framework for Internal Algorithmic Auditing. FAccT 2020. https://dl.acm.org/doi/10.1145/3351095.3372873

EU AI Act (2024). European Parliament and Council of the European Union. https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689

NIST AI Risk Management Framework 1.0 (January 2023). https://www.nist.gov/system/files/documents/2023/01/26/AI%20RMF%201.0.pdf
