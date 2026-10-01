# Evaluating Style Transfer for Text

Mir et al. (2019) compare evaluation methods for three text style-transfer models on Yelp binary sentiment. They distinguish style transfer intensity, content preservation, and naturalness. See the [source record](../paper-sources/style-evaluation.md), §2, pp. 495–496, and §5, p. 498.

Relative naturalness judgments have higher average inter-rater agreement in Table 6, p. 499: Fleiss' kappa is 0.526, versus 0.170 and 0.312 for thresholded absolute judgments. Section 5.2, pp. 499–500, reports no corresponding improvement for relative style intensity. These numbers measure agreement, not author recognition or the share of readers fooled. See the [recorded passage](../paper-sources/style-evaluation.md#relevant-passage).

The three models exhibit tradeoffs between style intensity, content preservation, and naturalness (§5.4, pp. 501–502, in the [source record](../paper-sources/style-evaluation.md)). This is evidence from sentiment transfer, not a universal result about imitation of authors.

**Inference for this project.** Separate factual and copying checks from resemblance and readability judgments. A relative naturalness result does not establish the validity of a Feynman identification task. [TinyStyler](tinystyler.md) adds an authorship setting, but its human evaluation addresses another task. See the [comparison](question.md).

**Status.** Unchecked by the user; agent factual check F1 and connection check C1 appear in the [ledger](../evidence/agent-checks.md).
