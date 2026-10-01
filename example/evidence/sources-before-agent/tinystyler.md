# Source record

DRAFT with agent passage checks. No user reading or user check is recorded. See [agent checks](../evidence/agent-checks.md).

- Title: TinyStyler: Efficient Few-Shot Text Style Transfer with Authorship Embeddings
- Authors and year: Zachary Horvitz, Ajay Patel, Kanishk Singh, Chris Callison-Burch, Kathleen McKeown, Zhou Yu, 2024
- Original URL or DOI: https://aclanthology.org/2024.findings-emnlp.781.pdf (Findings of EMNLP 2024, pp. 13376–13390)
- Local paper path, if saved: not saved
- How this paper bears on my spec question: It rewrites text toward a target author's style from a few examples and reports how it measured success, which bears on both open decisions in my spec.

## Relevant passage

Paraphrase, §3, pp. 13378–13379. TinyStyler conditions text reconstruction on authorship embeddings, then filters synthetic transfer examples and trains on them.

Paraphrase, §4.1, p. 13380, and Table 2, p. 13381. Automatic evaluation reports Away, Towards, Sim, and Joint. Away and Towards use held-out UAR authorship embeddings, while reranking uses STYLE embeddings. Sim uses Mutual Implication Score (MIS). The authors avoid directly reranking on the automatic authorship evaluation representation; this does not make every evaluation signal independent of selection.

Paraphrase, §4.2, pp. 13381–13382. The human evaluation tests formality transfer, not imitation of a particular author.

Paraphrase, §3.1–3.3, pp. 13379–13380. The approach trains a reconstruction model and fine-tunes on selected synthetic transfers. It is not simply a prompt containing author examples. These training steps are outside the example spec's no-fine-tuning scope.

## Conditions and limits

§4.1, p. 13380. The automatic evaluation uses Reddit authors. §7, p. 13384, warns that authorship metrics may miss what authors themselves care about. These passages do not test whether readers can recognize an author, or whether technical explanations stay accurate and free of copied wording.
