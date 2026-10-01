# Agent claim checks

All verdicts below are the agent's. No user check is recorded. Page numbers refer to printed proceedings pages, with PDF page numbers supplied for navigation. Passages were read from the original PDFs using text extraction.

| ID and kind | Claim checked | Original passage | Agent verdict and limit |
|---|---|---|---|
| F1, factual claim in the reading map | Relative naturalness judgments have higher agreement, but relative style-intensity judgments do not show the same gain. | [Mir et al. PDF](https://aclanthology.org/N19-1049.pdf#page=5), §5.2 and Table 6, pp. 499–500, PDF pp. 5–6. Table 6 gives average kappa 0.526 for relative naturalness, versus 0.170 and 0.312 for thresholded absolute ratings. | Supported in this Yelp sentiment experiment. The measure is inter-rater agreement, not a reader deception rate. It does not establish agreement on resemblance to an author. |
| F2, source precision | TinyStyler uses a held-out representation for automatic authorship evaluation. | [TinyStyler PDF](https://aclanthology.org/2024.findings-emnlp.781.pdf#page=5), §4.1, p. 13380, PDF p. 5; Table 2, p. 13381, PDF p. 6; §3.2, p. 13379, PDF p. 4. Away and Towards use UAR for evaluation and STYLE for selection. Sim uses MIS, which also appears in filtering. | Supported only for the authorship representation distinction. A claim that every evaluation signal is independent of selection is too broad. The source record and the reading map state the narrower claim. |
| C1, connection between papers | Both papers motivate keeping evaluation dimensions separate, but neither establishes a human test for Feynman recognition. | Mir et al. §2, pp. 495–496, PDF pp. 1–2, and §5.2, pp. 499–500; TinyStyler §4.1–4.2, pp. 13380–13382, PDF pp. 5–7. The first studies sentiment and relative naturalness; the second separates automatic author metrics from human formality judgments. | Supported as a bounded synthesis. Using separate judgments in this project is an agent inference. The papers are not reported as disagreeing or as testing the same outcome. |
| A1, answer claim | TinyStyler's human evaluation does not test recognition of a named author. | [TinyStyler PDF](https://aclanthology.org/2024.findings-emnlp.781.pdf#page=6), §4.2, pp. 13381–13382, PDF pp. 6–7, especially Human Evaluation and Table 4. Annotators judge meaning preservation, fluency, and formality. | Supported. The answer draft preserves the task limitation. This does not establish anything about how our future readers would vote. |

The factual check addresses [the evaluation page](../map/style-evaluation.md). The connection check addresses [the comparison](../map/question.md). The answer check addresses [the answer draft](../map/answer-draft.md).

## Evidence still missing

No user reading, user claim check, or partner judgment is supplied. There is no fresh-session answer, actual conversation export, reader pilot, measured author-recognition accuracy, or demonstrated improvement over the plain prompt. The source settings do not settle the reader count, number of passages for a main study, or improvement threshold.

No reading map claim is promoted to user-checked status. The project decision remains an exploratory example.
