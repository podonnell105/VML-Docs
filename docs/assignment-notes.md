# Assignment notes

Source: CSC3067 Face Detection lecture slides (Jesus Martinez del Rincon, Baharak Ahmaderaghi). Back to [overview](overview.md) · [README](../README.md).

## Marks

| Component | Marks |
| --- | --- |
| Training the automatic system | 32 |
| Testing / evaluating the classifier | 21 |
| Detection implementation | 37 |
| Extra credit | up to 10 |

> **[TO CONFIRM]** Slide 4 says "40% (24 marks)" as the minimum, and the totals do not obviously reconcile. The slides also mention "pedestrian" in places, likely leftover text; the task is faces.

## Training

- Two components: a **feature descriptor** and a **learning method**.
- Feature descriptors: full image (Prac 4 and 5); dimensionality reduction (Prac 6, e.g. PCA/LDA); Gabor features via the provided `gabor_feature_vector.ipynb` (used similarly to HOG in Prac 5).
- Learning methods: SVM, Nearest Neighbour, K-NN (Prac 4).
- Training crops are in `images/face` and `images/non-face`.
- Justify the choices and parameter values.

## Testing

- Split the data into train/test. Options: the provided `face_train.cdataset` and `face_test.cdataset`; half/half; cross validation.
- Use the test set to choose the best techniques and parameters.
- Metrics: recognition rate; TP/FP/TN/FN (Prac 6); precision, recall, specificity, sensitivity.

## Detection

- Sliding window crops at every location; the classifier decides face or not.
- Multiple scales (resize the image).
- Non-maxima suppression (Prac 5) removes overlapping detections, keeping the strongest.
- Run on the 4 files `imX.jpg`, evaluate (TP, FP, TN, FN etc.), generate output images with bounding boxes, and reflect on why and when it fails.

## Available code

- No implementation is provided, only usage. Prac 4: SVM functions + sklearn alternative. Prac 6: LDA.
- Already developed in the practicals: preprocessing (Prac 1-2), NMS (Prac 5), K-NN (Prac 4), sliding windows concept (Prac 4, 5), evaluation metrics (Prac 6), PCA (Prac 6).
- Main thing to implement: the **multi-scale sliding window**.

## Basic system

- Try as many combinations of methods as possible, especially feature extraction and classifiers.
- Final performance does NOT determine the mark. What counts: correct experimental setup, quantitative evaluation, tables/graphs, good parameter setting, and good analysis and explanation of decisions.

## Excellent system / extra credit (up to 10)

- Boosting/bagging, random trees or NN/DNN classifiers.
- Leave-one-out cross validation.
- ROC curves.
- Own feature extractor.
- Part-based detectors.

## Critical analysis

- Justify every decision with objective data.
- Weak: "We applied SVM."
- Good: "... because it requires few training images, fitting our problem."
- Excellent: add an empirical comparison with another method, e.g. a 10% gain shown in Table 1.

## Initial demo (10%)

- Completing Prac 4 and 5 gives a good baseline.
- Show real progress: initial feature + classifier combinations, a first detector attempt, parameter tuning.
- Get the marking template and written feedback.

## Report and code

- Report: clear structure in logical order (training, testing, ...), many pictures/tables of results, justify every decision.
- Code: the lecturer must be able to run it and understand it; comments and good structure.
- GitLab is compulsory (one repo per group provided); include code and result images; results must match the report; include only final results, not all intermediates.

## Peer assessment

- Professional behaviour and respect; all members must contribute to all aspects.
- Criteria: 4 categories (Design, Implementation, Testing, Report), scored out of 10 each (per the slides' worked example, totals like 31, 29), plus a one-paragraph comment.
- The lecturer moderates marks using GitLab contributions and may call a group interview (all members present). Raise group problems early.

## Office hours

- Jesus: Wed 14:00-17:00, 16 Malone Road 01.008.
- Baharak: Tue and Thu 11:00-12:30, CSB 0G.010.
- MS Teams is fine; email first.
