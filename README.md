# Reading Map

A starter for building and checking a literature wiki around a question from your project spec. Connect papers to a project decision, check the evidence, and keep unanswered questions visible.

See [Write like a professor (2026)](spec-example.md) for a worked project. Build a tool that imitates one professor's writing, then ask readers to distinguish real passages from generated ones. Its open questions give the wiki something to investigate.

## Start

Clone the repository and work from its root.

```sh
git clone https://github.com/agency-with-ai/reading-map.git
cd reading-map
```

Put your project spec in `spec.md`. If you keep it in another project folder, copy it here and keep that original as the spec you update. Use [the example](spec-example.md) to see the detail needed to choose a literature question.

Open the clone in a Claude session that can read and edit local files and search the web. Follow [the wiki guide](reading-wiki/README.md) to find sources, build connected pages, check claims, and use the evidence for a project decision. Keep your reading notes and checks in [your research notes](reading-wiki/sources/notes.md).

No wiki app or package installation is needed. Keep local Git commits as you work; pushing is not required.

## Files

| File or folder | Use |
|---|---|
| `spec.md` | Your project spec, supplied by you and ignored by Git |
| [Write like a professor (2026)](spec-example.md) | A concrete writing project with a sample request and two open literature questions |
| [reading-wiki/README.md](reading-wiki/README.md) | The guide to finding, reading, and checking sources |
| [reading-wiki/prompts.md](reading-wiki/prompts.md) | Requests to send Claude for each task |
| [reading-wiki/CONVENTIONS.md](reading-wiki/CONVENTIONS.md) | Rules Claude follows when it finds sources, builds pages, and answers from them |
| `reading-wiki/sources/` | Your source records and notes |
| `reading-wiki/wiki/` | Pages Claude creates and connects |
| `evidence/` | Saved conversations and file-read records |
| [references/](references/README.md) | A guide to the example spec and further reading |

Use project material you may share with Claude and anyone reviewing your work. Keep your working copy local or in a private repository. Git ignores `spec.md`, saved papers, and `evidence/`. Source records and notes can enter commits, so inspect them before sharing.

The starter is adapted from [Agency with AI course materials](https://github.com/agency-with-ai/courseware) under [CC BY-SA 4.0](LICENSE). Papers, excerpts, and your project files retain their own licenses.
