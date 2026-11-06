# Progress log

Add a row after each work session: what you did, any blockers and the next step. Newest rows at the bottom. Use ISO dates. See [tasks.md](tasks.md) for the board.

| Date | Who | Phase | Update | Blockers | Next step |
| --- | --- | --- | --- | --- | --- |
| 2026-10-28 | Patrick | | Hub created | | Settle the three classifier experiments and the shared evaluation procedure. |
| 2026-11-02 | Patrick (with assistant) | Phase 1 | Completed task 1.3 data inspection; report in docs/. | | |
| 2026-11-02 | Peter (via Claude) | Phase 1 | Task 1.2 (#3): pinned package versions in the GitLab requirements.txt (Python 3.12+, tested on 3.13.2), added pyproject.toml so notebooks can import src/, extended check_setup.py (Python version, SVM train/predict smoke test), documented setup in the GitLab README. GitLab commit 5b27755. | | Patrick and Daire run the README setup from a clean clone and confirm on #3. |
| 2026-11-02 | Peter (via Claude) | Phase 1-6 | Board updated in tasks.md: demo due dates from docs/demo-plan.md, feature analysis tasks (2.9-2.11) and all six classifier experiments (3.1-3.3, 3.9-3.11), now 61 tasks. Task 1.1 is done (#2) and 2.3 is in review. | | Each owner starts their feature analysis (due 2026-11-05). |
| 2026-11-03 | Patrick (via Cursor) | | Added GitLab coding standards for agents: personal experiment folders, minimal code, function comments, `f/` branches with review, and `feat/` / `fix/` commit names. See docs/gitlab-coding-standards.md. | | Use the standards on the next GitLab change. |
| 2026-11-06 | Peter (via Claude) | Phase 2-4 | Issue #8: raw pixels analysis, raw pixels + k-NN (best k=1, 80.9% on person-grouped folds), `cross_validate` options for training-fold augmentation, person-grouped folds and out-of-fold scores, and a first multi-scale sliding-window detector run on im1-im4. Found that training faces 1-25 are 5 people with 5 photos each (and 48-49 one person), which inflates ordinary-fold results (raw 1-NN 88.3% to 80.9%, raw SVM 89.4% to 87.2%). GitLab draft MR from `f/raw_pixels_analysis` (commits 2e87cac, a05c809, effcf3c, 4c27326). Tasks 2.5, 2.9, 3.2, 4.2, 4.3 in review; 4.4 in progress. | MR waits for `feat/hog_classifier_baselines` to merge, then a rebase | Group to decide on person-grouped folds; plug in NMS and the locked classifier |
| 2026-11-06 | Peter (via Claude) | All | Added docs/progress-map.md: done, built-awaiting-merge and to-do steps for each marked section, with owners. Linked from the README repo map. | | Update the map when a section changes |
