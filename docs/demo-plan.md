# Plan to the initial demo

Assumes a demo on 18 November. Confirm the slot with staff.

| # | Step | Owner | Finish by |
|---|---|---|---|
| 1 | Analyse your feature: raw pixels, Gabor or HOG | Peter, Daire, Patrick | 5 Nov |
| 2 | Share findings and agree decisions: evaluation, normalisation and settings to test | Everyone | 5 Nov |
| 3 | Build the shared pipeline: folds, scoring, and raw pixels + k-NN | Peter, with review | 6 Nov |
| 4 | Run raw pixels + SVM and Gabor + SVM | Patrick, Daire | 8 Nov |
| 5 | Build the sliding window, starting with raw pixels + k-NN | Peter | 10 Nov |
| 6 | Run Gabor + k-NN, HOG + SVM and HOG + k-NN | Daire, Patrick | 10 Nov |
| 7 | Lock settings, run the test set once, and choose one or two classifiers | Everyone | 11 Nov |
| 8 | Finish the first detector: scales, NMS and the chosen classifier | Peter, Daire | 13 Nov |
| 9 | Annotate eyebrow-to-chin face boxes on all four photos | Split between everyone | 13 Nov |
| 10 | Run and score the detector, save output images and note failures | Everyone | 15 Nov |
| 11 | Make the slides and results files | Everyone | 16 Nov |
| 12 | Rehearse a timed 10-minute run through on Teams | Everyone | 17 Nov |
| 13 | Do the demo and submit the slides, tables and results | Everyone | 18 Nov |

## Shared comparison rules

1. Use one shared pipeline, with the same folds, random seed and scoring code.
2. Tune with cross-validation on the 94 training crops only.
3. Keep crops of the same person in the same fold where we can identify them.
4. Augment only the training part of each fold, never the validation or test data.
5. Fit normalisation and PCA on the training part of each fold only.
6. Run the 30 test crops once, after settings are locked.
7. Report accuracy, precision, recall, specificity, a confusion matrix and runtime per crop.
8. Compare against the 66.7% test accuracy from always predicting "face".

## If we fall behind

Drop the HOG experiments first, then Gabor + k-NN. Keep the detector, as the demo expects an initial attempt.

## Demo contents

1. System pipeline and experimental setup
2. Feature analysis
3. Classifier results table and reasons for our choices
4. Detector output on the four photos, with detection scores
5. What fails, why, and what we will do before the final submission
