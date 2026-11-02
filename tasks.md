# Task board

Source of truth for task status. 61 tasks across 7 phases. Owner tags: a person's name = task owner, **ALL 3** = all three participate, **TBD** = the group still needs to decide or confirm something, **OPTIONAL** = extension, not a core requirement.

The dates up to the demo follow [docs/demo-plan.md](docs/demo-plan.md).

## Board summary

| Status | Count |
| --- | --- |
| To do | 57 |
| In progress | 0 |
| In review | 2 |
| Blocked | 0 |
| Done | 2 |
| **Total** | **61** |

Per phase:

| Phase | Tasks | To do | In progress | In review | Blocked | Done |
| --- | --- | --- | --- | --- | --- | --- |
| Phase 1 - Setup & data | 6 | 3 | 0 | 1 | 0 | 2 |
| Phase 2 - Baseline classifier | 11 | 10 | 0 | 1 | 0 | 0 |
| Phase 3 - Compare classifiers | 11 | 11 | 0 | 0 | 0 | 0 |
| Phase 4 - Build detector | 8 | 8 | 0 | 0 | 0 | 0 |
| Phase 5 - Test detector | 7 | 7 | 0 | 0 | 0 | 0 |
| Phase 6 - Initial demo | 7 | 7 | 0 | 0 | 0 | 0 |
| Phase 7 - Report & submission | 11 | 11 | 0 | 0 | 0 | 0 |

> Keep this summary in step with the tables below whenever you change a status.

## How to update

1. Edit the **Status** cell of the task row (allowed values: `To do`, `In progress`, `In review`, `Blocked`, `Done`).
2. Add a line to [progress-log.md](progress-log.md) describing what changed.
3. Update the board summary counts above.
4. Put new results in [experiments.md](experiments.md) and agreed decisions in [decisions.md](decisions.md); see [AGENTS.md](AGENTS.md) for commit conventions.

## Phase 1 - Setup & data

| ID | Task | Owner | Type tag | Status | Due | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| 1.1 | Set up the group GitLab repository and initial folder structure. | Peter | Owner task | Done | – | Skeleton pushed to GitLab |
| 1.2 | Set up the Python environment and verify dependencies. | Daire | Owner task | In review | 2026-11-04 | Done by Peter. Patrick and Daire to confirm a clean setup on #3 |
| 1.3 | Inspect the images/face and images/non-face training crops. | Patrick | Owner task | Done | – | [training-data-analysis.html](docs/training-data-analysis.html), [dataset-summary.md](docs/dataset-summary.md). Corrections to the report still to be made |
| 1.4 | Inspect face_train.cdataset and face_test.cdataset and document how they are loaded. | Patrick, Daire | Owner task | To do | 2026-11-04 |  |
| 1.5 | Review the practical code for SVM, K-NN, Gabor features, sliding windows and NMS. | Patrick, Peter, Daire | ALL 3 | To do | As released | Prac 4-6 not yet completed. Use sklearn until then |
| 1.6 | Agree the shared code structure, experiment-recording format and division of responsibilities. | Patrick, Peter, Daire | TBD | To do | 2026-11-05 | Group decision needed |

## Phase 2 - Baseline classifier

| ID | Task | Owner | Type tag | Status | Due | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| 2.1 | Decide which feature representations and classifiers to compare. | Patrick, Peter, Daire | TBD | To do | 2026-11-05 | Proposed: raw pixels, Gabor and HOG, each with k-NN and SVM |
| 2.2 | Decide how training and testing data will be separated. | Patrick, Peter, Daire | TBD | To do | 2026-11-05 | Proposed: supplied 94/30 split, tuning with cross-validation on the 94 |
| 2.3 | Implement the shared data-loading and labelling pipeline. | Patrick, Daire | Owner task | In review | 2026-11-04 | `src/data_loader.py` is in the skeleton, for Patrick and Daire to review |
| 2.4 | Implement or adapt the first feature-extraction method. | Patrick | Owner task | To do | 2026-11-06 | `raw_pixels()` is in the skeleton, for Patrick to review |
| 2.5 | Implement or adapt the baseline classifier. | Peter | Owner task | To do | 2026-11-06 | Raw pixels + k-NN |
| 2.6 | Integrate feature extraction and classification into one working pipeline. | Patrick, Peter, Daire | ALL 3 | To do | 2026-11-06 | Peter leads, others review |
| 2.7 | Train the baseline model and evaluate it with cross-validation on the training crops. | Patrick, Peter, Daire | ALL 3 | To do | 2026-11-06 | Test set stays unused until task 3.7 |
| 2.8 | Record baseline metrics, settings and limitations. | Daire | Owner task | To do | 2026-11-06 |  |
| 2.9 | Analyse raw pixel features. | Peter | Owner task | To do | 2026-11-05 | Training crops only. See [demo plan](docs/demo-plan.md) |
| 2.10 | Analyse Gabor features. | Daire | Owner task | To do | 2026-11-05 | Training crops only. See [demo plan](docs/demo-plan.md) |
| 2.11 | Analyse HOG features. | Patrick | Owner task | To do | 2026-11-05 | Training crops only. Confirm with staff that HOG is acceptable |

