# AGENTS.md: instructions for AI coding assistants

This file is for AI coding assistants (Claude etc.) used by Patrick, Peter and Daire. `CLAUDE.md` has identical content.

## What this project is

QUB CSC3067 Video Analytics group project "Face Detection" (group: Patrick, Peter, Daire). We train a face / non-face classifier (feature descriptor + learning method), evaluate it, then build a multi-scale sliding-window detector with non-maximum suppression and run it on four supplied `imX.jpg` images. This repo is a **team workspace and notes**.

**GitLab is the compulsory submission repository** (the lecturer provides one GitLab repo per group). Code must be mirrored to GitLab before submission **[TO CONFIRM how]**. Everyone commits their own work to GitLab so individual contributions are visible.

## Read order

1. [README.md](README.md): summary, key dates, repo map
2. [docs/overview.md](docs/overview.md): marks, rules, working agreements
3. [docs/assignment-notes.md](docs/assignment-notes.md): lecture notes
4. [tasks.md](tasks.md): task board
5. [decisions.md](decisions.md): open and settled decisions
6. [progress-log.md](progress-log.md): what happened recently
7. [experiments.md](experiments.md): results so far

## Rules

- **Never invent lecture content or results.** If something is not in [docs/assignment-notes.md](docs/assignment-notes.md) or the user's sources, say so and mark it **[TO CONFIRM]**.
- **Record only real numbers produced by code** that was actually run. Never estimate, round up, or fill in placeholders with plausible values.
- **Only edit files for tasks the user asked for.** Do not reorganise, reformat or "improve" unrelated files.
- Keep **[TO CONFIRM]** markers until the user confirms the point.
- Do not decide TBD items yourself; propose options and let the group decide.
- Use **ISO dates** (YYYY-MM-DD) and **Europe/London** times.

## Which file to update

| Kind of change | File |
| --- | --- |
| Task status | [tasks.md](tasks.md) (edit the Status cell; keep the board summary counts in step) |
| Progress / work session summary | [progress-log.md](progress-log.md) |
| Experiment results | [experiments.md](experiments.md) |
| Decisions | [decisions.md](decisions.md) |
| Meeting notes | [meetings/](meetings/TEMPLATE.md) (copy `TEMPLATE.md` to `meetings/YYYY-MM-DD.md`) |
| Code | `src/` |
| Output images, metrics CSVs | `results/` |

Allowed Status values: `To do`, `In progress`, `In review`, `Blocked`, `Done`.

## Git workflow and commit conventions

- Make **small commits**.
- Message format: `<area>: <what> (task 3.2)`, e.g. `classifier: add K-NN baseline (task 2.5)`. Include the **author initials** in the commit body.
- **Always `git pull --rebase` before editing and before pushing.**
- **Commit and push straight to `main`** (group decision, 28 Oct 2026). No branches or pull requests needed. Run `git pull --rebase` before editing and again before every push, keep commits small, and if the rebase conflicts, stop and ask the user rather than overwriting someone else's work.
- **Never rewrite shared history** (no force-push, no rebasing pushed commits, no amending pushed commits).
- **Never commit secrets** (tokens, passwords, keys) **or the large datasets** (`data/`, `*.cdataset`, large images).
- **After every work session add a changelog line to [progress-log.md](progress-log.md)** (Date, Who, Phase, Update, Blockers, Next step).
