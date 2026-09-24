# Concept 08: Lineage

## Definition

Lineage is the end-to-end documented history of a piece of data as it moves through a pipeline: its origin, every transformation applied to it, every system that processed it, and every output it contributed to. Provenance addresses where data came from; lineage addresses everything that happened to it afterward.

## Why It Matters for AI-Assisted Products

AI systems process data through pipelines — ingestion, cleaning, transformation, embedding, retrieval, inference. Each step can introduce errors, bias, or loss of information. Without lineage, it is impossible to determine whether a flawed AI output was caused by bad source data, a transformation error, or a model problem. In regulated environments, data lineage is a compliance requirement: financial regulators, healthcare auditors, and data protection authorities all require the ability to trace data through processing pipelines.

## Established Patterns

### Pipeline Visualization [Established]
A graphical representation of the data flow from source to output: every system, transformation, and output node. dbt, Apache Atlas, and OpenLineage implement this as engineering tooling. Design consideration: pipeline visualizations designed for data engineers are not accessible to business users or investigators. A simplified, narrative version of the pipeline is needed for end-user-facing lineage.

### Transformation Log [Established]
Every step applied to a data item is recorded in sequence: what operation, by what system or process, at what timestamp, with what parameters. MLflow and DVC implement this for ML experiments. Applied to AI-assisted investigation: any data item processed by AI carries a log of every operation applied to it.

### Upstream Dependency Graph [Established]
For any output, the system can show all upstream data items and transformations that contributed to it. Implemented in data catalog tools. Used in impact analysis: if a data source is found to be compromised or incorrect, the dependency graph shows which outputs are affected.

## Proposed Patterns

### Evidence Pipeline Disclosure [Proposed]
A simplified, investigator-facing representation of how digital evidence was processed before it reached the review interface. Current forensic tools display the results of processing — extracted artifacts, classified items, ranked findings — without surfacing the pipeline that produced them. An investigator reviewing an AI-classified image should be able to see: what model processed it, what version, what classification criteria were applied, and whether any pre-processing altered the artifact. This is a simplified lineage view designed for domain users, not engineers.

## Connections

- **Provenance** — provenance is the starting point of lineage; lineage is the full journey
- **Integrity** — lineage traces the path; integrity verifies no unauthorized alteration occurred at each step
- **Traceability** — lineage traces data through a pipeline; traceability links a decision back to its inputs
- **Reproducibility** — a full lineage record is a prerequisite for reproducibility

## Sources

Moreau, L., Missier, P., et al. (2013). PROV-DM: The PROV Data Model. W3C Recommendation. https://www.w3.org/TR/prov-dm/

OpenLineage — Open Standard for Data Lineage. https://openlineage.io/

Apache Atlas — Data Governance and Metadata Framework. https://atlas.apache.org/

dbt — Data Build Tool. Lineage and documentation. https://www.getdbt.com/

Schelter, S., et al. (2018). Automating Large-Scale Data Quality Verification. VLDB 2018. https://dl.acm.org/doi/10.14778/3229863.3229867
