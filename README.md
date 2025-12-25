# vindr-radiogenomic-lesion-detection

VinDr Radiogenomic Lesion Detection:

Project Overview
This project focuses on automic lesion detection in mammography images and radiogenomic feature analysis. The main goal is not only to detect breast lesions using deep learning, but also to extract biological information from detected regions.
This studt uses the VinDr-Mammo dataset and combines:
Computer Vision(YOLO- basedd detection)
Medical image preprocessing
Radiomics feature extraction
Biological interpretation from a Molecular biology anf gebetics perspective.

Motivation:
Breast cancer lesions in mammography images can be:
 Very Small(especially calcifications),
 Hard to distinguish from dense breast tissue
Most deep learning studies stop after detection.
In this project, detection is used as a tool, ot the final goal.
Detected lesion regions are treated as a digital biopsy, and quantitative tissue features are extracted to better understand:
 Tissue heterogeneity
 lession complexity
 Possible links to tumor microenvironment activity

Project Pipeline:
This project is divided into five main stages:
1.Sampling: 
  Smart selection of image from the Vindr_Mammo dataset
  Focuses on mass and calcification cases
  Balanced inclusion of healthy images to reduce class imbalance 
2.Preprocessinng
 Conversion of DICOM images to PNG format
 İmage normalization of resizing
 Conversion of bounding box annotations to YOLO format
3.Dataset Sanity Check
 Class distribution analysis
 Visiual inspection of bounding boxes
 Validation  of label correctness before training
4.Lesion Detection
 Training a YOLO-based object detection model
 Detection of lesion regions in mammography iamges
5.Radiogenomic Analysis
 Extraction of radiomics features from detected lesion regions
 Analysis of texture , entropy, and  shape features
 Biological interpretaion of tissue heterogeneity

Tools an Libraries
Python
PyDICOM
OpenCV
YOLO(ultralytics)
PyRadiomics
NumPy,Pandasi Matplotlib

Scientific contribution
This project goes beyond standard object detection by:
 Using deep learning as a region proposal method
 Extracting quantitive tissue features from detected lesions
 Connecting imaging features with biological meaning
The approach aims to bridge medical imaging and molecular biology, supporting radiogenomic research.

Author
Melisa Ağrı
Molacular biology and genetics student
This project is developed as a learning-oriented research study.



  

