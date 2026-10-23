# Image Quality Control — When Focus Scores Fail

## Overview

A sharpness score that falls as a field goes out of focus can still reject a good field, or keep a bad one, when the exposure changes. This module builds a small synthetic acquisition — hard-edged ellipses, a Gaussian PSF, photon noise, a gain, and a vignette — and compares four no-reference scores while one of those factors changes at a time.

The images are generated in the notebook. They are not experimental microscopy, and a cutoff fit on them is not a cutoff for a real microscope.

## What you will learn

- How normalized variance, Laplacian variance, a no-reference blur score, and a mid-band spectral slope respond to defocus when the object is held fixed.
- Which of those scores move when photon count, object density, clipping, exposure, or shading changes and focus does not.
- Why an empty field can look sharp to one score and blurred to another.
- How to fit a reject/keep cutoff on one set of objects and count false positives and false negatives on objects that were held out.

## Notebooks

| File | Description |
|------|-------------|
| [`image_quality_metric_failure_modes.ipynb`](image_quality_metric_failure_modes.ipynb) | Controlled failure cases for four sharpness scores, plus a field-grouped cutoff with false-positive and false-negative rates. |

## Setup

```bash
pip install numpy scipy scikit-image matplotlib scikit-learn
```

No GPU is required. The notebook runs in a few seconds on CPU, including a free Colab CPU runtime.
