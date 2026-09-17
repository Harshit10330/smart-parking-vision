# Smart Parking Vision



A computer vision project that detects parking spaces and classifies them as empty or occupied using YOLO and the PKLot dataset.



## Project Overview



Smart Parking Vision uses a YOLO object detection model to identify parking spaces in parking-lot images.



The system:



- Detects parking spaces.

- Classifies each detected space as `space-empty` or `space-occupied`.

- Calculates total parking spaces.

- Calculates empty and occupied spaces.

- Calculates parking occupancy percentage.

- Produces an annotated output image.



## Dataset



The project uses the PKLot dataset in YOLO format.



Dataset classes:



- `0` - `space-empty`

- `1` - `space-occupied`



Dataset split:



- Training images: 8,691

- Validation images: 2,483

- Test images: 1,242



## Model



The project uses YOLO11n through Ultralytics.



The trained model is saved locally as:



`runs/detect/runs/smart\_parking/weights/best.pt`



The trained model is intentionally excluded from the GitHub repository because model files are large.



## Validation Results



Validation was performed on 2,483 images.



| Metric | Result |

|---|---:|

| Precision | 0.961 |

| Recall | 0.972 |

| mAP@50 | 0.980 |

| mAP@50-95 | 0.773 |



Class-wise validation results:



| Class | Precision | Recall | mAP@50 | mAP@50-95 |

|---|---:|---:|---:|---:|

| space-empty | 0.973 | 0.947 | 0.976 | 0.776 |

| space-occupied | 0.950 | 0.997 | 0.985 | 0.769 |



These values are measurements from the validation run and should not be interpreted as guaranteed real-world performance.



## Project Structure



smart-parking-vision/

├── config/

│   ├── config.yaml

│   └── parking\_slots.json

├── data/

│   ├── input/

│   └── pklot\_dataset/

├── docs/

│   ├── README.md

│   └── statement.md

├── models/

├── outputs/

├── src/

│   ├── \_\_init\_\_.py

│   ├── detector.py

│   ├── main.py

│   └── parking.py

├── tests/

│   └── test\_parking.py

├── .gitignore

├── README.md

└── requirements.txt



## Installation



Install the required Python packages:



pip install -r requirements.txt



## Usage



Run the parking detection application with an image:



python .\\src\\main.py --image ".\\data\\pklot\_dataset\\test\\images\\2013-04-16\_10\_20\_04\_jpg.rf.cf2eeba0fef298a616a157669246fabe.jpg"



You can also specify a custom model:



python .\\src\\main.py --image ".\\path\\to\\parking\_image.jpg" --model ".\\path\\to\\best.pt"



The application prints a parking summary similar to:



Smart Parking Vision

--------------------

Total spaces: 43

Empty spaces: 1

Occupied spaces: 42

Occupancy: 97.67%

Output saved to: outputs\\parking\_result.jpg



The annotated result is saved to:



outputs/parking\_result.jpg



## Testing



Run the automated tests with:



pytest



The project contains tests covering:



- Empty parking summary

- Full parking summary

- Mixed parking summary

- YOLO detection summary conversion



Expected result:



4 passed



## Example Result



For one test image, the system detected:



- Total spaces: 43

- Empty spaces: 1

- Occupied spaces: 42

- Occupancy: 97.67%



An annotated image was generated in the outputs directory.



## Technologies



- Python 3.12

- OpenCV

- NumPy

- Pandas

- Matplotlib

- Ultralytics YOLO

- PyYAML

- Pytest



## Model Evaluation



The trained YOLO model was evaluated using the validation split provided by the dataset.



The evaluation produced:



- Precision: 0.961

- Recall: 0.972

- mAP@50: 0.980

- mAP@50-95: 0.773



The model was also tested on all 1,242 images in the test directory for prediction generation.



## Dataset Attribution



The PKLot dataset version used for this project was obtained in YOLO format from Roboflow. The dataset metadata identifies the dataset license as CC BY 4.0.



Dataset source:



https://universe.roboflow.com/brad-dwyer/pklot-1tros/dataset/2



## Limitations



The current system operates on parking-lot images and relies on object detection to identify parking spaces.



Performance can vary with:



- Different camera viewpoints

- Lighting conditions

- Occlusions

- Image quality

- Parking-lot layouts that differ from the training data



The reported validation metrics are specific to the dataset split used during evaluation.



## Future Improvements



Possible future improvements include:



- Real-time camera/video processing

- Parking-space tracking across video frames

- Automatic parking-slot mapping

- Web-based dashboard

- Historical occupancy statistics

- Multiple camera support

- Deployment on edge devices



## License



This project was developed for educational purposes as a computer vision project.



The dataset remains subject to its original license and attribution requirements.


