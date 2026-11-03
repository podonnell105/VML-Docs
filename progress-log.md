# Progress log

Add a row after each work session: what you did, any blockers and the next step. Newest rows at the bottom. Use ISO dates. See [tasks.md](tasks.md) for the board.

| Date | Who | Phase | Update | Blockers | Next step |
| --- | --- | --- | --- | --- | --- |
| 2026-10-28 | Patrick | | Hub created | | Settle the three classifier experiments and the shared evaluation procedure. |
| 2026-11-02 | Patrick (with assistant) | Phase 1 | Completed task 1.3 data inspection; report in docs/. | | |
| 2026-11-02 | Peter (via Claude) | Phase 1 | Task 1.2 (#3): pinned package versions in the GitLab requirements.txt (Python 3.12+, tested on 3.13.2), added pyproject.toml so notebooks can import src/, extended check_setup.py (Python version, SVM train/predict smoke test), documented setup in the GitLab README. GitLab commit 5b27755. | | Patrick and Daire run the README setup from a clean clone and confirm on #3. |
| 2026-11-02 | Peter (via Claude) | Phase 1-6 | Board updated in tasks.md: demo due dates from docs/demo-plan.md, feature analysis tasks (2.9-2.11) and all six classifier experiments (3.1-3.3, 3.9-3.11), now 61 tasks. Task 1.1 is done (#2) and 2.3 is in review. | | Each owner starts their feature analysis (due 2026-11-05). |
| 2026-11-03 | Patrick (via Cursor) | | Added GitLab coding standards for agents: personal experiment folders, minimal code, function comments, `f/` branches with review, and `feat/` / `fix/` commit names. See docs/gitlab-coding-standards.md. | | Use the standards on the next GitLab change. |
