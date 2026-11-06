# Progress map

Snapshot of what is done and what is left, by marked section. **As of 2026-11-06.** The live task status is in [tasks.md](../tasks.md); update this map when a section changes.

**Key:** ✅ done · 🔄 built, waiting for review or merge · ⬜ to do

## Summary

| | Steps |
| --- | --- |
| ✅ Done | 4 |
| 🔄 Built, waiting for review or merge | 11 |
| ⬜ To do | 26 |
| **Total** | **41** |

| Section | Marks | Built (✅ + 🔄) |
| --- | --- | --- |
| Setup | – | 4 of 5 |
| Training the classifier | 32 | 5 of 9 |
| Testing the classifier | 21 | 2 of 6 |
| Detection | 37 | 2 of 10 |
| Extra credit | 10 | 0 of 3 |
| Merging the code | – | 2 of 2 (both 🔄) |
| Initial demo | 10% of module | 0 of 3 |
| Final submission | 30% of module | 0 of 3 |

Nothing beyond the skeleton is on GitLab `main` yet. The built work sits in two branches: `feat/hog_classifier_baselines` (Patrick) and `f/raw_pixels_analysis` (Peter).

## 1. Setup

| | Step | Owner |
| --- | --- | --- |
| ✅ | Repo skeleton and folder structure | Peter |
| ✅ | Python environment pinned, setup check | Peter |
| ✅ | Training data inspected | Patrick |
| ✅ | Loader with safe augmentation | Group |
| ⬜ | Agree the 12 open decisions in [decisions.md](../decisions.md) | All 3 |

## 2. Training the classifier (32 marks)

| | Step | Owner |
| --- | --- | --- |
| 🔄 | Raw pixels analysis | Peter |
| 🔄 | HOG feature and analysis | Patrick |
| ⬜ | Gabor analysis | Daire |
| 🔄 | Raw pixels + SVM tuned | Patrick |
| 🔄 | Raw pixels + k-NN tuned | Peter |
| 🔄 | HOG + SVM and HOG + k-NN tuned | Patrick |
| ⬜ | Gabor + SVM and Gabor + k-NN | Daire |
| ⬜ | Preprocessing experiment (histogram equalisation) | Anyone |
| ⬜ | PCA / LDA features (after Prac 6) | Anyone |

## 3. Testing the classifier (21 marks)

| | Step | Owner |
| --- | --- | --- |
| 🔄 | Shared cross-validation and metrics | Patrick, Peter |
| 🔄 | Person-grouped folds | Peter |
| ⬜ | Group decides the fold rule ([#11](https://github.com/podonnell105/VML-Docs/issues/11)) | All 3 |
| ⬜ | Rerun HOG on person-grouped folds | Patrick |
| ⬜ | Lock settings and run the test set once (11 Nov) | All 3 |
| ⬜ | One comparison table and graphs | Daire |

## 4. Detection (37 marks)

| | Step | Owner |
| --- | --- | --- |
| 🔄 | Sliding window | Peter |
| 🔄 | Multi-scale search | Peter |
| ⬜ | Non-maximum suppression | Daire |
| ⬜ | Plug in the locked classifier | Peter |
| ⬜ | Ground-truth boxes for im1 to im4 | All 3 |
| ⬜ | Detection TP, FP, FN, precision and recall | Daire |
| ⬜ | Hard negative mining | Peter |
| ⬜ | Tune threshold, step and scales | All 3 |
| ⬜ | Final output images with boxes | Daire |
| ⬜ | Failure analysis: why and when it fails | Patrick |

## 5. Extra credit (10 marks)

| | Step | Owner |
| --- | --- | --- |
| ⬜ | Leave-one-out cross-validation | Anyone |
| ⬜ | ROC curves from SVM scores | Anyone |
| ⬜ | Random forest, AdaBoost or neural network | Anyone |

## 6. Merging the code

| | Step | Owner |
| --- | --- | --- |
| 🔄 | `feat/hog_classifier_baselines` (needs the OpenCV setup fix) | Patrick |
| 🔄 | `f/raw_pixels_analysis` (rebase after Patrick's branch merges) | Peter |

## 7. Initial demo (18 to 20 Nov, 10% of module)

| | Step | Owner |
| --- | --- | --- |
| ⬜ | Slides: pipeline, results, detector | All 3 |
| ⬜ | Timed rehearsal | All 3 |
| ⬜ | Present and submit slides | Patrick |

## 8. Final submission (10 to 11 Dec, 30% of module)

| | Step | Owner |
| --- | --- | --- |
| ⬜ | Report: training, testing, detection, discussion | All 3 |
| ⬜ | Clean, commented code that reproduces the report | All 3 |
| ⬜ | Peer assessment | Each |
