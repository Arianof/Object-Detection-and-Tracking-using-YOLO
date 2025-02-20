# Object Detection and Tracking
## Overview
This project implements object detection and tracking using YOLOv8 and BoT-SORT/ByteTrack algorithms. The pipeline is designed for processing videos, detecting multiple objects, and tracking them efficiently. It includes preprocessing, hyperparameter tuning, and real-time object tracking. The implementation is done in Python using OpenCV and Ultralytics YOLO.
## Features
- **YOLOv8-based Object Detection**: Utilizes the latest Ultralytics YOLO model for high-accuracy object detection.
- **Multi-Object Tracking**: Supports BoT-SORT and ByteTrack tracking algorithms.

- **Customizable Parameters**: Users can configure tracking thresholds, object IDs, and motion compensation settings.

- **Image Enhancements**: Includes blurring techniques for improving detection performance.

- **Automated Video Processing**: Reads input video, applies detection/tracking, and saves the processed output video.

- **Kalman Filter Adjustments:** Provides an option to modify Kalman filter parameters for tracking stability.

## Installation
To use this project, install the required dependencies using the following commands:
```
pip install ultralytics scikit-learn opencv-python
```

## Usage
Run the main pipeline to process videos automatically:
```
task_pipeline()
```

## Configuration
The tracking pipeline uses configurable YAML files for BoT-SORT and ByteTrack. These files define hyperparameters such as confidence thresholds, tracking buffers, and motion compensation settings.
### Sample BoT-SORT Configuration
```
tracker_type: botsort
track_high_thresh: 0.6
track_low_thresh: 0.3
new_track_thresh: 0.85
track_buffer: 100
match_thresh: 0.6
fuse_score: True
min_box_area: 10
gmc_method: sparseOptFlow
proximity_thresh: 0.6
appearance_thresh: 0.6
with_reid: True
```

### Sample ByteTrack Configuration
```
tracker_type: bytetrack
track_high_thresh: 0.35
track_low_thresh: 0.025
new_track_thresh: 0.8
track_buffer: 300
match_thresh: 0.8
fuse_score: True
min_box_area: 1
```

## Object Detection and Tracking Workflow
1. **Load and preprocess video**: Reads input video and applies preprocessing like blurring.
2. **Configure tracking algorithm**: Sets up BoT-SORT or ByteTrack based on user selection.
3. **Run YOLOv8 detection**: Detects objects in each frame of the video.
4. **Apply tracking**: Assigns unique IDs to detected objects and tracks their movement.
5. **Draw bounding boxes**: Customizes bounding boxes with object IDs.
6. **Save and export video**: Writes processed frames to an output video file.

## Dependencies
- Python 3.x
- Ultralytics YOLOv8
- OpenCV
- scikit-learn

## Output
The processed video will be saved in the specified output directory, and can be downloaded directly.
