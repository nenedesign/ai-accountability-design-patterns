# Concept 06: Explainability

## Definition

Explainability is the capacity of an AI system to communicate why it produced a given output: what factors it weighted, what evidence it drew from, and how confident it is. A system is explainable when its reasoning is accessible to the humans who act on its outputs.

## Why It Matters for AI-Assisted Products

AI confidence is a product of many factors that are not visible in the output. A high-confidence recommendation may rest on weak evidence, outdated data, or inputs that do not apply to the current case. Without explainability, users cannot calibrate their trust in AI outputs or identify when the AI is operating outside its reliable range. In regulated and forensic contexts, an unexplained AI output cannot be defended.

Explainability is the design property that keeps AI judgment visible to human judgment.

## Established Patterns

### Confidence Display [Established]
The AI outputs a confidence level alongside its recommendation, expressed in plain language or as a calibrated score. Clinical decision support systems and financial risk tools implement this. Design requirement: confidence must be calibrated. A 90% confidence score must be correct approximately 90% of the time and expressed in terms the user can interpret, not raw probability.

### Reasoning Summary [Established]
The AI provides a natural-language explanation of why it reached its conclusion: what it considered, what it weighted heavily, and what it ruled out. Chain-of-thought prompting makes this accessible at the model level. Legal AI tools surface reasoning alongside conclusions. Clinical tools present the evidence rules that triggered a recommendation.

### Feature Importance Visualization [Established]
For structured data inputs, the AI displays which input features most influenced the output. LIME (Ribeiro et al., 2016) and SHAP (Lundberg & Lee, 2017) are the standard techniques. Implemented in credit risk platforms, healthcare risk scoring, and fraud detection. Design consideration: feature importance visualizations designed for data scientists are often inaccessible to domain users and require translation into the user's vocabulary.

### Source Attribution Inline [Established]
Every AI-generated claim is linked to the specific source document or data item it drew from, displayed inline with the output. RAG-based systems surface the retrieved chunk alongside the generated response. Users can verify claims without navigating away.

## Proposed Patterns

No proposed patterns. Established coverage is sufficient.

## Connections

- **Transparency**: explainability is per-decision (why did the AI produce this output); transparency is per-system (how does the AI work in general)
- **Traceability**: explainability follows the AI's reasoning; traceability follows the data and actor path
- **Reproducibility**: an explainable output is a step toward a reproducible one; the methodology must be disclosed

## Sources

Ribeiro, M., Singh, S., & Guestrin, C. (2016). "Why Should I Trust You?": Explaining the Predictions of Any Classifier. KDD 2016. https://dl.acm.org/doi/10.1145/2939672.2939778

Lundberg, S. & Lee, S. (2017). A Unified Approach to Interpreting Model Predictions. NeurIPS 2017. https://dl.acm.org/doi/10.5555/3295222.3295230

Doshi-Velez, F. & Kim, B. (2017). Towards a Rigorous Science of Interpretable Machine Learning. arXiv:1702.08608. https://arxiv.org/abs/1702.08608

Wachter, S., Mittelstadt, B., & Russell, C. (2017). Counterfactual Explanations Without Opening the Black Box. Harvard Journal of Law and Technology, 31(2). https://jolt.law.harvard.edu/assets/articlePDFs/v31/Counterfactual-Explanations-without-Opening-the-Black-Box-Sandra-Wachter-et-al.pdf

Amershi, S., Weld, D., Vorvoreanu, M., et al. (2019). Guidelines for Human-AI Interaction. CHI 2019. https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/

NIST AI Risk Management Framework 1.0 (January 2023). https://www.nist.gov/system/files/documents/2023/01/26/AI%20RMF%201.0.pdf
