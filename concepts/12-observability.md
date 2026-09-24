# Concept 12: Observability

## Definition

Observability is the ability to understand the internal state and behavior of a system from its external outputs. An observable system can be monitored, interrogated, and diagnosed without requiring direct access to its internals. In software systems, observability rests on three signals: logs, metrics, and traces. In AI-assisted products, it extends to model behavior: is the AI performing as expected, and is its performance changing over time?

## Why It Matters for AI-Assisted Products

AI systems degrade. Models drift as the data they operate on shifts away from their training distribution. Error rates change. Latency increases. In regulated and forensic contexts, a system that was performing well six months ago may not be performing the same way today — and the people relying on its outputs may have no way of knowing. Observability is the design property that makes AI system health visible to the people who depend on it.

Most observability tooling is engineering-facing. This creates a gap: investigators, analysts, and compliance officers who rely on AI systems daily have no in-product signal when those systems degrade. The proposed patterns in this concept address that gap.

## Established Patterns

### System Health Dashboard [Established]
A real-time view of system performance: request volume, error rates, latency, uptime. Standard in production engineering (Grafana, Datadog, AWS CloudWatch). Primarily engineering-facing. Users of AI-assisted products rarely see this information.

### Model Performance Monitoring [Established]
Tracking of model-specific metrics over time: accuracy, precision, recall, and drift indicators. Implemented in ML monitoring platforms (Arize, WhyLabs, Evidently). Designed to detect when a model's behavior changes in production — which may happen without any code change, as the data the model operates on shifts.

## Proposed Patterns

### Investigator-Facing Health Indicator [Proposed]
A visible, plain-language signal within the investigator's workspace indicating whether the AI system is operating within normal reliability parameters. Not a technical dashboard — a simple, interpretable status that surfaces to the person doing the work: "AI classification performance is normal" or "AI classification confidence has been flagged for review in this evidence category." An investigator should not need to contact an operations team to know whether the tool they are using is behaving reliably.

### Degraded Mode Disclosure [Proposed]
An explicit UI state when the AI system is operating below normal reliability thresholds — due to model issues, data quality problems, or infrastructure degradation. The disclosure appears in the user's active workflow, not only in system logs or admin dashboards. It communicates: what is degraded, what this means for the user's work, and what they should do differently. Analogous to an aircraft maintenance indicator that surfaces to the pilot, not only to the maintenance crew.

## Connections

- **Transparency** — transparency is what the system discloses about itself by design; observability is what can be measured about its live behavior
- **Integrity** — observability monitoring can detect when model behavior suggests an integrity issue
- **Reproducibility** — model drift revealed through observability undermines reproducibility of analyses over time
- **Responsibility Assignment** — users cannot take informed responsibility for AI outputs if they have no visibility into whether the AI is performing normally

## Sources

OpenTelemetry — Cloud Native Computing Foundation. https://opentelemetry.io/

Sculley, D., Holt, G., Golovin, D., et al. (2015). Hidden Technical Debt in Machine Learning Systems. NeurIPS 2015. https://dl.acm.org/doi/10.5555/2969442.2969519

Kleppmann, M. (2017). Designing Data-Intensive Applications. O'Reilly.

Arize AI — ML Observability Platform. https://arize.com/

WhyLabs — AI Observability. https://whylabs.ai/
