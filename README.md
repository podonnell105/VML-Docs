# Face Detection: Group Project Hub (QUB CSC3067)

Team workspace and notes for the **QUB CSC3067 Video Analytics** group project "Face Detection".

- **Group:** Patrick, Peter, Daire
- **Lecturers:** Jesus Martinez del Rincon, Baharak Ahmaderaghi

> **Immediate priority:** settle the three classifier experiments and the shared evaluation procedure so work can run in parallel (see [decisions.md](decisions.md)).

> **GitLab is the compulsory submission repository** (the lecturer provides one GitLab repo per group). This GitHub repo is a team workspace and notes only. Code must be mirrored to GitLab before submission **[TO CONFIRM how]**.

## Project summary

Build an automatic face detection system in two parts:

1. **Train and test a face / non-face classifier** (feature descriptor + learning method), using the training crops in `images/face` and `images/non-face`.
2. **Build a multi-scale sliding-window detector** with non-maximum suppression, run it on the four supplied `imX.jpg` images, evaluate it and produce output images with bounding boxes.

Details: [docs/assignment-notes.md](docs/assignment-notes.md) and [docs/overview.md](docs/overview.md).

## Key dates (Europe/London)

| Date | Milestone | Details |
| --- | --- | --- |
| 18-20 Nov 2026 | Initial demo | 10 min per group on MS Teams with Baharak, Jesus or a demonstrator. Formative + summative (10% of module). Submit the presented slide deck, tables and results. |
| Thu 10 Dec 2026 | Final report + code due | Submit via Canvas + GitLab. |
| Fri 11 Dec 2026 | Peer assessment due | Canvas, completed individually. |
| 16 Dec 2026 | Final exam | 40% of module, separate from the project. |

## Repo map

| Path | Purpose |
| --- | --- |
| [README.md](README.md) | This file: summary, dates, repo map, quick start |
| [AGENTS.md](AGENTS.md) / [CLAUDE.md](CLAUDE.md) | Instructions for AI coding assistants (identical content) |
| [docs/overview.md](docs/overview.md) | Marks breakdown, rules in brief, working agreements |
| [docs/assignment-notes.md](docs/assignment-notes.md) | Key notes from the lecture slides |
| [tasks.md](tasks.md) | Task board (55 tasks, 7 phases) |
| [decisions.md](decisions.md) | TBD decisions register |
| [progress-log.md](progress-log.md) | One row per work session |
| [experiments.md](experiments.md) | Experiment results log |
| [meetings/](meetings/TEMPLATE.md) | Meeting notes (copy `TEMPLATE.md`) |
| [src/](src/README.md) | Code (mirror to GitLab) |
| [results/](results/README.md) | Output images, metrics CSVs |

## Quick start for humans

1. Clone this repo and `git pull --rebase` before you start each session.
2. Read [docs/overview.md](docs/overview.md), then check [tasks.md](tasks.md) for your tasks and [decisions.md](decisions.md) for open decisions.
3. Commit small changes straight to `main` (group decision): `git pull --rebase`, edit, commit, `git pull --rebase`, push.
4. After each session: update the task **Status** in [tasks.md](tasks.md), add a line to [progress-log.md](progress-log.md), and record any real results in [experiments.md](experiments.md).
5. Keep datasets (`data/`, `*.cdataset`) out of git. Commit your own work to GitLab as well so individual contributions are visible.
