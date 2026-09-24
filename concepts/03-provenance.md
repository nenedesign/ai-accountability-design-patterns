# Concept 03: Provenance

## Definition

Provenance is the documented origin and handling history of a piece of data or artifact. A system with strong provenance can answer: where did this come from, who created it, and what has happened to it since.

## Why It Matters for AI-Assisted Products

AI systems generate outputs from data. When users or reviewers cannot trace data back to its origin, they cannot assess whether the AI's inputs were valid, current, or trustworthy. In forensic and investigative contexts, provenance is a legal requirement: evidence without documented origin is inadmissible.

Provenance is the design property that keeps AI outputs grounded in verifiable data.

## Established Patterns

### Data Source Label [Established]
Every artifact, output, or data item displays its origin at the point of use. The label includes where the data came from, when it was retrieved or created, and what version or snapshot it represents. Implemented in data catalogs (Apache Atlas, Alation), AI model interfaces (Hugging Face model pages), and document management systems.

### Model Card [Established]
Structured disclosure of where an AI model came from: training data, intended use cases, evaluation results, and known limitations. Introduced by Mitchell et al. (2019) at Google. Now standard at Hugging Face, Google, and Anthropic for published models. Design pattern: a model card is not documentation: it is a structured element that appears wherever the model is deployed, accessible from within the product.

### Artifact Metadata Panel [Established]
A persistent panel or tooltip attached to any artifact: file, image, dataset, document: showing its origin, creator, creation timestamp, modification history, and chain of handling. Standard in digital asset management systems, forensic tools, and enterprise content management platforms.

### Data Lineage Display [Established]
The full upstream chain of a data item is visible: what source it came from, what transformations it passed through, what other data it was combined with. Implemented in dbt, Apache Atlas, and OpenLineage. Design consideration: most lineage tools are engineering-facing; making lineage readable for end users requires a simplified, narrative representation of the technical graph.

## Proposed Patterns

No proposed patterns. Established coverage is sufficient.

## Connections

- **Chain of Custody**: provenance documents origin; chain of custody documents transfer and control after origin
- **Lineage**: provenance is about where data came from; lineage is about every transformation along the way
- **Integrity**: provenance is undermined if the artifact has been altered; integrity verifies it has not

## Sources

Moreau, L., Missier, P., et al. (2013). PROV-DM: The PROV Data Model. W3C Recommendation. https://www.w3.org/TR/prov-dm/

Mitchell, M., Wu, S., Zaldivar, A., et al. (2019). Model Cards for Model Reporting. FAccT 2019. https://dl.acm.org/doi/10.1145/3287560.3287596

NIST AI Risk Management Framework 1.0 (January 2023). https://www.nist.gov/system/files/documents/2023/01/26/AI%20RMF%201.0.pdf

Apache Atlas: Data Governance and Metadata Framework. https://atlas.apache.org/

OpenLineage: Open Standard for Data Lineage. https://openlineage.io/
