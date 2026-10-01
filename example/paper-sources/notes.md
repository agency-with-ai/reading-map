# Example research notes

Agent-authored notes. See [example status](../README.md#status).

## Question from my spec

How should we test whether a generated technical explanation resembles Feynman's writing?

The relevant [spec passage](../project-spec.md#comparison-procedure) asks whether pairing a generated explanation with a reserved original measures resemblance to the author. Open decision 2 also asks how many passages and readers to use and how much improvement counts.

## Candidate selection

| Paper | Why it belongs in this example | Access and scope |
|---|---|---|
| [Evaluating Style Transfer for Text](style-evaluation.md) | Separates evaluation dimensions and compares human judgment tasks. | Public [PDF](https://aclanthology.org/N19-1049.pdf); Yelp sentiment transfer. |
| [TinyStyler](tinystyler.md) | Distinguishes automatic author-style evaluation from human formality evaluation. | Public [PDF](https://aclanthology.org/2024.findings-emnlp.781.pdf); Reddit authors and GYAFC formality. |

The original papers are available at the PDF links above.

## Reading notes

### [Evaluating Style Transfer for Text](style-evaluation.md)

| Lab 2 question | Agent observation and original location |
|---|---|
| Motivation | Inconsistent evaluation makes model comparisons hard (§1, p. 495; §3, p. 496). |
| Solution | Evaluate style transfer intensity, content preservation, and naturalness separately; compare human tasks and automated metrics (§2–5, pp. 495–501). |
| Old idea | Prior studies use different scales and combinations of human ratings, style classifiers, BLEU, and perplexity (§3, p. 496; Table 1). |
| Delta | Compare relative judgments and style masking with earlier tasks; study tradeoffs across model settings (§4–5). Table 6 supports relative naturalness judgments, but §5.2 reports no agreement gain for relative style intensity. |

Agent inference for the spec: fluent prose is insufficient evidence of resemblance to Feynman. The naturalness result motivates testing a comparison task, but does not establish an author-recognition test. See the [source record](style-evaluation.md) for the experiment's conditions.

### [TinyStyler](tinystyler.md)

| Lab 2 question | Agent observation and original location |
|---|---|
| Motivation | Author-style transfer may have only a few examples, while large-model prompts and controllable generation can be expensive (§1, pp. 13376–13377). |
| Solution | Train text reconstruction conditioned on authorship embeddings, then train on selected synthetic transfers (§3, pp. 13378–13380). |
| Old idea | Prompt large models with examples or use reconstruction and controlled generation (§2, pp. 13377–13378). |
| Delta | Use pretrained authorship representations in one transfer model and distill selected outputs (§3). Evaluate author transfer automatically (§4.1, Table 2), and formality with humans (§4.2, Table 4). |

Agent inference for the spec: the author-style benchmark is closer to our question than sentiment, but it supplies no human recognition result for Feynman. Its training recipe is outside our scope. Neither paper settles our reader count or improvement threshold.

## Claim checks

The [agent checks](../evidence/agent-checks.md) give passage locations and verdicts for a factual claim, a connection between papers, and an answer claim.

## Project decision

Use the [one-day evaluation decision](../project-spec.md#evaluation-decision-for-the-example) as an exploratory comparison. Keep facts, copied wording, and invented experiences as rejection checks. Record style resemblance and readability separately. Leave the reader-study design, reader and passage counts, and improvement threshold open.

See [the evidence comparison](../map/question.md) for supporting passages and limits.

## Saved exchanges

[Build summary](../evidence/map-build.md), [query summary](../evidence/map-query.md), and [answer draft](../map/answer-draft.md).

The [source snapshot](../evidence/sources-before-agent/) captures this directory before the reading map was built. Checks and execution results live outside it so the records remain comparable.
