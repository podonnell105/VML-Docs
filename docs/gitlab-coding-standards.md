# GitLab coding standards

Mandatory for every person and every coding agent before they change the group GitLab repository (CSC3067 Face Detection). This GitHub repo is notes only. These rules apply to GitLab, including anything that ends up on `main`.

Read this file before writing code, committing, pushing, or opening a merge request.

## 1. Personal experiments and results

Personal experiments and the results from those experiments live in a folder named with your initials. They do not go in shared `src/` or shared `results/` until the group has accepted them onto `main`.

| Person | Initials | Folder |
| --- | --- | --- |
| Patrick O'Donnell | POD | `notebooks/POD/` |
| Peter Bryson | PB | `notebooks/PB/` |
| Daire O'Sullivan | DOS | `notebooks/DOS/` |

Notebook path:

```text
notebooks/<INITIALS>/<experiment_name>.ipynb
```

`experiment_name` is snake_case and matches the experiment you are doing. If a GitHub issue says you are running an experiment, that notebook is the place it lives.

Patrick's work on issue #10 (HOG analysis, raw pixels SVM, HOG experiments) looks like this:

```text
notebooks/POD/hog_analysis.ipynb
notebooks/POD/raw_pixels_svm.ipynb
notebooks/POD/hog_experiments.ipynb
```

Plots, metrics and other outputs from that run sit beside the notebook:

```text
notebooks/POD/hog_analysis/
```

Do not put your experiment in someone else's initials folder. Do not commit datasets (`data/`, `*.cdataset`, or other large data files).

Shared code that the group has reviewed belongs in `src/`. Final figures the group has agreed to submit belong in `results/` only after that review.

## 2. Minimal code

Write the smallest amount of code that does the job. A reader should understand every name without a glossary. Prefer one clear function over a pile of helpers. Leave out unused imports, dead branches and code that is not needed for this change.

## 3. Function comments

Put one short comment above each function saying what it does, in plain language. Do not comment every line. Do not restate the code. Add a second sentence only when the reason for the code is not obvious from reading it.

```python
def recognition_rate(y_true, y_pred):
    """Return the fraction of labels the classifier got right."""
```

## 4. Branches and review

Do all GitLab work on your own feature branch. Never commit directly to `main`.

Branch name:

```text
f/<snake_case_summary>
```

Example: `f/hog_svm_baseline`.

Start the branch from an up-to-date `main`. One branch per piece of work.

Before that work can land on `main`:

1. Push the `f/` branch.
2. Open a GitLab merge request into `main`.
3. Ask one of the other two people to review it. The author does not review their own merge request.
4. Merge only after that person approves.

An agent stops at the merge request. It must not merge to `main` and must not push commits onto `main`. Say who still needs to review.

## 5. Commit messages

Use one type prefix, a slash, then a snake_case summary. No spaces. Lower case.

```text
<type>/<snake_case_summary>
```

| Prefix | Use for |
| --- | --- |
| `feat/` | New behaviour |
| `fix/` | A bug fix |
| `refactor/` | A restructure that does not change behaviour |
| `test/` | Tests only |
| `docs/` | Documentation only |
| `chore/` | Setup, tooling or dependencies |

```text
feat/hog_svm_baseline

Train HOG features with an SVM on the training crops.

Initials: POD
```

```text
fix/nms_iou_threshold
```

Put your initials in the commit body. If the work has a task id or GitHub issue, put those in the body too. Keep the subject to the type and the snake_case name.

## Before you push

- You are on `f/<snake_case_summary>`, not `main`.
- Experiments and personal results are under `notebooks/<INITIALS>/`.
- The code is as small as it can be, and each function has a comment saying what it does.
- The commit message is `<type>/<snake_case_summary>`.
- The merge request asks one of the other two people to review.
- You have not merged to `main`.
