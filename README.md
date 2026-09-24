# AI Accountability Design Patterns

Design patterns for AI-assisted products that must answer for their decisions, data, and outputs.

---

**Neville Ko**: AI Product Manager, Designer & Builder
[Portfolio](https://fromus.ca) · [LinkedIn](https://www.linkedin.com/in/nevilleko/)

---

## What Is AI Accountability

AI accountability is the capacity of an AI-assisted system to answer for its actions, decisions, and outputs to the humans and institutions it serves. It is not a single feature or control. It is a design property that emerges from 12 interlocking concepts.

Each concept addresses a specific question the system must be able to answer. Together, they form the design layer of accountability: the patterns, controls, and disclosures that make a system answerable.

AI augments workflow for human judgment. It does not replace it.

---

## The 12 Concepts

| # | Concept | Core question | Patterns |
|---|---------|--------------|---------|
| 01 | [Traceability](./concepts/01-traceability.md) | How did we get here? | Established |
| 02 | [Auditability](./concepts/02-auditability.md) | What happened, and can we prove it? | Established |
| 03 | [Provenance](./concepts/03-provenance.md) | Where did this come from? | Established |
| 04 | [Breadcrumbing](./concepts/04-breadcrumbing.md) | What path did we take? | Established + Proposed |
| 05 | [Chain of Custody](./concepts/05-chain-of-custody.md) | Who had it, and when did they pass it on? | Established + Proposed |
| 06 | [Explainability](./concepts/06-explainability.md) | Why did the system decide this? | Established |
| 07 | [Reproducibility](./concepts/07-reproducibility.md) | Can we recreate this result independently? | Established + Proposed |
| 08 | [Lineage](./concepts/08-lineage.md) | What transformations did this data go through? | Established + Proposed |
| 09 | [Responsibility Assignment](./concepts/09-responsibility-assignment.md) | Who is responsible for this decision? | Established + Proposed |
| 10 | [Integrity](./concepts/10-integrity.md) | Has this data been altered? | Established + Proposed |
| 11 | [Transparency](./concepts/11-transparency.md) | Is the system itself understandable? | Established + Proposed |
| 12 | [Observability](./concepts/12-observability.md) | What is the system doing right now? | Established + Proposed |

---

## Repo Structure

```
/concepts      12 concept files: definition, patterns, industry examples, sources
/audit         Scorable checklist for evaluating an AI-assisted product
references.md  Full citation list
```

---

## How to Use

**Concepts** define each accountability dimension and the design patterns that implement it. Read these to understand the design requirements for a specific accountability property.

**Audit** is a scorable checklist for evaluating an existing AI-assisted product across all 12 concepts. Use it in design reviews, heuristic evaluations, or pre-launch assessments.

---

## On Established and Proposed Patterns

Patterns marked **[Established]** are named, documented practices with real industry examples. They are grounded in published standards, deployed products, or peer-reviewed research.

Patterns marked **[Proposed]** are original design recommendations grounded in adjacent research and first-principles reasoning. They address gaps in the existing literature: accountability problems that practitioners face but the field has not yet named or standardized. Proposed patterns are offered as starting points for discussion and testing, not finished prescriptions.

Not all 12 concepts have equally developed design pattern libraries. Concepts where the field is thin are identified. In those cases, proposed patterns extend the existing literature rather than repeat it.

---

## Sources

See [references.md](./references.md) for the full citation list.

---

## Related

- [trauma-informed-design-patterns](https://github.com/nenedesign/trauma-informed-design-patterns): interaction design patterns for forensic, investigative, and high-stakes digital products, grounded in SAMHSA's six principles. Evidence Provenance and Explainable AI Output patterns there complement Chain of Custody and Explainability concepts here.
- [conversational-ai-patterns](https://github.com/nenedesign/conversational-ai-patterns): conversational AI interaction design patterns, including HITL handoff design, source traceability, auditable AI output, and scale triage for regulated evidence review.
- [conversational-ops-runtime](https://github.com/nenedesign/conversational-ops-runtime): production API that implements chain of custody, stale approval detection, and append-only audit trails for governed AI agent execution.
