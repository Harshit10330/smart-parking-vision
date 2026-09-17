\# Smart Parking Vision



A computer vision project that detects parking spaces and classifies them as empty or occupied using YOLO and the PKLot dataset.



\## Project Overview



Smart Parking Vision uses a YOLO object detection model to identify parking spaces in parking-lot images.



The system:



\- Detects parking spaces.

\- Classifies each detected space as `space-empty` or `space-occupied`.

\- Calculates total parking spaces.

\- Calculates empty and occupied spaces.

\- Calculates parking occupancy percentage.

\- Produces an annotated output image.



\## Dataset



The project uses the PKLot dataset in YOLO format.



Dataset classes:



\- `0` - `space-empty`

\- `1` - `space-occupied`



Dataset split:



\- Training images: 8,691

\- Validation images: 2,483

\- Test images: 1,242



\## Model



The project uses YOLO11n through Ultralytics.



The trained model is saved as:



```text

runs/detect/runs/smart\_parking/weights/best.pt

