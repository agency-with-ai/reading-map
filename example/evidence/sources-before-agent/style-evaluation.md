# Source record

DRAFT with agent passage checks. No user reading or user check is recorded. See [agent checks](../evidence/agent-checks.md).

- Title: Evaluating Style Transfer for Text
- Authors and year: Remi Mir, Bjarke Felbo, Nick Obradovich, Iyad Rahwan, 2019
- Original URL or DOI: https://aclanthology.org/N19-1049.pdf (NAACL-HLT 2019, pp. 495–504)
- Local paper path, if saved: not saved
- How this paper bears on my spec question: It measures style change, content preservation, and naturalness separately, which bears on how to test whether a draft resembles Feynman's writing.

## Relevant passage

Paraphrase, §2, pp. 495–496. Evaluate style change, content preservation, and naturalness separately. A text can succeed on one dimension while failing another.

Paraphrase, §5.2, pp. 499–500. In these experiments, relative judgments improved annotator agreement for naturalness. The paper does not report the same gain for style-transfer intensity.

Table 6, p. 499. Average Fleiss' kappa is 0.526 for relative naturalness judgments, versus 0.170 and 0.312 for absolute judgments binned at thresholds 3 and 2. These are agreement scores, not the fraction of readers fooled. The three raters each evaluated 244 texts per aspect per model (§5, p. 499).

Paraphrase, §5.4, pp. 501–502. For the three tested models, content preservation and naturalness tend to fall as style-transfer intensity rises.

## Conditions and limits

§5, p. 498. The experiments test three models on Yelp binary sentiment. That task changes a review's sentiment, not its author's voice. Applying these dimensions to Feynman-style explanations is my inference, not a finding of the paper.
