# Road Traffic Vehicle Detection using Background Subtraction (MATLAB)

This project implements a complete classical computer vision pipeline for detecting moving vehicles in traffic footage using background subtraction, morphological operations, and connected-component analysis. The system processes a raw video, extracts the foreground, segments valid vehicle regions, and generates a detection video with bounding boxes and frame-wise statistics.

This project was completed as part of the Image Processing for Engineering and Science course by MathWorks (Coursera).

## Features

- Median filtering for noise reduction
- Grayscale conversion and intensity normalization
- Static background modeling
- Absolute frame differencing
- Morphological cleanup: closing, opening, hole filling
- Region filtering using bwpropfilt
- Bounding box generation over detected vehicles
- Frame-level metrics:
    - Number of regions
    - Mean region area
    - Total region area
- Extraction of metrics for a target frame (e.g., Frame 152)

## Pipeline Overview

### Video Enhancement
- Apply median filters to remove salt-and-pepper noise
- Convert each frame to grayscale
- Export a noise-reduced version of the video

### Background Subtraction
- Read the first frame as the reference background
- Compute foreground by absolute difference

### Segmentation
- Thresholding
- Morphological closing and opening
- Hole filling
- Region filtering based on area

### Region Properties
- Compute area and bounding boxes using regionprops
- Store metrics for each frame
- Render detection results into an output video

## File Structure

```
├── RoadTraffic.mp4                # Input video  
├── RoadTrafficFiltered.mp4        # Noise-reduced intermediate output
├── CarDetection.mp4               # Final detection video with bounding boxes
├── vehicle_detection.m            # Main MATLAB script
└── README.md
```

## Results

- Noise-reduced preprocessed video
- Foreground vehicle masks
- Bounding box detection video
- Quantitative region metrics across all frames
- Detailed region analysis for Frame 152

## Dependencies

- MATLAB R2022a or later
- Image Processing Toolbox
- Video Processing Toolbox

## Future Improvements

- Adaptive background modeling (Mixture of Gaussians)
- Shadow suppression
- Motion tracking using centroids
- Frame-to-frame consistency filtering
- Reduced reliance on large morphological operators
