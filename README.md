# Object Detection using Pretrained YOLOv8 on VisDrone Dataset

## Project Overview

This project demonstrates object detection using the **YOLOv8 (You Only Look Once)** pretrained model on the **VisDrone 2019 Dataset**. The implementation was carried out entirely in a Kaggle Notebook using the Ultralytics YOLO framework.

The model detects various objects such as pedestrians, cars, buses, trucks, bicycles, motorcycles, and more from aerial images captured by drones.

---

## Dataset

**Dataset Name:** VisDrone 2019 Detection Dataset

**Source:** Kaggle

The dataset contains:

- Training Images
- Validation Images
- Test Images
- YOLO formatted annotations
- Configuration file (`visdrone.yaml`)

### Object Classes

| Class ID | Object |
|----------|---------|
| 0 | Pedestrian |
| 1 | People |
| 2 | Bicycle |
| 3 | Car |
| 4 | Van |
| 5 | Truck |
| 6 | Tricycle |
| 7 | Awning-Tricycle |
| 8 | Bus |
| 9 | Motorcycle |

---

## Technologies Used

- Python
- Kaggle Notebook
- Ultralytics YOLOv8
---

## Project Workflow

1. Install Ultralytics YOLO.
2. Import required libraries.
3. Load the pretrained YOLOv8 model.
4. Load the VisDrone dataset.
5. Configure the dataset using the YAML file.
6. Perform object detection.
7. Save prediction results.
8. Evaluate the model.

---

## Installation

Install the required package:

```python
!pip install ultralytics
```

---

## Import Libraries

```python
from ultralytics import YOLO
import os
import glob
```

---

## Load Pretrained Model

```python
model = YOLO("yolov8n.pt")
```

---

## Perform Object Detection

```python
results = model.predict(
    source="/kaggle/input/datasets/banuprasadb/visdrone-dataset/VisDrone_Dataset/VisDrone2019-DET-val/images",
    save=True,
    conf=0.25
)
```

---

## Output

The predicted images are saved automatically in:

```
/kaggle/working/runs/detect/predict-2
```

Each image contains bounding boxes with:

- Object Class
- Confidence Score

---

## Sample Output

Example detection:

```
Image: 0000364_01765_d_0000782.jpg

Detected Objects:
- Person (3)
- Car (4)
- Truck (1)
```

---

## Model Used

- **Model:** YOLOv8 Nano (`yolov8n.pt`)
- **Framework:** Ultralytics YOLO
- **Task:** Object Detection

---

## Results

The pretrained YOLOv8 model successfully detected multiple object categories from aerial drone images.

Example detections include:

- Pedestrians
- Cars
- Vans
- Trucks
- Motorcycles
- Buses
- Bicycles

Prediction results were generated for all validation images and saved successfully.

---

## Project Structure

```
Object-Detection-Using-YOLOv8/
│
├── README.md
├── Object_Detection.ipynb
├── visdrone_fixed.yaml
├── runs/
│   └── detect/
│       ├── predict/
│       ├── predict-2/
│       └── train/
└── yolov8n.pt
```

---

## Future Improvements

- Fine-tune YOLOv8 on the VisDrone dataset.
- Compare YOLOv8n with YOLOv8s and YOLOv8m.
- Deploy the model using Streamlit or Flask.
- Perform real-time object detection on videos.
- Improve detection accuracy through data augmentation.

---

## Conclusion

This project demonstrates how a pretrained YOLOv8 model can be used for efficient object detection on aerial imagery. The implementation highlights the ease of using the Ultralytics framework within a Kaggle environment to perform accurate and fast object detection without training a model from scratch.

---

## Author

**Nandini Tekuri**

B.Tech Student

Artificial Intelligence & Machine Learning

---

## License

This project is intended for educational and research purposes.
