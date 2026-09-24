# Concept 04: Breadcrumbing

## Definition

Breadcrumbing is the practice of leaving visible markers as a user or system moves through a process, so that the path can be reconstructed, reviewed, or retraced. In navigation design this is literal: a trail showing where you are in a structure. In AI-assisted workflows it extends further: a record of what the AI surfaced, what the human accepted or rejected, and why.

## Why It Matters for AI-Assisted Products

Complex AI-assisted workflows (investigation, diagnosis, underwriting, compliance review) involve many steps, many AI suggestions, and many human decisions. Without breadcrumbing, it is impossible to reconstruct the process after the fact, understand why a conclusion was reached, or identify where the workflow went wrong. The path matters as much as the destination.

## Established Patterns

### Hierarchical Breadcrumb [Established]
Shows where the user is within a structure: Home / Cases / Case 4412 / Evidence / Item 23. Standard UX pattern across file systems, content management platforms, and enterprise applications. Tells the user where they are in relation to the whole.

### Step Indicator [Established]
Shows the user's position in a sequential workflow: Step 3 of 7. Standard in wizard patterns, form flows, onboarding sequences, and compliance checklist tools. Tells the user how far they have come and how far remains.

### Annotation Trail [Established]
As the user moves through an investigation or review, their notes, flags, and highlights are attached to the artifacts they acted on, forming a visible record of their path through the material. Implemented in forensic tools, legal review platforms, and clinical documentation systems. The annotation trail is both a working tool and an audit artifact.

### History-Based Navigation Trail [Established]
The user's recent path through the product is accessible and navigable. Recently viewed items and session history of which artifacts were reviewed in what order are standard features in complex investigation tools.

## Proposed Patterns

### AI Suggestion Trail [Proposed]
In AI-assisted investigation or review workflows, a persistent record of what the AI surfaced, what the human accepted, modified, or rejected, and at what point in the workflow. The trail distinguishes between AI-generated conclusions and human-validated ones. Most current systems surface AI suggestions without recording the human's response to each one. In regulated and forensic contexts, this trail is part of the evidentiary record.

### Investigative Path Reconstruction [Proposed]
A timeline view of an investigator's session: which artifacts were reviewed, in what order, what actions were taken, what AI tools were applied, and what conclusions were reached at each step. Reconstructable after the fact, not only during the session. Designed for peer review, quality assurance, and legal challenge scenarios.

## Connections

- **Traceability**: traceability follows data and decisions; breadcrumbing follows the human path through the workflow
- **Auditability**: annotation trails and suggestion trails are audit artifacts
- **Responsibility Assignment**: the breadcrumb trail identifies who did what at each step

## Sources

Nielsen, J. Breadcrumb Navigation Increasingly Useful. Nielsen Norman Group. https://www.nngroup.com/articles/breadcrumb-navigation-useful/

ACPO Good Practice Guide for Digital Evidence, v5 (2012). Association of Chief Police Officers. https://www.digital-detective.net/digital-forensics-documents/ACPO_Good_Practice_Guide_for_Digital_Evidence_v5.pdf

NIST SP 800-86: Guide to Integrating Forensic Techniques into Incident Response. https://csrc.nist.gov/publications/detail/sp/800-86/final

Krug, S. (2014). Don't Make Me Think, Revisited. New Riders.
