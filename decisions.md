# Decisions to settle (TBD register)

Resolve these together at the next group meeting. Tick each item when decided and write the outcome on the **Decision** line, plus **Decided by/date**. Related tasks: [tasks.md](tasks.md). Log each decision session in [progress-log.md](progress-log.md).

- [ ] **1. Classifier experiments:** which three feature/classifier combinations will we compare?
  - Suggested start: SVM + pixels, K-NN + pixels, SVM + Gabor features.
  - Decision:
  - Decided by/date:
- [ ] **2. Evaluation:** which training/testing strategy will we use?
  - Suggested start: use the supplied `face_train.cdataset` and `face_test.cdataset` if suitable; confirm their format and purpose first.
  - Decision:
  - Decided by/date:
- [ ] **3. Evaluation:** which metrics will we report?
  - Suggested start: recognition rate and confusion-matrix counts (TP, FP, TN, FN), plus precision and recall; add specificity where appropriate.
  - Decision:
  - Decided by/date:
- [ ] **4. Detector:** what window size, stride and scale factor will we start with?
  - Suggested start: pick a baseline, then tune systematically and record each setting.
  - Decision:
  - Decided by/date:
- [ ] **5. NMS:** what overlap threshold will we use to suppress duplicate detections?
  - Suggested start: choose a starting value and compare results on validation examples.
  - Decision:
  - Decided by/date:
- [ ] **6. Ground truth:** where are the ground-truth boxes for the four full images, and how will matches be judged?
  - Suggested start: confirm the annotations and agree a bounding-box overlap rule before calculating detection metrics. (The lecture material reviewed gives no specific overlap threshold.)
  - Decision:
  - Decided by/date:
- [ ] **7. Demo:** what must be finished and who presents each section?
  - Suggested start: aim to show classifier comparisons, a working initial detector, parameter tuning and recorded results.
  - Decision:
  - Decided by/date:
- [ ] **8. Extensions:** will we attempt any extra-credit techniques?
  - Suggested start: decide only after the core classifier and detector work reliably.
  - Decision:
  - Decided by/date:
