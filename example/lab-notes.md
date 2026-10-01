# Lab 3 example notes

This rehearsal follows `~/code/agency-ai/labs/w03/lab.md` and its student note template. The reading questions come from `~/code/agency-ai/labs/w02/lab.md`. The local Lab 3 source governs this run; the hosted page was unavailable to the browser tool. These notes are agent-authored, with no student, partner, or staff participation claimed.

## Step 1. Project spec

The [spec](project-spec.md) describes a local tool for short technical explanations in Feynman's style. Its intended users include students and teachers. The one-day version compares one method with a plain request on three reserved passages, with the project owner judging the drafts.

The challenges are factual errors, copied wording, invented experiences, and recognition of familiar originals. Reading informs the writing method and evaluation. Building involves a local generation script and records of prompts, drafts, checks, and judgments. The model and writing method remain undecided.

## Step 2. Worked case

**Request.** Explain overfitting to a college student in at most 200 words.

**Expected content.** Explain why strong training performance does not guarantee performance on new examples, and how a held-out test set helps assess generalization. The factual brief is supplied by the existing spec. This is a reasoning exercise, not an output from an implemented tool.

| Candidate fragment invented for this case | Agent judgment | Spec basis |
|---|---|---|
| “A model can fit the examples it practiced on and still fail on new examples.” | Meets this part of the factual brief; author resemblance is untested. | Inputs and output; acceptance checks. |
| “Perfect training accuracy proves that the model will work on new examples.” | Reject for contradicting the factual brief. | Inputs and output. |
| “When I first learned this, I was confused too.” | Unresolved. It could be an invented personal experience, which the spec rejects, or part of how Feynman typically addresses the reader. | Acceptance checks; open question below. |
| “Imagine learning every answer on a practice exam without learning how to solve a new problem.” | An analogy, not a claim about a past experience; resemblance and copying still need review. | Acceptance checks. |

The spec rejects invented personal experiences but does not say whether a line like this counts as one. Its fact and copying checks would not catch an invented anecdote either. This example leaves both questions open and the spec unchanged. It has no check for invented anecdotes yet.

### Agent critique

1. The audience and overfitting example make factual success concrete, but “resembles Feynman” lacks a tested judgment rule. The literature question targets that gap.
2. An original-versus-generated vote can reflect recognition of a familiar original or differences in fluency. A vote alone does not identify the reason for the choice.
3. Three owner-judged cases can expose failures, but do not establish how other readers would judge author resemblance. Report the individual cases without a population claim.
4. As a tool for preparing an explanation, this could be useful if the owner checks its facts. The agent has no personal need for it and supplies no evidence of demand from actual users.

## Step 3. Partner exchange and Checkoff 1

Pending. No partner case, partner interpretation, or staff feedback is recorded. The worked case above is the agent's own case, not a substitute for a partner's independent interpretation.

## Step 4. Reading map and decision

The [research notes](paper-sources/notes.md) document both papers with Lab 2's four questions. The [wiki](wiki/index.md) connects their evidence to open decision 2. The [agent checks](evidence/agent-checks.md) compare a factual claim, a connection, and an answer claim with original passages.

TinyStyler supplies an author-style evaluation setting, while Mir et al. supplies evidence about human judgment tasks. Together they make the missing evidence concrete. Neither tests whether readers recognize Feynman's style in technical explanations.

The [spec decision](project-spec.md#evaluation-decision-for-the-example) keeps the one-day comparison exploratory. It separates the rejection checks, resemblance judgment, and readability judgment. The reader study remains open. The next check is a pilot that records recognition of originals and the reasons for reader judgments.

### Checkoff 2 preparation

| Question | Example answer |
|---|---|
| What choice did the reading map help make? | Use separate evaluation dimensions and leave a claim of reader-level author imitation open. |
| What evidence supports the choice? | Mir et al. §2 and §5.2 distinguish dimensions and limit the agreement result to naturalness. TinyStyler §4.1–4.2 distinguishes author metrics from human formality judgments. |
| How did the spec guide the reading? | The desired result is resemblance to a named author, so the decisive check is whether a study actually tests that outcome with people. |

Partner explanation, reconsideration of the partner's case, and staff Checkoff 2 are pending. The [run records](evidence/wiki-build.md) are summaries; actual conversation exports are pending too.

## Next coding question

How should a local script keep the model, factual brief, and word limit fixed across the plain prompt and chosen method, while saving every rejected draft? Selecting and running that implementation belongs to the project build, beyond this reading-map example.

The optional recurring search is not run.
