# Basketball Shot Analyzer

An AI-powered application that tracks, analyzes, and provides feedback on basketball shooting form using computer vision and machine learning.

## Project Overview

This project aims to create a comprehensive tool for basketball players and coaches to analyze shooting form and receive actionable feedback for improvement. By combining state-of-the-art object detection and pose estimation techniques, the system tracks both the basketball and the player's body movements throughout the shooting motion.

## Motivation

As both a basketball player and a data science enthusiast, I wanted to create a tool that bridges the gap between sports and technology. Professional athletes have access to advanced motion analysis systems, but these remain inaccessible to most amateur players. This project aims to democratize shot analysis technology by creating an accessible solution that provides personalized coaching feedback without requiring expensive equipment or professional trainers.

### Current Features
- Custom-trained YOLOv8 model for robust basketball detection across various lighting conditions and environments
  - Current model achieves >98% mAP@50 on validation data
  - Ongoing work to expand the training dataset for further improvements
- Data pipeline for video processing, frame extraction, and annotation
- Basketball tracking across video frames with temporal consistency using YOLOv8's integrated tracking capabilities

### Planned Features
- Advanced shooting form analysis using AlphaPose pose estimation
- Extraction of biomechanical metrics:
  - Joint angles throughout the shooting motion
  - Ball release point and timing
  - Player and ball velocity/acceleration profiles
- Machine learning analysis using Random Forest classifiers to identify optimal form characteristics
- AI-powered coaching feedback using an LLM
  - Natural language explanations of shot mechanics
  - Personalized coaching tips based on detected form issues
  - Progressive training recommendations
- Real-time feedback system for immediate form correction
- Performance metrics dashboard for tracking improvement over time
- Mobile application for easy recording and analysis

## Technical Details

### Data Processing Pipeline
1. Video acquisition and frame extraction
2. Manual annotation using CVAT for basketball detection dataset creation
3. Data augmentation and preprocessing
4. Object detection and pose estimation
5. Feature extraction from movement patterns
   - Joint angle calculations
   - Temporal derivatives for velocity and acceleration
   - Release point detection and analysis
6. Analysis using Random Forest models to classify effective shooting mechanics
7. LLM-enhanced feedback generation
   - Translation of technical metrics into actionable coaching advice
   - Natural language communication of findings to users
   - Contextual recommendations for improvement

### Models and Technologies
- **Object Detection**: Custom-trained YOLOv8 model for basketball tracking
  - Fine-tuned on basketball-specific dataset created with CVAT
  - Achieves >98% mAP@50 accuracy on current validation set
  - Uses YOLOv8's integrated BoTSORT tracker for consistent object tracking
- **Pose Estimation**: AlphaPose (planned implementation) for accurate human pose detection
- **Computer Vision**: OpenCV for video processing and visualization
- **Data Processing**: Python with NumPy, Pandas for data manipulation
- **Machine Learning**: Random Forest classifiers for initial shot form analysis
- **Natural Language Processing**: Integration with LLM APIs for generating human-like coaching feedback
- **Visualization**: Matplotlib and OpenCV for result visualization

## Project Structure
- `/basketball_dataset`: Dataset for YOLO model training
- `/input`: Input videos for analysis
- `/notebooks`: Jupyter notebooks for development and testing
  - Contains initial prototype (`V1_mediapipe_csrt.ipynb`) kept for reference only
- `/output`: Output videos with tracking and analysis
- `/src`: Source code for the main application
- `/train`: Training data for YOLO models
- `/training_results`: Model checkpoints and training metrics
- `/val`: Validation data for models

## Technical Evolution
The project has evolved through several iterations:
1. Initial prototype using MediaPipe and OpenCV's CSRT tracker (kept as reference only)
2. Current implementation with custom-trained YOLOv8 model for basketball detection
   - Achieved high accuracy (>98% mAP@50) with initial training data
   - Planning to expand the dataset for enhanced robustness in varied conditions
   - Using YOLOv8's built-in tracking capabilities rather than external tracking algorithms
3. Future implementation will integrate AlphaPose for more accurate pose estimation
4. Planned integration of biomechanical metrics (joint angles, release point, velocity, acceleration) 
5. Development of Random Forest models to analyze shooting form and provide actionable feedback
6. Integration with LLM APIs to transform technical analysis into natural coaching language

## Setup and Installation

*Detailed installation instructions will be added in a future update*

## Development Roadmap

1. ✅ Basketball object detection and tracking with YOLOv8
   - ✅ Initial model trained with >98% mAP@50 accuracy
   - 🔄 Expanding training dataset for improved generalization
2. 🔄 AlphaPose integration for pose estimation
3. 🔄 Shooting motion temporal analysis
   - 🔄 Joint angle calculation
   - 🔄 Velocity and acceleration profiling
   - 🔄 Release point detection
4. 🔄 Form analysis algorithm development
   - 🔄 Feature engineering from biomechanical metrics
   - 🔄 Random Forest model for shot form classification
5. 🔄 Feedback system implementation
   - 🔄 LLM API integration for natural language coaching
   - 🔄 Conversion of technical metrics to actionable advice
6. 🔄 User interface development
7. 🔄 Mobile application development

## Skills Demonstrated

This project demonstrates proficiency in several key data science and machine learning areas:

- **Computer Vision**: Object detection, tracking, and pose estimation
- **Machine Learning**: Model training, evaluation, and hyperparameter tuning
- **Feature Engineering**: Extracting meaningful features from time-series motion data
- **Data Processing**: Creating pipelines for video processing and analysis
- **AI Integration**: Combining multiple AI systems (computer vision, ML classification, LLMs)
- **Software Development**: Creating modular and maintainable code architecture
- **Technical Problem Solving**: Addressing challenges in real-time tracking and analysis

## Acknowledgements
- The YOLO object detection system by Ultralytics
- AlphaPose for advanced human pose estimation
- Computer Vision Annotation Tool (CVAT) for dataset creation

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

luke.c.hakso@gmail.com
