# TinyStyler

Horvitz et al. (2024) train reconstruction conditioned on authorship embeddings, then fine-tune on selected synthetic transfers. The training recipe is outside this project's no-fine-tuning scope. See the [source record](../paper-sources/tinystyler.md), §3, pp. 13378–13380.

The automatic authorship evaluation uses Reddit authors. Away and Towards use held-out UAR embeddings, whereas reranking uses STYLE embeddings. Sim uses Mutual Implication Score. This distinction avoids directly reranking on the authorship evaluation representation, but does not establish independence of every metric from selection. See §4.1, p. 13380, and Table 2, p. 13381, in the [source record](../paper-sources/tinystyler.md#relevant-passage).

The human evaluation concerns formality transfer, not recognition of a named author (§4.2, pp. 13381–13382). The authors also warn that authorship metrics may not capture authors' preferences (§7, p. 13384). See the [record and limits](../paper-sources/tinystyler.md).

**Inference for this project.** Automatic authorship scores are insufficient evidence that readers will mistake explanations for Feynman's writing. Together with [Mir et al.](style-evaluation.md), this supports separating dimensions while leaving the reader task unresolved. See the [comparison](question.md).

**Status.** Unchecked by the user; agent checks F2, C1, and A1 appear in the [ledger](../evidence/agent-checks.md).
