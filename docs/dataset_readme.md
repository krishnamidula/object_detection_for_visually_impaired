# Dataset README

This document describes where dataset files should be stored and the expected structure.

## Raw data (original downloads)
- `data/raw/iodr/`  
  - Put the original IODR dataset files (images and annotations) here as downloaded.
- `data/raw/coco/`  
  - Put the COCO subset images and annotations you download for outdoor classes here.
- `data/raw/custom/`  
  - Put any custom-collected images (unlabeled) here for later annotation.

## Processed data (YOLO-ready)
After annotation/conversion, processed files go here:
- `data/processed/train/`  
  - Images and matching `.txt` annotation files for training.
- `data/processed/val/`  
  - Images and `.txt` files for validation.
- `data/processed/test/`  
  - Images and `.txt` files for testing.

Each `.txt` annotation file must follow YOLO format: one object per line with `class_id x_center y_center width height` (normalized).  
Image sizes will be standardized later (e.g., 640×640) during the training pipeline.

## Notes / next steps
1. Download IODR dataset and place files into `data/raw/iodr/`.  
2. Decide which COCO classes to download (vehicle, curb, person if needed) and place them in `data/raw/coco/`.  
3. Collect 100–300 custom images for `small_object` and put them in `data/raw/custom/` for annotation.  
4. We will then convert raw annotations to YOLO `.txt` files and split into train/val/test under `data/processed/`.

(Keep this file updated as the dataset evolves.)
