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

## Agent workflow: issues, documentation and task updates

This repo is **managed by agents** (Claude and others working for Patrick, Peter and Daire). The rules below are mandatory for every agent.

### Issues are our ticket system
- **Every task in [tasks.md](tasks.md) has one GitHub Issue**, titled `<task ID> <task name>` (e.g. `3.2 Implement the second classifier/feature experiment`). Use labels for the phase (`phase-1` ... `phase-7`), the owner (`patrick`, `peter`, `daire`) and the type (`all-3`, `tbd`, `optional`). If an issue for the task does not exist yet, create it before starting work.
- **Start of work:** find the issue for the task you were asked to do, comment that you are starting, and set the task Status in `tasks.md` to `In progress`.
- **New problems:** if you hit a bug, blocker, open question or decision that is not already tracked, **open a new issue** (label `bug`, `blocked` or `question`) with what you saw, what you tried and what is needed. Link it to the related task ID. Set the task Status to `Blocked` if it stops work.
- **Every commit message references its issue**, e.g. `classifier: add K-NN baseline (task 2.5, #12)`. Close the issue only with a comment that says what was done and links the commit, and only when the task is genuinely finished.
- Never delete issues. Never close another person's issue unless the user told you to.

### Document every change
After **every** work session or change, before you finish:
1. **Update the task Status** in [tasks.md](tasks.md) (`To do`, `In progress`, `In review`, `Blocked`, `Done`) for each task you touched, and refresh the status counts at the top of that file.
2. **Add a line to [progress-log.md](progress-log.md)**: Date (ISO), Who (the human you are working for), Phase, Update (what changed and the issue number), Blockers, Next step. Mention which agent did it, e.g. `Patrick (via Claude)`.
3. **Record real results** in [experiments.md](experiments.md): the exact configuration, split, metrics and who ran it. Only numbers produced by code that actually ran.
4. **Record decisions** in [decisions.md](decisions.md): tick the item, fill in the Decision and Decided by/date lines, and update any task that depended on it.
5. **Comment on the related issue** with a short summary of the change and the commit link.
6. If you changed code behaviour, interfaces or how to run something, update the relevant documentation (README or the docs/ folder) in the same commit.

### Keep tasks in sync
- A task is `Done` only when its output exists in the repo (code, results, notes) and its issue is closed with a summary.
- If your work affects other tasks (for example changing the classifier interface affects phase 4), update those tasks' Notes in `tasks.md` and comment on their issues.
- If you find tasks, issues and files out of sync, fix them or open an issue saying what is wrong. Do not leave it silently.

### Hand-off check (do this before you tell the user you are done)
- [ ] Issue commented and, if finished, closed
- [ ] `tasks.md` status and counts updated
- [ ] `progress-log.md` line added
- [ ] `experiments.md` / `decisions.md` updated if relevant
- [ ] Commit message references the task ID and issue number
- [ ] Pulled with `--rebase` and pushed to `main`
