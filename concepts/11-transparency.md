# Concept 11: Transparency

## Definition

Transparency is openness about how an AI system works: what data it uses, what model it applies, what its limitations are, and what it cannot or should not do. Where explainability operates at the level of a single decision ("why did the AI say this?"), transparency operates at the level of the system ("what is this AI and how does it work?").

## Why It Matters for AI-Assisted Products

Users who do not understand what an AI system is cannot calibrate their trust in it. They will over-rely on it in situations where it is unreliable, and under-rely on it in situations where it is strong. They will not know when they are operating at the edge of its designed use case. Transparency gives users the information they need to apply appropriate judgment to AI outputs.

## Established Patterns

### System Card and Model Card [Established]
Structured disclosure of what the AI system is: its purpose, training data, known limitations, evaluation results, intended use cases, and out-of-scope uses. Model Cards were introduced by Mitchell et al. (2019) at Google. Now standard at Hugging Face, Google, and Anthropic for published models. Design pattern: these are not documentation pages — they are structured elements accessible from within the product, not buried in external help sites.

### Capability Disclosure [Established]
At the point of first use or at system boundaries, the product communicates what the AI can and cannot do. Implemented in enterprise AI deployments and clinical AI systems. Prevents users from relying on the AI for tasks outside its design.

### Data Usage Disclosure [Established]
The system communicates clearly what data it has access to, what data it was trained on, and what data it sends to third parties. Required by the EU AI Act for high-risk AI systems. Implemented in enterprise AI deployments and GDPR-compliant products.

### Limitation Notice [Established]
When the AI is producing output at the edge of its reliable range — low confidence, sparse training data for this domain, or a query type it was not designed for — the interface displays an explicit limitation notice. Distinct from a confidence score: a limitation notice explains why reliability may be lower, not just that it is.

## Proposed Patterns

### In-Session Transparency Panel [Proposed]
A persistent, always-accessible panel within the product that displays: which AI model is running, what version, what data it has access to in this session, and what it cannot do. Not buried in settings, help documentation, or onboarding flows — visible within the active work context. A user mid-investigation should be able to check what the AI is and what it is doing without leaving their workflow. Currently, AI capability and version information is typically in documentation or onboarding, not surfaced during active use.

## Connections

- **Explainability** — transparency is about the system; explainability is about a specific output
- **Observability** — transparency is what the system discloses about itself; observability is what can be measured about its live behavior
- **Responsibility Assignment** — users need transparency to understand what they are taking responsibility for when they act on AI outputs

## Sources

Mitchell, M., Wu, S., Zaldivar, A., et al. (2019). Model Cards for Model Reporting. FAccT 2019. https://dl.acm.org/doi/10.1145/3287560.3287596

European Commission High-Level Expert Group on AI. Ethics Guidelines for Trustworthy AI. April 2019. https://digital-strategy.ec.europa.eu/en/library/ethics-guidelines-trustworthy-ai

EU AI Act (2024). European Parliament and Council of the European Union. https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32024R1689

IEEE 7001-2021: Transparency of Autonomous Systems. https://standards.ieee.org/ieee/7001/6929/

NIST AI Risk Management Framework 1.0 (January 2023). https://www.nist.gov/system/files/documents/2023/01/26/AI%20RMF%201.0.pdf
