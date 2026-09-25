# Concept 05: Chain of Custody

## Definition

Chain of custody is the documented record of who has had control of a piece of evidence or data, when they had it, what they did with it, and when they transferred it. Each transfer is documented, signed, and timestamped. The chain must be unbroken for the evidence to be admissible and defensible.

## Why It Matters for AI-Assisted Products

When AI processes digital evidence (images, files, communications, financial records), it handles material that may be presented in legal, regulatory, or compliance proceedings. If the system does not document every step of AI handling in the chain, the integrity of the evidence is in question. An AI that processed evidence without a chain of custody record is a gap that opposing counsel or a regulator will find.

## Established Patterns

### Custody Log [Established]
A sequential record of every person and system that has had control of an artifact: who received it, when, from whom, what they did with it, and when they passed it on. Implemented in digital investigation tools as a required workflow step. Each log entry includes actor identity, timestamp, action performed, and transfer destination.

### Transfer Documentation [Established]
Each transfer of evidence or data between parties (analyst to analyst, tool to tool, system to system) is documented with a signed record at the moment of transfer. The ACPO Good Practice Guide for Digital Evidence specifies that every person who accesses digital evidence must document their involvement. Transfer documentation is captured at the point of transfer, not reconstructed afterward.

### Read-Only Evidence Mode [Established]
Evidence is displayed in a protected mode that prevents modification. Accessing evidence for review does not alter it. Implemented in investigative acquisition tools and evidence review platforms. The hash of the original artifact is preserved and can be verified at any point in the review process.

### Cryptographic Seal at Handoff [Established]
At each point of transfer, a cryptographic hash or digital signature is applied to the evidence package. This allows any party in the chain to verify that what they received is identical to what was transferred, and that no modification occurred in transit.

## Proposed Patterns

### AI Handling Disclosure [Proposed]
When AI processes an artifact: classifying it, extracting information, ranking it, or flagging it: the handling record documents: which AI model version performed the processing, what operation was performed, what the input was, what the output was, and the timestamp. This disclosure is part of the chain of custody record, not a separate log. The investigator reviewing an AI-flagged artifact can see exactly what the AI did to it and when. Currently absent in most AI-assisted investigative tools: AI processing is logged at a system level but not surfaced in the artifact's custody record.

## Connections

- **Provenance**: provenance documents origin; chain of custody documents every transfer after origin
- **Integrity**: chain of custody records who had the evidence; integrity verifies it was not altered during their possession
- **Auditability**: the custody log is an audit artifact; auditability is the broader property it contributes to
- **Responsibility Assignment**: each custody entry assigns responsibility to a specific actor

## Sources

ACPO Good Practice Guide for Digital Evidence, v5 (2012). Association of Chief Police Officers. https://www.digital-detective.net/digital-forensics-documents/ACPO_Good_Practice_Guide_for_Digital_Evidence_v5.pdf

NIST SP 800-86: Guide to Integrating Forensic Techniques into Incident Response. https://csrc.nist.gov/publications/detail/sp/800-86/final

Scientific Working Group on Digital Evidence (SWGDE). Best Practices for Digital Evidence Collection. https://www.swgde.org/

Carrier, B. & Spafford, E. (2003). Getting Physical with the Digital Investigation Process. International Journal of Digital Evidence, 2(2).
