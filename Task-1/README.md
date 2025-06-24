# YOLOv8 Object Detection and Instance Segmentation

## Problem Statement

For a GNU/Linux-based setup (adapted to Windows 11), implement object detection and instance segmentation using YOLOv8 via the Ultralytics package.

## Environment Setup

- Operating System: Windows 11  
- IDE: Visual Studio Code  
- Python Version: 3.12.3  
- Framework: YOLOv8 via Ultralytics Python package  

## Implementation Approach

### Virtual Environment Creation

Created an isolated Python environment in VS Code to manage project dependencies without affecting the global Python installation.

### Package Installation

Installed the required ultralytics package using pip.

## Object Detection Implementation

- Model Used: yolov8l.pt (Large variant for high accuracy)
- Process:
  - Loaded the pre-trained detection model.
  - Performed inference on a test image.
- Results: Detected objects with bounding boxes, class labels, and confidence scores.

## Instance Segmentation Implementation

- Model Used: yolov8l-seg.pt (Large segmentation variant)
- Process:
  - Applied the segmentation model to the same test image.
- Results: Generated precise pixel-level object masks and boundaries.

## Key Achievements

- Successfully set up a YOLOv8 development environment.
- Demonstrated both detection and segmentation on the same image.
- Verified model performance on real-world image data.
- Gained hands-on experience with the Ultralytics framework and YOLOv8 architecture.

## Technologies Utilized

| Technology          | Purpose                                                      |
|:--------------------|:-------------------------------------------------------------|
| YOLOv8               | State-of-the-art object detection and segmentation framework |
| Ultralytics          | Python package providing YOLOv8 implementation               |
| Visual Studio Code   | Development environment with Python extension support        |

## Learning Outcomes

- Understood computer vision model deployment workflows.
- Gained experience with pre-trained model inference and result interpretation.
- Developed knowledge of YOLOv8 model variants and their specific use cases.

## Resources

- [Ultralytics YOLOv8 Documentation](https://docs.ultralytics.com/)
