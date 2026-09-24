# Concept 02: Auditability

## Definition

Auditability is the property of a system that maintains a complete, accurate, and tamper-evident record of what happened, when, and by whom. An auditable system can produce evidence for review, investigation, or compliance verification after the fact.

## Why It Matters for AI-Assisted Products

When AI takes actions or influences decisions in regulated environments, the system must be able to demonstrate what occurred. Audit requirements are not satisfied by logs that can be edited, systems where actions go unrecorded, or records that do not capture enough context for a reviewer to reconstruct what happened.

Auditability is the infrastructure that makes accountability verifiable.

## Established Patterns

### Append-Only Event Log [Established]
Every action writes a new record. No record can be modified or deleted after creation. The log grows in one direction. SOC 2 Type II audit infrastructure, FINRA Rule 17a-4 WORM storage, and HIPAA audit logs all require this property. In design terms: edit and delete operations on the log must be architecturally impossible, not merely policy-prohibited.

### Activity Feed [Established]
A real-time, human-readable record of recent actions is visible within the product. Slack's channel history, Notion's page history, Jira's issue activity log, and GitHub's commit history all implement this. The feed is a primary navigation and orientation tool that creates an audit record as a side effect.

### Audit Report Export [Established]
The system produces a structured, compliance-ready export of activity for a defined period or scope. The export is formatted for a reviewer who was not present: it includes actor, action, timestamp, object, and outcome. Designed for external auditors, legal counsel, or compliance officers.

### Non-Repudiation Record [Established]
Key actions — approvals, sign-offs, authorizations — are cryptographically signed so the actor cannot later deny having performed them. DocuSign implements this for document signatures. SWIFT messages use this for financial transactions. In AI-assisted systems: any human approval of an AI recommendation should carry a non-repudiation record.

## Proposed Patterns

No proposed patterns. Established coverage is sufficient.

## Connections

- **Traceability** — auditability records that an action occurred; traceability explains how the output was produced
- **Integrity** — auditability requires records that have not been tampered with; integrity is the property that guarantees this
- **Responsibility Assignment** — audit records must identify the responsible human, not just the system

## Sources

NIST SP 800-92: Guide to Computer Security Log Management. https://csrc.nist.gov/publications/detail/sp/800-92/final

SOC 2 Trust Service Criteria. American Institute of CPAs. https://www.aicpa.org/resources/download/2017-trust-services-criteria

FINRA Rule 17a-4: Records to Be Preserved by Certain Exchange Members, Brokers, and Dealers. https://www.finra.org/rules-guidance/rulebooks/finra-rules/17a-4

NIST AI Risk Management Framework 1.0 (January 2023). https://www.nist.gov/system/files/documents/2023/01/26/AI%20RMF%201.0.pdf
