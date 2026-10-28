# Task board

Source of truth for task status. 55 tasks across 7 phases. Owner tags: a person's name = task owner, **ALL 3** = all three participate, **TBD** = the group still needs to decide or confirm something, **OPTIONAL** = extension, not a core requirement.

## Board summary

| Status | Count |
| --- | --- |
| To do | 55 |
| In progress | 0 |
| In review | 0 |
| Blocked | 0 |
| Done | 0 |
| **Total** | **55** |

Per phase:

| Phase | Tasks | To do | In progress | In review | Blocked | Done |
| --- | --- | --- | --- | --- | --- | --- |
| Phase 1 - Setup & data | 6 | 6 | 0 | 0 | 0 | 0 |
| Phase 2 - Baseline classifier | 8 | 8 | 0 | 0 | 0 | 0 |
| Phase 3 - Compare classifiers | 8 | 8 | 0 | 0 | 0 | 0 |
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
| 1.1 | Set up the group GitLab repository and initial folder structure. | Peter | Owner task | To do | – |  |
| 1.2 | Set up the Python environment and verify dependencies. | Daire | Owner task | To do | – |  |
| 1.3 | Inspect the images/face and images/non-face training crops. | Patrick | Owner task | To do | – |  |
| 1.4 | Inspect face_train.cdataset and face_test.cdataset and document how they are loaded. | Patrick, Daire | Owner task | To do | – |  |
| 1.5 | Review the practical code for SVM, K-NN, Gabor features, sliding windows and NMS. | Patrick, Peter, Daire | ALL 3 | To do | – |  |
| 1.6 | Agree the shared code structure, experiment-recording format and division of responsibilities. | Patrick, Peter, Daire | TBD | To do | – | Group decision needed |

## Phase 2 - Baseline classifier

| ID | Task | Owner | Type tag | Status | Due | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| 2.1 | Decide which feature representations and classifiers to compare. | Patrick, Peter, Daire | TBD | To do | – | See TBD register item 1 |
| 2.2 | Decide how training and testing data will be separated. | Patrick, Peter, Daire | TBD | To do | – | See TBD register item 2 |
| 2.3 | Implement the shared data-loading and labelling pipeline. | Patrick, Daire | Owner task | To do | – |  |
| 2.4 | Implement or adapt the first feature-extraction method. | Patrick | Owner task | To do | – |  |
| 2.5 | Implement or adapt the baseline classifier. | Peter | Owner task | To do | – |  |
| 2.6 | Integrate feature extraction and classification into one working pipeline. | Patrick, Peter, Daire | ALL 3 | To do | – |  |
| 2.7 | Train the baseline model and test it on unseen image crops. | Patrick, Peter, Daire | ALL 3 | To do | – |  |
| 2.8 | Record baseline metrics, settings and limitations. | Daire | Owner task | To do | – |  |

## Phase 3 - Compare classifiers

| ID | Task | Owner | Type tag | Status | Due | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| 3.1 | Implement the first classifier/feature experiment. | Patrick | Owner task | To do | – |  |
| 3.2 | Implement the second classifier/feature experiment. | Peter | Owner task | To do | – |  |
| 3.3 | Implement the third classifier/feature experiment. | Daire | Owner task | To do | – |  |
| 3.4 | Ensure all experiments use a fair, agreed evaluation procedure. | Patrick, Peter, Daire | ALL 3 | To do | – |  |
| 3.5 | Tune relevant model parameters and record each configuration. | Patrick, Peter, Daire | ALL 3 | To do | – |  |
| 3.6 | Calculate recognition rate, TP, FP, TN, FN, precision and recall, as appropriate. | Daire | Owner task | To do | – | All 3 review |
| 3.7 | Compare the results in a single table and select the classifier for the detector. | Patrick, Peter, Daire | TBD | To do | – | Model-selection criteria to be agreed |
| 3.8 | Document why the chosen approach performed best and its limitations. | Patrick, Peter, Daire | ALL 3 | To do | – |  |

## Phase 4 - Build detector

| ID | Task | Owner | Type tag | Status | Due | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| 4.1 | Agree the interface between the classifier and detector. | Patrick, Peter, Daire | TBD | To do | – | Group decision needed |
| 4.2 | Implement the sliding-window scan across an image. | Peter | Owner task | To do | – |  |
| 4.3 | Implement multi-scale detection by resizing the image or scanning at different scales. | Peter | Owner task | To do | – |  |
| 4.4 | Pass each window through the selected classifier and collect candidate detections. | Peter, Patrick | Owner task | To do | – |  |
| 4.5 | Implement or adapt non-maximum suppression (NMS). | Daire | Owner task | To do | – |  |
| 4.6 | Integrate scanning, classification and NMS into one detector. | Patrick, Peter, Daire | ALL 3 | To do | – |  |
| 4.7 | Tune window size, stride, scale changes and NMS settings. | Patrick, Peter, Daire | TBD | To do | – | Select experimentally, record each setting |
| 4.8 | Generate and save images with predicted bounding boxes. | Daire | Owner task | To do | – |  |

## Phase 5 - Test detector

| ID | Task | Owner | Type tag | Status | Due | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| 5.1 | Run the integrated detector on all four supplied imX.jpg images. | Peter | Owner task | To do | – |  |
| 5.2 | Check or obtain the ground-truth face annotations for the test images. | Patrick | TBD | To do | – | Location of ground truth TBD (TBD register item 6) |
| 5.3 | Agree how a predicted bounding box will count as a correct detection. | Patrick, Peter, Daire | TBD | To do | – | See TBD register item 6; no overlap threshold given in lecture material |
| 5.4 | Calculate detection TP, FP, FN and suitable performance metrics. | Daire | Owner task | To do | – |  |
| 5.5 | Inspect annotated outputs for missed faces and false detections. | Patrick, Peter, Daire | ALL 3 | To do | – |  |
| 5.6 | Test whether changes to detector parameters improve results. | Patrick, Peter, Daire | ALL 3 | To do | – |  |
| 5.7 | Record final results and explain when and why the detector fails. | Patrick | Owner task | To do | – | All 3 review |

## Phase 6 - Initial demo

| ID | Task | Owner | Type tag | Status | Due | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| 6.1 | Select the initial feature/classifier combinations and results to present. | Patrick, Peter, Daire | ALL 3 | To do | 2026-11-17 |  |
| 6.2 | Prepare slides explaining the problem, dataset and approach. | Patrick | Owner task | To do | 2026-11-17 |  |
| 6.3 | Prepare the classifier comparison table and initial metrics. | Daire | Owner task | To do | 2026-11-17 |  |
| 6.4 | Prepare the initial detector demonstration and bounding-box outputs. | Peter | Owner task | To do | 2026-11-17 |  |
| 6.5 | Combine slides, results and screenshots into one presentation. | Patrick, Peter, Daire | ALL 3 | To do | 2026-11-17 |  |
| 6.6 | Rehearse the 10-minute presentation and verify that the demonstration works. | Patrick, Peter, Daire | ALL 3 | To do | 2026-11-17 |  |
| 6.7 | Submit the presented slide deck, tables and results as required. | Patrick | Owner task | To do | 2026-11-17 | All 3 review |

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
