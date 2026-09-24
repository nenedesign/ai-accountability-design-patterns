# Concept 01: Traceability

## Definition

Traceability is the ability to link an output, decision, or action back to the inputs, data, and actors that produced it. A traceable system can answer: who did this, what did they act on, and how did the data get here.

## Why It Matters for AI-Assisted Products

AI systems compress complex reasoning into outputs that appear authoritative. Without traceability, users and reviewers cannot verify whether those outputs are grounded in relevant data, applied to the right inputs, or reached by a valid process. In regulated and high-stakes contexts, an output that cannot be traced is an output that cannot be trusted or defended.

Traceability is the design property that keeps AI outputs accountable to their inputs.

## Established Patterns

### Inline Attribution [Established]
Every output, change, or action displays who performed it, when, and what it acted on: at the point of display, not in a separate log. GitHub's blame view, Figma's version history, Google Docs' edit attribution, and Notion's activity trail all implement this. The record is visible without navigating away from the artifact.

### Source Citation [Established]
Every AI-generated claim or recommendation is linked to the specific source it drew from. Perplexity and Bing Copilot display numbered source citations inline with answers. Retrieval-augmented generation (RAG) systems implement this by surfacing the retrieved document alongside the generated response. The user can verify the claim against the source without leaving the interface.

### Decision Trail [Established]
The reasoning path from input to conclusion is visible to the user. Legal AI tools link AI-generated analysis to the specific case law that supports it. Clinical decision support systems surface the evidence rules triggered by a patient's data. The trail is part of the output, not an optional deep-dive.

### Diff View [Established]
Changes to a document, record, or artifact are displayed explicitly: what was added, what was removed, what remained. GitHub pull request diffs, Figma version comparison, and document revision history all implement this. The user does not infer what changed; the system shows it.

## Proposed Patterns

No proposed patterns. Established coverage is sufficient.

## Connections

- **Auditability**: traceability explains how an output was produced; auditability records that it happened
- **Provenance**: traceability follows a decision path; provenance follows a data origin
- **Breadcrumbing**: breadcrumbing is the navigation equivalent of traceability
- **Explainability**: explainability is a specific form of traceability applied to AI reasoning

## Sources

Amershi, S., Weld, D., Vorvoreanu, M., et al. (2019). Guidelines for Human-AI Interaction. CHI 2019. https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/

NIST AI Risk Management Framework 1.0 (January 2023). https://www.nist.gov/system/files/documents/2023/01/26/AI%20RMF%201.0.pdf

IEEE 7001-2021: Transparency of Autonomous Systems. https://standards.ieee.org/ieee/7001/6929/

European Commission High-Level Expert Group on AI. Ethics Guidelines for Trustworthy AI. April 2019. https://digital-strategy.ec.europa.eu/en/library/ethics-guidelines-trustworthy-ai
