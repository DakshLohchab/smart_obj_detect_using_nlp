Advanced Scene Detection System
This repository contains the Advanced Scene Detection System, a Python script designed for nuanced and accurate analysis of human activities within images. The system combines GroundingDINO for object detection and Google's Gemini model for contextual reasoning, offering robust scene detection with confidence scoring and rich visualizations.
Overview
The system leverages a hybrid approach to move beyond simple object labeling, understanding relationships between objects and people, verifying activities, and providing confidence scores. Key features include:

General-Purpose Scene Detection: Analyze any custom scene (e.g., "people shopping," "a group protesting").
Specialized Activity Modules: Optimized for complex activities like cooking and talking.
Multi-Layered Analysis: Includes element detection, contextual scoring, AI verification, and robust decision-making.
Rich Visualizations: Detailed outputs showing detected elements and primary activities.

Setup and Installation
Prerequisites

Python 3.8 or higher
pip (Python package manager)

Dependencies
Install the required Python libraries using pip:
pip install groundingdino-py google-generativeai pillow matplotlib opencv-python torch

Model Weights and Configuration
The system requires pre-trained model weights for GroundingDINO. Follow these steps to download and set them up:

Create necessary directories:
mkdir -p config weights


Download the configuration file:
wget -O config/GroundingDINO_SwinT_OGC.py https://raw.githubusercontent.com/IDEA-Research/GroundingDINO/main/groundingdino/config/GroundingDINO_SwinT_OGC.py


Download the model weights:
wget -O weights/groundingdino_swint_ogc.pth https://github.com/IDEA-Research/GroundingDINO/releases/download/v0.1.0-alpha/groundingdino_swint_ogc.pth



API Key Configuration
The system uses the Google Generative AI API for verification. Obtain an API key from the Google Cloud Console and configure it as follows:

Open the script (e.g., main.py).
Locate the configuration section and replace "YOUR_API_KEY_HERE" with your API key:# Configuration
API_KEY = "YOUR_API_KEY_HERE"  # <-- Replace with your key
genai.configure(api_key=API_KEY)


Note: Treat your API key as a password and do not expose it in public repositories.

Running the System

Ensure all dependencies and model weights are installed and configured.
Run the script with an image path and desired scene description:python main.py --image /path/to/image.jpg --scene "people walking in a busy street"



Usage
The system provides simple and advanced detection functions:

detect_scene(scene_description, image_path, confidence=0.6): Returns a boolean (True/False) for scene detection.
detect_scene_advanced(scene_description, image_path, confidence=0.6): Returns a detailed dictionary with confidence scores and analysis.

Example:
from main import detect_scene

image_file = "/path/to/image.jpg"
if detect_scene("people walking in a busy street", image_file):
    print("Scene detected!")

Contributing
Contributions are welcome! Please fork the repository and submit pull requests with improvements or bug fixes.
License
This project is licensed under the MIT License - see the LICENSE file for details.
