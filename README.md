# nudity-detection# Nudity Detection

## Overview

Nudity detection is the process of analyzing an image or video to identify and classify explicit content, specifically nudity. This project uses **NudeNet**, a deep learning-based nudity detection model, to identify various types of nudity in images and videos. The model detects specific labels like **BUTTOCKS_EXPOSED**, **FEMALE_BREAST_EXPOSED**, **FEMALE_GENITALIA_EXPOSED**, and more. It can be used in applications requiring content moderation, parental control, or safe content filtering.

## Features

- **Detects Various Types of Nudity**: Identify different categories of nudity including exposed body parts like breasts, genitals, buttocks, and more.
- **Confidence Scoring**: Each detected nudity class is associated with a confidence score, which allows fine-tuning of detection thresholds.
- **Image and Video Support**: The model works for both images and videos, processing each frame to detect nudity.
- **Customizable Criteria**: Set thresholds for detection to suit specific needs, such as detecting nudity only if the confidence score exceeds a certain value.
- **Parallel Processing for Video**: Use worker threads for multi-threaded video processing to analyze multiple frames concurrently for performance improvements.

## Use Cases

- **Content Moderation**: Automatically filter out explicit content in social media platforms, chat applications, or any environment that involves user-uploaded media.
- **Parental Control**: Scan and filter images and videos for inappropriate content before displaying them to users.
- **Safe Search**: Implement safe search filters in search engines or media platforms.

## Technical Details

This project uses **NudeNet**, a pre-trained model for nudity detection, which provides a high accuracy in detecting exposed and covered body parts. The model works by analyzing images or video frames and returning results as classes with confidence scores.

- **Supported Classes**:
  - `BUTTOCKS_EXPOSED`
  - `FEMALE_BREAST_EXPOSED`
  - `FEMALE_GENITALIA_EXPOSED`
  - `MALE_BREAST_EXPOSED`
  - `ANUS_EXPOSED`
  - `MALE_GENITALIA_EXPOSED`
  - And more...

## How It Works

### Image Detection:
1. **Input Image**: A single image file is provided for nudity analysis.
2. **Nudity Detection**: The image is processed through the NudeNet model to identify whether any nudity exists, checking for specific labels (e.g., `FEMALE_BREAST_EXPOSED`).
3. **Confidence Thresholds**: Each class detected is given a confidence score, which can be customized (e.g., only consider a class detected if the confidence score is above 0.5).
4. **Results**: The detection results are returned, and the system decides whether specific nudity is present based on the labels and confidence.

### Video Detection:
1. **Input Video**: A video file is provided for frame-by-frame analysis.
2. **Frame Processing**: Each frame of the video is processed individually to detect nudity.
3. **Parallel Processing**: Optionally, worker threads can be used to process multiple frames in parallel for faster performance.
4. **Detection in Frames**: The same confidence scoring is applied to detect nudity in each frame.
5. **Output**: If nudity is detected in any frame, the process can stop early or continue depending on the configuration.

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/AyemunHossain/nudity-detection/
   cd nudity-detection
    ```
2. **Pyhon dependency install **:
  ```
      pip install -r requirements.txt
  ```
3. Add you image/video path
4. Run image.py or video.py
