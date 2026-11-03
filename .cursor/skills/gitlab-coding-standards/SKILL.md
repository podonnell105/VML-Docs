---
name: gitlab-coding-standards
description: >-
  Enforces CSC3067 GitLab coding standards before any code, commit, push, or
  merge to the group GitLab repo. Use when contributing to GitLab, editing the
  face-detection coursework repo, writing notebooks or experiments, naming
  branches, writing commit messages, opening a merge request, or committing to
  main. Requires personal experiment folders, minimal code, function comments,
  f/ feature branches, peer review, and feat/ or fix/ snake_case commits.
---

# GitLab coding standards

Before writing, committing, pushing, or merging any code in the group GitLab repository, read and follow [docs/gitlab-coding-standards.md](../../../docs/gitlab-coding-standards.md) in the VML-Docs repo. If this workspace is the parent project, the same file is `VML-Docs/docs/gitlab-coding-standards.md`.

These rules apply to GitLab only. The GitHub VML-Docs repo still commits small docs changes straight to `main`.

## Hard rules

1. Personal experiments and their results go in `notebooks/<INITIALS>/<experiment_name>.ipynb`. Initials: Patrick `POD`, Peter `PB`, Daire `DOS`. Example: `notebooks/POD/hog_analysis.ipynb`.
2. Keep code minimal. Every name should be understandable on its own.
3. One plain-language comment above each function saying what it does.
4. Work on a branch named `f/<snake_case_summary>`. Do not commit to `main`. Open a merge request and get one of the other two people to review it. The author does not approve their own request. An agent must not merge to `main`.
5. Commit messages are `<type>/<snake_case_summary>`, for example `feat/hog_svm_baseline` or `fix/nms_iou_threshold`. Allowed types: `feat/`, `fix/`, `refactor/`, `test/`, `docs/`, `chore/`. Put initials in the body.

Do not commit datasets.
