# Source record

DRAFT from a Codex rehearsal. Check each passage and page number against the PDF, then delete this line.

- Title: TinyStyler: Efficient Few-Shot Text Style Transfer with Authorship Embeddings
- Authors and year: Zachary Horvitz, Ajay Patel, Kanishk Singh, Chris Callison-Burch, Kathleen McKeown, Zhou Yu, 2024
- Original URL or DOI: https://aclanthology.org/2024.findings-emnlp.781.pdf (Findings of EMNLP 2024, pp. 13376–13390)
- Local paper path, if saved: not saved
- How this paper bears on my spec question: It rewrites text toward a target author's style from a few examples and reports how it measured success, which bears on both open decisions in my spec.

## Relevant passage

Paraphrase, §3, pp. 13378–13379. TinyStyler conditions text reconstruction on authorship embeddings, then filters synthetic transfer examples and trains on them.

Paraphrase, §4.1, p. 13380. Automatic evaluation reports four scores, Away, Towards, Sim, and Joint. It scores with UAR embeddings, which differ from the STYLE embeddings used to rerank outputs, so the reported scores do not reuse the reranking signal.

Paraphrase, §4.2, pp. 13381–13382. The human evaluation tests formality transfer, not imitation of a particular author.

## Conditions and limits

§4.1, p. 13380. The automatic evaluation uses Reddit authors. §7, p. 13384, warns that authorship metrics may miss what authors themselves care about. These passages do not test whether readers can recognize an author, or whether technical explanations stay accurate and free of copied wording.
