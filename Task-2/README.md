# Task 2: Multi-Image Segmentation and Video Processing with YOLOv8

## Problem Statement

Implement segmentation on multiple images from a local folder, then extend to video processing by extracting frames, performing segmentation on each frame, and reconstructing the video with the segmented results.

## Implementation Approach

### Phase 1: Multi-Image Processing

#### 1. Dataset Preparation
- Downloaded sample images from a Kaggle dataset.
- Organized images in a dedicated `input/` directory for batch processing.
- Ensured diverse image content for comprehensive testing.

#### 2. Batch Object Detection
- Model Used: yolov8l.pt (Large variant for high accuracy)
- Process:
  - Initialized the YOLO model with pre-trained weights.
  - Set the source directory to `input/` for batch processing.
  - Enabled automatic saving to `detect/predict/` directory.
  - Extracted detection details including bounding boxes and confidence scores.
- Output: Detection results with bounding boxes saved to `detect/predict/`.

#### 3. Batch Instance Segmentation
- Model Used: yolov8l-seg.pt (Large segmentation variant)
- Process:
  - Loaded the segmentation model for pixel-level analysis.
  - Processed all images in the `input/` directory simultaneously.
  - Generated detailed segmentation masks and object boundaries.
  - Extracted comprehensive results including boxes, masks, and probabilities.
- Output: Segmented images with pixel-level masks saved to `segment/predict/`.

### Phase 2: Video Processing Pipeline

#### 4. Video Acquisition and Frame Extraction
- Source: Downloaded sample video using yt-dlp tool.
- Frame Extraction: Used FFmpeg for high-quality frame extraction.
  - Command: `ffmpeg -i video.mp4 -vf "fps=30,scale=1280:720" frames/frame_%04d.jpg`
  - Specifications: 30 FPS extraction rate, 720p resolution (1280x720).
  - Output: Sequential frames saved as `frame_0001.jpg`, `frame_0002.jpg`, etc.

#### 5. Video Frame Segmentation
- Process: Applied the yolov8l-seg model to all extracted video frames.
- Batch Processing: Segmented the entire frame sequence automatically.
- Quality: Maintained consistent segmentation quality across all frames.
- Output: Segmented frames saved in `segment/predict/` directory.

#### 6. Video Reconstruction
- Tool: FFmpeg for professional video encoding.
- Command: `ffmpeg -framerate 30 -i segment/predict/frame_%04d.jpg -c:v libx264 -pix_fmt yuv420p output_segmented_video.mp4`
- Specifications:
  - 30 FPS output matching the original frame rate.
  - H.264 encoding for optimal compatibility.
  - YUV420P pixel format for broad media player support.
- Output: Complete segmented video saved as `output_segmented_video.mp4`.

## Key Achievements

- Successfully implemented batch processing for multiple images.
- Demonstrated seamless transition from image processing to video processing.
- Integrated multiple tools (YOLOv8, FFmpeg, yt-dlp) in a unified workflow.
- Maintained video quality and frame rate consistency throughout the pipeline.
- Created an end-to-end automated video segmentation system.

## Technologies Utilized

| Technology         | Purpose                                        | Implementation                               |
|:------------------|:-----------------------------------------------|:----------------------------------------------|
| YOLOv8l / YOLOv8l-seg | Object detection and segmentation               | Batch processing of images and video frames   |
| FFmpeg             | Video processing and frame manipulation        | Frame extraction and video reconstruction     |
| yt-dlp             | Video acquisition                               | Download video content from online sources    |
| Ultralytics        | YOLO model interface                            | Python API for model loading and inference    |

## Learning Outcomes

- Mastered efficient batch processing of multiple images.
- Developed a complete video-to-video processing workflow.
- Successfully combined multiple specialized tools for complex tasks.
- Maintained consistent output quality across different media types.
- Created a scalable, automated solution for video content analysis.

## Status

Completed Successfully

This task demonstrated advanced computer vision capabilities by extending single-image processing to comprehensive video analysis, showcasing practical applications in video content understanding and automated media processing.
