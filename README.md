VinDr-Mammo Lesion Detection with YOLO
Project Overview:
This project focuses on automatic lesion detection in mammography images using a YOLO-based object detection model. The goal is to detect clinically meaningful breast lesions from mammograms and localize them with bounding boxes. This study uses the VinDr-Mammo dataset and applies a deep learning object detection pipeline without any radiomics or genomic analysis. 


Why Mass and Calcification?
The VinDr-Mammo dataset contains several types of findings.
In this project, we intentionally focus on only two lesion types:
Mass
Calcification
Reasons for this choice:
These two findings are the most common and clinically important in breast cancer screening .They are well-defined in the annotations. They represent different visual challenges:
Mass: larger, shape-based lesions
Calcification: smaller, texture-based lesions
Focusing on these two classes reduces noise and makes the problem more interpretable. The objective is not to detect every possible abnormality, but to build a reliable and focused lesion detector.




Dataset
Dataset: VinDr-Mammo (PhysioNet)
Original size: ~20,000 mammography images
Selected images: 2,863
1,363 images with at least one Mass or Calcification
1,500 healthy (no finding) images
Final split:
Training images: 2,290
Validation images: 573
The split is study-based, ensuring that images from the same patient do not appear in both training and validation sets.




Preprocessing
DICOM to PNG conversion
Original images are in DICOM format
Converted to 8-bit PNG
Pixel intensity normalization applied
MONOCHROME1 images are inverted correctly
Image size:
All images resized to 640 × 640
This resolution is a standard and efficient input size for YOLO models




Annotation Strategy
Bounding box annotations are taken directly from finding_annotations.csv. all Mass and Calcification boxes are included. No manual annotation is performed
Class mapping:
0 → Mass
1 → Calcification
This all-box strategy allows the model to see: small lesions, large lesions, easy and difficult cases together




Model and Training
Model: YOLOv8m
Chosen as a balance between:
model capacity
training stability
GPU memory usage
Training settings:
Epochs: 120
Image size: 640
Batch size: 8

Optimizer and augmentation: YOLO default settings
GPU: Google Colab



Training Results
Best epoch:
Precision: 0.77
Recall: 0.23
mAP50: 0.24
mAP50–95: 0.13

Final epoch:
Precision: 0.81
Recall: 0.22
Loss values (final epoch):
Box loss: 1.64
Classification loss: 1.85
DFL loss: 1.54 




Interpretation of Results

The model shows:
High precision → detected lesions are usually correct
Lower recall → some lesions are intentionally missed
This indicates a conservative detection behavior.
Why recall is lower:
Calcifications are very small and low-contrast
Image resizing reduces fine details
The dataset contains many negative images
The model avoids false positives
This makes the model more suitable for reliable lesion localization rather than exhaustive screening.



Limitations
Calcifications are difficult to detect at 640×640 resolution
Class imbalance affects recall
No segmentation or pixel-level analysis is performed


Author
Melisa Ağrı
Molacular biology and genetics student
This project is developed as a learning-oriented research study.



  

