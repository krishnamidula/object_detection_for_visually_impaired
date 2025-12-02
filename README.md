# object_detection_for_visually_impaired
# Object Detection for Visually Impaired People
Author: Krishna Midula K
Affiliation: Dept. of Data Science, Amrita Vishwa Vidyapeetham
Date: 2025-12-02

## Project goal
Build a real-time, lightweight object detection system that detects key indoor/outdoor obstacles (doors, stairs, people, chairs, vehicles, curbs, small floor objects) and provides short, prioritized audio feedback for visually impaired users. Follow the first-review plan provided (document uploaded).

(Reference: Project review slides — System, Dataset and Methodology). :contentReference[oaicite:7]{index=7}

## Classes (primary)
- person
- stair
- door
- chair
- vehicle
- curb
- small_object

## Datasets
- Primary: IODR indoor dataset (doors, chairs, stairs, people). :contentReference[oaicite:8]{index=8}  
- Additional: selected MS-COCO classes for outdoor scenes (vehicle, curb examples). :contentReference[oaicite:9]{index=9}  
- Custom: manually collected 100–300 images for small and rare obstacles (floor items).

## High-level methodology
- Capture frames from webcam/phone.
- Apply basic preprocessing to handle lighting (adaptive adjustments).
- Train/fine-tune a lightweight YOLO-based detector (start with YOLOv8n).
- Optional: add simple tracking to stabilize detection across frames.
- Convert detections to short audio alerts using offline TTS (pyttsx3).
- Smart logic: per-class priority and cooldown to avoid repeated speech. :contentReference[oaicite:10]{index=10}

## Training & evaluation plan
- Environment: Google Colab GPU or local GPU.
- Augmentations: brightness shift, blur, cropping, — tuned per review suggestions. :contentReference[oaicite:11]{index=11}
- Metrics: mAP@0.5, mAP@[0.5:0.95], per-class AP, precision, recall; measure FPS (target >=10 FPS on laptop).
- Deliverables: trained model (best.pt), training logs/plots, demo video (30–90s), final PPT.

## Voice feedback
- Offline TTS using pyttsx3 or equivalent to avoid network delays.  
- Priority: person > vehicle > stairs > door > small_object.  
- Cooldown: configurable per-class cooldown to reduce spam (1.5–3.0s suggested). :contentReference[oaicite:12]{index=12}

## Next immediate tasks (for first week)
1. Obtain IODR dataset and sample COCO images for chosen classes.  
2. Create YOLO-compatible dataset structure: train/ val/ test + label files.  
3. Collect custom images for small objects (100–300).  
4. Smoke-check training environment (GPU access + ultralytics import).

## References
- Review slides (this project) — Krishna Midula K. :contentReference[oaicite:13]{index=13}
- (Additional references will be added to docs/ as needed.)