## Phase 3 - Compare classifiers

| ID | Task | Owner | Type tag | Status | Due | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| 3.1 | Run raw pixels + SVM. | Patrick | Owner task | To do | 2026-11-08 | Tune `C`, kernel and normalisation |
| 3.2 | Tune raw pixels + k-NN. | Peter | Owner task | To do | 2026-11-08 | Tune `k` and normalisation |
| 3.3 | Run Gabor + SVM. | Daire | Owner task | To do | 2026-11-08 | Tune `C`, kernel and PCA |
| 3.4 | Ensure all experiments use a fair, agreed evaluation procedure. | Patrick, Peter, Daire | ALL 3 | To do | 2026-11-06 | See comparison rules in the [demo plan](docs/demo-plan.md) |
| 3.5 | Tune relevant model parameters and record each configuration. | Patrick, Peter, Daire | ALL 3 | To do | 2026-11-10 |  |
| 3.6 | Calculate recognition rate, TP, FP, TN, FN, precision, recall and specificity, as appropriate. | Daire | Owner task | To do | 2026-11-06 | All 3 review. Daire writes the metrics and the pipeline calls them |
| 3.7 | Lock settings, run the test set once, compare the results in a single table and select the classifier(s) for the detector. | Patrick, Peter, Daire | TBD | To do | 2026-11-11 | Proposed criteria: accuracy, runtime and a usable score for NMS |
| 3.8 | Document why the chosen approach performed best and its limitations. | Patrick, Peter, Daire | ALL 3 | To do | 2026-11-11 |  |
| 3.9 | Run Gabor + k-NN. | Daire | Owner task | To do | 2026-11-10 | Test with and without PCA. Drop if behind, after HOG |
| 3.10 | Run HOG + SVM. | Patrick | Owner task | To do | 2026-11-10 | First to drop if behind |
| 3.11 | Run HOG + k-NN. | Patrick | Owner task | To do | 2026-11-10 | First to drop if behind |

## Phase 4 - Build detector

| ID | Task | Owner | Type tag | Status | Due | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| 4.1 | Agree the interface between the classifier and detector. | Patrick, Peter, Daire | TBD | To do | 2026-11-06 | Group decision needed |
| 4.2 | Implement the sliding-window scan across an image. | Peter | Owner task | To do | 2026-11-10 | Start with raw pixels + k-NN |
| 4.3 | Implement multi-scale detection by resizing the image or scanning at different scales. | Peter | Owner task | To do | 2026-11-13 |  |
| 4.4 | Pass each window through the selected classifier and collect candidate detections. | Peter, Patrick | Owner task | To do | 2026-11-13 |  |
| 4.5 | Implement or adapt non-maximum suppression (NMS). | Daire | Owner task | To do | 2026-11-13 |  |
| 4.6 | Integrate scanning, classification and NMS into one detector. | Patrick, Peter, Daire | ALL 3 | To do | 2026-11-13 |  |
| 4.7 | Tune stride, scale changes and NMS settings. | Patrick, Peter, Daire | TBD | To do | 2026-11-15 | The window stays 18x27. Select experimentally, record each setting |
| 4.8 | Generate and save images with predicted bounding boxes. | Daire | Owner task | To do | 2026-11-13 |  |

