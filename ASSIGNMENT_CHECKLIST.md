# Assignment Checklist (inferred)

Note: I couldn't find the official assignment text in the workspace. This checklist is inferred from the notebook and the data (MPII) and maps likely deliverables to current implementation status.

- YOLO MPS compatibility: implemented (patched detector to be device-agnostic)
- HRNet inference on detected people: implemented (SimpleHRNet wrapper used)
- MPII joint order & skeleton mapping: fixed in notebook (uses dataset joint_names and skeleton)
- Multi-person plotting: implemented in notebook (plots all detected people)
- Full-dataset evaluation pipeline: added and runnable via `scripts/run_analysis.py` (saves results/plots)
- Saved outputs: script writes `results/per_image.csv`, `results/analysis_summary.json`, and PNGs
- Repro instructions: included below under "Run"
- Formal written report / assignment PDF: NOT FOUND / NOT GENERATED (I can generate a short report if you want)

Run
---
1. Activate your venv and ensure dependencies (`torch`, `opencv-python`, `matplotlib`, `numpy`) are installed.
2. From repo root run:

```
python scripts/run_analysis.py --annotations data/mpii_val_annotations.json --images data/images --output results
```

This will run detection + HRNet over the annotations and save results into `results/`.

If you provide the official assignment file (path or paste), I will produce a precise item-by-item mapping and implement any missing deliverables.
