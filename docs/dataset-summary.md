# Training data summary (Task 1.3, issue #4)

We measured all numbers from `images/`, `*.cdataset`, `*.ipynb`, `gabor.mat` and `im*.jpg`. The full report with figures is `training-data-analysis.html`.

## Key numbers
| | face | non-face |
|---|---|---|
| Count | 69 | 55 (files 1–59, missing 18, 19, 24, 40) |
| Share | 55.6% | 44.4% (1.25:1) |
| Format | PNG, mode L, 8-bit uint8 | same |
| Size (W×H) | 18×27, all | 18×27, all |
| Pooled mean / std | 98.0 / 58.0 | 98.1 / 66.2 |
| Per-image mean (avg ± sd) | 98.0 ± 29.0 | 98.1 ± 46.8 |
| Avg per-image std | 49.0 | 42.9 |
| Min / max | 0 / 255 | 0 / 255 |

- Corrupt files: 0. Exact duplicates (MD5 of pixels): 0.
- The correlation between the mean face image and the mean non-face image is 0.69. Some non-face images show partial or shifted faces (hard negatives).

## Splits (.cdataset)
The files are plain text: `CroppedImageDatabase` / `18 27` / count / one `±1 path` line for each sample.
- `face_train.cdataset`: 94 (49 face: face/1–49; 45 non-face)
- `face_test.cdataset`: 30 (20 face: face/50–69; 10 non-face: non-face/50–59)
- The files refer to each of the 124 images one time. No image is in both sets.
- `load_face_images(augmented=True)` makes 10 samples from each face image and 4 from each non-face image. Thus, the train set has 490 vs 180 samples (calculated from the code).

## Supporting files
- `loadFaceImages.ipynb` defines `load_face_images(filename, sampling=1, augmented=True)`. It uses numpy and cv2. It returns 486-dim float64 vectors (column order) and labels.
- `gabor_feature_vector.ipynb` defines `gabor_feature_vector(image)`. It uses numpy, cv2 and scipy. It applies CLAHE and a 5×8 Gabor bank in the FFT domain. The output is a 19,440-dim vector. The input size must be 27×18.
- `gabor.mat` has one key, `G`: a 5×8 cell of 32×32 filters. It has no ground-truth boxes.
- Full images (all greyscale JPG): im1 150×65, im2 130×96, im3 150×150, im4 600×254. The files have no ground truth.

## Implications
- Use a detection window of 18×27 (W×H).
- Use a multi-scale image pyramid.
- Correct the imbalance after augmentation (2.7:1). Use class weights or hard-negative mining.
- Normalise each detection window (z-score or CLAHE). Global brightness does not separate the classes (both means are approximately 98).
- Use the 94/30 split from the files.
- Do not augment the test set.
- Report the metrics for each class.
- Use cross-validation to tune the model.

## Open questions [TO CONFIRM]
1. Are the non-face files 18, 19, 24 and 40 missing on purpose?
2. Will the module staff give ground-truth boxes for im1–im4, or must we make them?
3. Is the same person in the train set and the test set (identity leakage)?
4. CLAHE `tileGridSize=(3,8)`: does it agree with the comment "8 rows × 3 cols"?
5. The `np.roll` shifts move edge pixels to the opposite edge. Is this a problem?

_Text written to ASD-STE100 Simplified Technical English._
