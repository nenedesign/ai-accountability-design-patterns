# Concept 10: Integrity

## Definition

Integrity is the assurance that data, evidence, or a record has not been altered, corrupted, or tampered with since it was created or acquired. A system with integrity can demonstrate that what it holds today is identical to what it received at acquisition.

## Why It Matters for AI-Assisted Products

Digital evidence processed by AI must retain integrity throughout the investigation. If the system cannot prove that evidence has not been altered (by the AI, by a storage failure, or by a user action), the evidence is compromised. In legal proceedings, a failure to demonstrate integrity is grounds for exclusion. In regulated environments, a tampered audit log invalidates the audit.

## Established Patterns

### Hash Verification [Established]
At acquisition, a cryptographic hash (SHA-256, MD5) is computed for each artifact. At any subsequent point, the hash can be recomputed and compared to the original. If they match, the artifact is unchanged. Standard practice in high-stakes evidence handling (NIST, SWGDE, ACPO) and implemented in all major investigative acquisition tools.

### Tamper Indicator [Established]
A visible alert in the interface when an artifact's hash does not match its original value, or when a record has been modified outside expected parameters. The indicator surfaces the integrity failure at the point of use, not only in a background log. Implemented in high-stakes evidence management systems and tamper-evident logging platforms.

### WORM Storage [Established]
Write-Once-Read-Many storage prevents modification of records after creation at the infrastructure level. Required by FINRA Rule 17a-4 for financial records. Used in regulated industries for audit logs, evidence archives, and compliance records. In AI-assisted systems: audit logs and evidence stores should be backed by WORM storage or an equivalent append-only mechanism.

### Digital Signature at Creation [Established]
At the moment an artifact is acquired or a record is created, it is cryptographically signed. The signature verifies both the content (unchanged) and the creator (authenticated). Implemented in investigative acquisition tools and document signing platforms.

## Proposed Patterns

### AI Processing Integrity Disclosure [Proposed]
When AI processes an artifact, the system records and surfaces whether the processing preserved or modified the original. Classification and metadata extraction are non-destructive: the original is unchanged. Some AI operations (enhancement, compression, format conversion) may alter the artifact. The disclosure makes this distinction explicit: "AI classification applied. Original artifact preserved. Hash unchanged." Most AI-assisted investigative tools do not currently surface this distinction; AI processing is treated as a black box in the custody record.

## Connections

- **Auditability**: auditability requires records that have not been tampered with; integrity is the property that guarantees this
- **Chain of Custody**: integrity verifies that what was transferred is what was received at each handoff
- **Provenance**: provenance is undermined if the artifact has been altered since acquisition
- **Reproducibility**: reproducing an analysis requires that the underlying data has not changed; integrity verifies this

## Sources

NIST SP 800-86: Guide to Integrating Forensic Techniques into Incident Response. https://csrc.nist.gov/publications/detail/sp/800-86/final

ACPO Good Practice Guide for Digital Evidence, v5 (2012). Association of Chief Police Officers.

Scientific Working Group on Digital Evidence (SWGDE). Best Practices for Digital Evidence Collection. https://www.swgde.org/

FINRA Rule 17a-4: Records to Be Preserved by Certain Exchange Members, Brokers, and Dealers. https://www.finra.org/rules-guidance/rulebooks/finra-rules/17a-4

ISO/IEC 27001:2022: Information Security Management Systems. https://www.iso.org/standard/82875.html
