# Concept 07: Reproducibility

## Definition

Reproducibility is the ability to recreate an AI output or analysis given the same inputs, model, and configuration. A reproducible result is one that another analyst, auditor, or court-appointed expert can independently verify.

## Why It Matters for AI-Assisted Products

AI outputs are not static. The same query can produce different results when the model changes, the data changes, or the configuration differs. In high-stakes, legal, and regulated contexts, an analysis that cannot be reproduced is an analysis that cannot be defended. Courts, regulators, and opposing counsel test AI-generated findings by attempting to reproduce them. A system that does not preserve the conditions of its original analysis gives users no way to respond to that challenge.

## Established Patterns

### Parameter Snapshot [Established]
The system records the exact model version, configuration, query, and data version used to produce an analysis at the time it was run. The snapshot is stored alongside the output, not reconstructed from logs. MLflow, Weights and Biases, and DVC implement this for ML experiments. Applied to AI-assisted investigation: any AI-generated finding is accompanied by the snapshot of conditions under which it was produced.

### Shareable Analysis State [Established]
The system can produce a link or export that recreates the exact analysis state: same query, same configuration, same data view. Observable, Jupyter notebooks, and Google Colab implement this for data analysis. Design consideration: shareable state must include the model version: a link that runs against the current model version is not reproducible if the model has been updated.

### Methodology Disclosure [Established]
The system surfaces a step-by-step account of what the AI did: what data was queried, what model processed it, what steps were applied, what output was produced. Implemented as a structured methodology section in AI-generated reports. In high-stakes contexts this is called adversarial defensibility: the methodology is written to withstand challenge by a party with an opposing interest.

## Proposed Patterns

### Independent Verification Indicator [Proposed]
A UI element attached to an AI-generated finding that shows whether the result has been independently reproduced and by whom. In high-stakes or legal contexts, a finding that has been independently verified by a second analyst or system carries greater weight than one that has not. Currently, verification status is handled outside the tool: in case management notes or expert reports. Surfacing it inside the product, at the artifact level, makes it visible at the point of decision.

### Model Change Alert [Proposed]
When the AI model underlying a tool is updated, the system notifies users who have active cases or saved analyses that were produced by a previous version. The alert identifies which analyses may be affected and offers the option to re-run them under the new model. Currently standard in ML infrastructure (MLflow model versioning) but rarely surfaced to end users in investigative or compliance tools.

## Connections

- **Explainability**: reproducibility requires that the methodology be disclosed; explainability makes the reasoning visible
- **Integrity**: reproducing an analysis requires that the data has not changed; integrity verifies this
- **Provenance**: reproducibility requires knowing exactly what data was used; provenance documents its origin
- **Observability**: model drift detected through observability directly undermines reproducibility over time

## Sources

Gundersen, O. & Kjensmo, S. (2018). State of the Art: Reproducibility in Artificial Intelligence. AAAI 2018. https://ojs.aaai.org/index.php/AAAI/article/view/11503

Hutson, M. (2018). Artificial intelligence faces reproducibility crisis. Science, 359(6377). https://www.science.org/doi/10.1126/science.359.6377.725

MLflow: Open Source Platform for the Machine Learning Lifecycle. https://mlflow.org/

DVC: Data Version Control. https://dvc.org/

ACPO Good Practice Guide for Digital Evidence, v5 (2012). Association of Chief Police Officers.
