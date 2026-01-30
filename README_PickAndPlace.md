# Interactive Pick and Place with Computer Vision

A vision-guided robotic system for automated object sorting using the AUBO-i5 collaborative robot. This project was developed as part of ME192 Robotics at San Jose State University.

## Overview

This system detects circular objects in real-time using a USB camera, calculates their position in robot coordinates, and communicates the location data to the robot controller for pick-and-place operations. Objects are selectively handled based on size criteria, simulating a warehouse sorting application.

## How It Works

1. Camera captures live video feed
2. Hough Circle Transform detects circular objects
3. Pixel coordinates are converted to millimeters using a calibration factor
4. Object positions (x, y, z) are tracked across frames for stability
5. Stable object locations are sent to the robot controller
6. Robot picks objects matching size criteria and places them in designated location

## Features

- Real-time circle detection using OpenCV
- Pixel-to-millimeter coordinate transformation
- Object tracking with persistent ID assignment
- Stability checking to avoid false detections
- Size-based filtering (configurable diameter range)
- Visual feedback with annotated video output

## Hardware Setup

- AUBO-i5 collaborative robot
- USB webcam mounted above workspace
- Custom suction-based end effector
- Checkerboard pattern for camera calibration

## Dependencies

```
opencv-python
numpy
```

## Usage

```python
python image_detection.py
```

Press 'q' to quit the detection loop.

## Configuration

Key parameters in the code:

- `mm_per_pixel`: Calibration factor for your camera setup
- `min_radius_pixels` / `max_radius_pixels`: Size filter for target objects
- `SERVER_HOST` / `SERVER_PORT`: Robot controller network settings

## Project Context

This was a team project focused on integrating perception, control, and mechanical design into a functional robotic system. My contributions included developing the vision detection pipeline, designing the end effector, and programming the motion planning.

## Author
Bhavagnya Vegunta
Ichiro Sone
Harreynish Gowtham Sarav
San Jose State University
November 2024
