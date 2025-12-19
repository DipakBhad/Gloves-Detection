🧤 Gloved vs Ungloved Hand Detection

Safety Compliance System

📂 Dataset

Dataset Name: Hand Glove Detection Dataset

Source: Roboflow

Classes:

gloved_hand

bare_hand

The dataset contains images captured in industrial and lab-like environments with variations in lighting, background, hand pose, and glove color.

🤖 Model Used

Model Architecture: YOLOv8 (Ultralytics)

Base Model: yolov8n.pt (pretrained on COCO)

Task Type: Object Detection

YOLOv8 was chosen due to its real-time performance, high accuracy, and easy deployment.

🛠 Preprocessing & Training
Preprocessing

Images resized to 640 × 640

Bounding box annotations in YOLO format

Automatic augmentations applied by YOLOv8:

Horizontal flip

Scaling

Color jitter

Training

Epochs: 15

Batch Size: 8

Optimizer: Default YOLOv8 optimizer

Hardware: CPU

Performance Metrics

Precision: ~85.5%

Recall: ~71.9%

mAP@50: ~81.3%

mAP@50–95: ~48.9%

Inference Speed: ~25 ms per image (CPU)

✅ What Worked Well

Model accurately detects gloved hands in most lighting conditions

Good precision, meaning few false positives

Real-time inference possible even on CPU

YOLOv8 handled small objects (hands) reasonably well

🚀 How to Run the Script
Requirements
pip install ultralytics opencv-python

Steps

Open detection_script.ipynb

Set the input image folder path

Run all cells

Outputs will be saved to:

output/ → annotated images

logs/ → JSON detection results

📌 Output Format

Each image generates:

An annotated image with bounding boxes

A JSON file containing:

Class name

Confidence score

Bounding box coordinates

🔮 Future Improvements

Increase dataset size

Train for more epochs

Use a larger YOLOv8 model (yolov8s/m)

Add video stream detection support