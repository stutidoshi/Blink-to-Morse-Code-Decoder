# Blink-to-Morse-Code-Decoder

A computer vision project that translates eye blinks into Morse code using Python, OpenCV, and MediaPipe.

## Overview

This project explores an alternative way to communicate using eye movements. It detects eye closures from a webcam feed or a prerecorded video and interprets their duration as Morse code dots and dashes. The decoded symbols are then mapped to letters and numbers.

## Features

- **Eye landmark detection:** Uses MediaPipe Face Landmarker to identify facial landmarks around the eyes.
- **Blink duration analysis:** Classifies eye closures into Morse code dots and dashes based on configurable time thresholds.
- **Morse code decoding:** Converts recognized sequences into letters and numbers.
- **Letter and word separation:** Uses intervals with eyes open to identify gaps between characters and words.
- **Webcam processing:** Supports live camera-based blink detection.
- **Video processing:** Includes a prerecorded-video implementation with options for previewing and saving annotated output.
- **Interactive controls:** Supports actions such as resetting the decoded text and deleting the last character where implemented.

## Tech Stack

- Python
- OpenCV
- MediaPipe
- NumPy
- Jupyter Notebook

## How It Works

1. Capture frames from a webcam or prerecorded video.
2. Detect facial landmarks using MediaPipe.
3. Analyze eye landmarks to estimate whether the eyes are open or closed.
4. Measure eye-closure duration to classify blinks as dots or dashes.
5. Identify letter and word boundaries using eye-open intervals.
6. Decode the Morse sequence into readable text.

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/Blink-to-Morse-Code-Decoder.git
cd Blink-to-Morse-Code-Decoder
```

Install the dependencies:

```bash
pip install mediapipe opencv-python numpy
```

Open `MorseCode.ipynb` in Jupyter Notebook or Google Colab, where supported, and run the cells in order.

The project may download the MediaPipe face landmark model automatically. An internet connection is required for the initial download unless the model file is already available locally.

## Morse Code Timing

The current implementation uses the following timing rules:

| Input | Interpretation |
|---|---|
| Eyes closed for 0.5 to less than 3 seconds | Dot (`.`) |
| Eyes closed for 3 seconds or longer | Dash (`-`) |
| Eyes open for 3 seconds | Letter gap |
| Eyes open for 6 seconds | Word space |

These are the project's current thresholds and may need adjustment depending on the user, camera conditions, and recording frame rate.

## Project Structure

```text
Blink-to-Morse-Code-Decoder/
├── MorseCode.ipynb
├── README.md
├── requirements.txt
├── .gitignore
└── LICENSE
```

## Limitations

- Accuracy may vary with lighting, camera quality, head position, and landmark detection.
- Long-duration blink gestures may be tiring and can be difficult to distinguish consistently.
- Timing thresholds may require calibration for different users.
- This is an experimental communication prototype and is not intended to replace validated assistive communication devices.

## Future Improvements

- Add a graphical user interface for easier interaction.
- Allow users to customize blink-duration thresholds.
- Improve detection robustness and reduce accidental inputs.
- Add speech output for decoded text.
- Evaluate decoding accuracy across different users and lighting conditions.

## Acknowledgements

Built with Python, OpenCV, and MediaPipe.