## Phase 5 - Test detector

| ID | Task | Owner | Type tag | Status | Due | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| 5.1 | Run the integrated detector on all four supplied imX.jpg images. | Peter | Owner task | To do | 2026-11-15 |  |
| 5.2 | Check or obtain the ground-truth face annotations for the test images. | Patrick, Peter, Daire | ALL 3 | To do | 2026-11-13 | Patrick asks staff. Otherwise split annotation, using eyebrow-to-chin boxes |
| 5.3 | Agree how a predicted bounding box will count as a correct detection. | Patrick, Peter, Daire | TBD | To do | 2026-11-13 | Proposed: IoU >= 0.5. No threshold given in lecture material |
| 5.4 | Calculate detection TP, FP, FN and suitable performance metrics. | Daire | Owner task | To do | 2026-11-15 |  |
| 5.5 | Inspect annotated outputs for missed faces and false detections. | Patrick, Peter, Daire | ALL 3 | To do | 2026-11-15 |  |
| 5.6 | Test whether changes to detector parameters improve results. | Patrick, Peter, Daire | ALL 3 | To do | 2026-11-15 | First pass for the demo. Continue for the report |
| 5.7 | Record results and explain when and why the detector fails. | Patrick | Owner task | To do | 2026-11-15 | All 3 review. First pass for the demo. Finalise for the report |

## Phase 6 - Initial demo

| ID | Task | Owner | Type tag | Status | Due | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| 6.1 | Select the initial feature/classifier combinations and results to present. | Patrick, Peter, Daire | ALL 3 | To do | 2026-11-16 |  |
| 6.2 | Prepare slides explaining the problem, dataset and approach. | Patrick | Owner task | To do | 2026-11-16 |  |
| 6.3 | Prepare the classifier comparison table and initial metrics. | Daire | Owner task | To do | 2026-11-16 |  |
| 6.4 | Prepare the initial detector demonstration and bounding-box outputs. | Peter | Owner task | To do | 2026-11-16 |  |
| 6.5 | Combine slides, results and screenshots into one presentation. | Patrick, Peter, Daire | ALL 3 | To do | 2026-11-16 |  |
| 6.6 | Rehearse the 10-minute presentation and verify that the demonstration works. | Patrick, Peter, Daire | ALL 3 | To do | 2026-11-17 |  |
| 6.7 | Do the demo and submit the presented slide deck, tables and results as required. | Patrick | Owner task | To do | 2026-11-18 | All 3 present and review. Confirm the slot and submission deadline |

## Phase 7 - Report & submission

| ID | Task | Owner | Type tag | Status | Due | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| 7.1 | Draft the introduction, project objective and dataset description. | Patrick | Owner task | To do | 2026-12-10 |  |
| 7.2 | Document the feature extraction and classifier methods. | Peter | Owner task | To do | 2026-12-10 |  |
| 7.3 | Document the experimental setup, metrics and classifier comparison. | Daire | Owner task | To do | 2026-12-10 |  |
| 7.4 | Document the sliding-window detector, multi-scale approach and NMS. | Peter | Owner task | To do | 2026-12-10 |  |
| 7.5 | Present the quantitative results, tables and annotated images. | Daire, Peter | Owner task | To do | 2026-12-10 |  |
| 7.6 | Write the discussion, failure analysis and conclusions. | Patrick | Owner task | To do | 2026-12-10 | All 3 review |
| 7.7 | Review the complete report for clarity and justification of decisions. | Patrick, Peter, Daire | ALL 3 | To do | 2026-12-10 |  |
| 7.8 | Organise, comment and test the final code so the lecturer can run it. | Patrick, Peter, Daire | ALL 3 | To do | 2026-12-10 |  |
| 7.9 | Check that reported results match the submitted code and output images. | Patrick, Peter, Daire | ALL 3 | To do | 2026-12-10 |  |
| 7.10 | Submit the final report and code through the required channels. | Patrick | Owner task | To do | 2026-12-10 | All 3 review. Canvas + GitLab |
| 7.11 | Complete individual peer assessments. | Patrick, Peter, Daire | ALL 3 | To do | 2026-12-11 | Each member completes their own, on Canvas |
