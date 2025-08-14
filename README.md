Robust Scene Detection using GroundingDINO and Gemini
This project provides an advanced, multi-layered pipeline for detecting complex scenes and human activities in images. It goes beyond simple object detection by combining the open-set detection capabilities of GroundingDINO with the powerful reasoning and verification abilities of Google's Gemini Pro model.

The system takes an image and a natural language query (e.g., "people having a conversation") and produces a robust, evidence-based conclusion on whether the scene is present, complete with detailed visualizations and analytics.

✨ Core Features
Multi-Stage Object Detection: Uses GroundingDINO with dynamically generated text prompts to find all objects relevant to a scene query.

Multi-Method AI Verification: Employs three distinct methods to verify the scene, reducing false positives:

Full Image Analysis: Gemini analyzes the entire image for context.

Focused Crop Analysis: Gemini analyzes a tight crop around detected objects for detail.

Pattern Analysis: A rule-based system checks the patterns of detected objects without an API call.

Spatial & Contextual Analysis: Analyzes the spatial relationships (e.g., proximity of people) between detected objects to infer activities.

Robust Decision Logic: Aggregates evidence from all stages using a weighted scoring system to make a final, confident decision.

Comprehensive Visualization: Generates rich, easy-to-understand outputs, including annotated images, analytics dashboards, and detailed text summaries.

Batch Processing: Includes a utility script to process multiple images against multiple queries automatically, saving all outputs to a specified folder.

⚙️ How It Works
The detection pipeline follows a systematic, evidence-gathering process:

Image Pre-processing: The input image is standardized, resized, and optimized for analysis.

Object Detection (GroundingDINO): Relevant objects are identified using a series of text prompts related to the main scene query. Detections are filtered for relevance and redundancy (IoU).

Evidence Verification (Gemini & Rule-Based): The initial findings are rigorously checked using the three verification methods described above.

Spatial Analysis: The positions and clustering of key objects (like people) are scored to add contextual evidence.

Final Decision (Weighted Scoring): A final confidence score is calculated by combining the weighted results from the detection, verification, and spatial analysis stages.

Report Generation: Visualizations and a text summary are generated and saved.

🛠️ Tech Stack & Models
Object Detection: GroundingDINO

LLM Verification & Reasoning: Google Gemini

Deep Learning Framework: PyTorch

Image Processing & Visualization: Matplotlib, Pillow, OpenCV

Numerical Operations: NumPy


