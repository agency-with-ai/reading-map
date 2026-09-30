# Reading Map

A starter for building and checking a literature wiki around a question from your project spec. Connect papers to a project decision, check the evidence, and keep unanswered questions visible.

See [Write like a professor (2026)](spec-example.md) for a worked project. Build a tool that imitates one professor's writing, then ask staff to distinguish real passages from generated ones. Its open questions give the wiki something to investigate.

For [Lab 3](https://agencyai.mit.edu/lab3/), begin here at Step 4, after Checkoff 1. Write and review your project spec in your own project folder before using this starter.

## Start

Clone the repository and work from its root.

```sh
git clone https://github.com/agency-with-ai/reading-map.git
cd reading-map
```

Copy your revised project spec into this folder as `spec.md`. The original in your project folder remains the spec you update. Keep your notes in the `lab3-note.md` you started in Lab 3. Then follow [the wiki guide](reading-wiki/README.md).

No wiki app or package installation is needed. Keep local Git commits as you work; pushing is not required.

## Files

| File or folder | Use |
|---|---|
| `spec.md` | Your revised project spec, copied here by you and ignored by Git |
| [Write like a professor (2026)](spec-example.md) | A concrete writing project with a sample request and two open literature questions |
| [reading-wiki/README.md](reading-wiki/README.md) | The guide to finding, reading, and checking sources |
| [reading-wiki/prompts.md](reading-wiki/prompts.md) | Requests to send Claude for each task |
| [reading-wiki/CONVENTIONS.md](reading-wiki/CONVENTIONS.md) | Rules Claude follows when it finds sources, builds pages, and answers from them |
| `reading-wiki/sources/` | Your source records and notes |
| `reading-wiki/wiki/` | Pages Claude creates and connects |
| `evidence/` | Saved conversations and file-read records |
| [references/](references/README.md) | A guide to the example spec and further reading |

Use project material you may share with Claude, your partner, and staff. Keep your working copy local or in a private repository. Git ignores `spec.md`, saved papers, and `evidence/`. Source records and notes can enter commits, so inspect them before sharing.

The starter's teaching materials are adapted from [courseware](https://github.com/agency-with-ai/courseware) under [CC BY-SA 4.0](LICENSE). Papers, excerpts, and student project files retain their own licenses.
