# Sample Data

A small representative sample (13 images) from the labeled facade-defect dataset used to train Dobby's crack-detection model [Real dataset ~5,700-image].

- `images/` — sample facade photos
- `labels/` — corresponding YOLO-format bounding-box labels (one `.txt` per image, one line per defect instance: `class_id x_center y_center width height`, normalized 0-1)
- `classes.yaml` — class list and dataset metadata for this export

Selected to span all 5 labeled defect classes (Crack, Efflorescence, Rebar, Rust, Spall) where possible, including cases with multiple defects per image.

Full dataset: hosted on Roboflow