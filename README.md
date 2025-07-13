# 🐾 Pet Detection System using YOLOv5

A comprehensive real-time pet detection system that uses YOLOv5 object detection to monitor pets and send notifications when they cross predefined boundary lines. Features include movement heatmap generation, customizable processing speeds, and multi-channel notifications (SMS/WhatsApp).

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Notifications](#notifications)
- [Output Files](#output-files)
- [Performance Optimization](#performance-optimization)
- [Technical Details](#technical-details)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## 🎯 Overview

The Pet Detection System leverages YOLOv5's powerful object detection capabilities to provide comprehensive pet monitoring with the following key features:

- **Real-time Detection**: Accurate detection of cats and dogs in video feeds
- **Line Crossing Alerts**: Configurable virtual boundaries with instant notifications
- **Movement Heatmaps**: Visual analysis of pet movement patterns
- **Multi-channel Notifications**: SMS and WhatsApp alerts via Twilio and PyWhatKit
- **Performance Optimization**: Configurable frame processing for speed vs accuracy balance
- **Comprehensive Statistics**: Detailed processing and detection analytics

## 🚀 Features

### Current Features
- ✅ **YOLOv5 Integration**: State-of-the-art object detection for pets
- ✅ **Smart Frame Processing**: Configurable frame skipping for optimal performance
- ✅ **Line Crossing Detection**: Customizable virtual boundaries
- ✅ **Real-time Notifications**: SMS via Twilio and WhatsApp via PyWhatKit
- ✅ **Movement Heatmaps**: Visual representation of pet activity patterns
- ✅ **Progress Tracking**: Real-time processing progress with ETA calculations
- ✅ **Comprehensive Statistics**: Detailed analytics and performance metrics
- ✅ **Flexible Input**: Support for various video formats (MP4, AVI, MOV, MKV)

### Advanced Capabilities
- 🎯 **Adaptive Processing**: Choose between accuracy (every frame) or speed (frame skipping)
- 📊 **Movement Analytics**: Track pet positions and generate heatmaps
- 🔔 **Smart Notifications**: Throttled alerts to prevent spam
- 📈 **Performance Metrics**: FPS tracking and processing time analysis
- 🎨 **Visual Feedback**: Real-time bounding boxes and confidence scores

## 🛠️ Installation

### Prerequisites
- Python 3.7 or higher
- OpenCV
- PyTorch
- Required Python packages (see requirements below)

### Dependencies Installation

```bash
# Core dependencies
pip install torch torchvision torchaudio
pip install opencv-python-headless
pip install pandas matplotlib seaborn
pip install moviepy

# Notification dependencies
pip install twilio          # For SMS notifications
pip install pywhatkit       # For WhatsApp notifications

# YOLOv5 setup (automatically handled by the script)
# The script will clone and set up YOLOv5 automatically
```

### Setup

1. **Download the script**
```bash
# Save the pet_detection.py file to your desired directory
```

2. **Prepare your video files**
```bash
# Place your video files in the same directory as the script
# Supported formats: MP4, AVI, MOV, MKV
```

3. **Configure notifications (optional)**
```bash
# For SMS: Set up Twilio account (credentials are hardcoded in the script)
# For WhatsApp: Ensure PyWhatKit is installed and working
```

## 📖 Usage

### Basic Usage

1. **Run the detection system**
```bash
python pet_detection.py
```

2. **Follow the interactive prompts**
   - Select your video file
   - Choose processing mode (every frame vs frame skipping)
   - Configure line crossing detection
   - Set up notifications (optional)

### Processing Modes

#### Maximum Accuracy Mode
- Processes every frame
- Highest detection accuracy
- Slower processing speed
- Best for critical monitoring

#### Speed Optimized Mode
- Processes every nth frame (configurable)
- Faster processing
- May miss some detections
- Good for general monitoring

### Configuration Options

#### Line Crossing Detection
- **Default**: Horizontal line at video center
- **Custom**: Define line coordinates as percentages
- **Format**: Start point (x1%, y1%) to end point (x2%, y2%)

#### Frame Processing
- **Frame Skip 1**: Process every frame (maximum accuracy)
- **Frame Skip 2-10**: Process every nth frame (faster)
- **Recommendation**: Use 2-3 for balanced performance

## 🔔 Notifications

### SMS Notifications (Twilio)
- **Pre-configured**: Twilio credentials are hardcoded
- **Setup**: Only requires your phone number
- **Format**: Include country code (+1234567890)
- **Rate Limiting**: Minimum 60 seconds between notifications

### WhatsApp Notifications (PyWhatKit)
- **Requirements**: PyWhatKit must be installed and working
- **Setup**: Requires phone number and WhatsApp Web access
- **Scheduling**: Automatically schedules messages
- **Rate Limiting**: Built-in throttling to prevent spam

## 📁 Output Files

The system generates several output files:

### 1. Processed Video
- **Filename**: `pet_detection_output.mp4`
- **Content**: Original video with detection overlays
- **Features**: Bounding boxes, confidence scores, frame counters

### 2. Movement Heatmap
- **Filename**: `pet_movement_heatmap.jpg`
- **Content**: Visual representation of pet movement patterns
- **Features**: Color-coded activity intensity, timestamps

### 3. Statistics Output
- **Format**: Console display and can be logged
- **Content**: Comprehensive processing and detection metrics

## ⚡ Performance Optimization

### Processing Speed Tips
1. **Frame Skipping**: Use frame skip 2-3 for 2-3x speed improvement
2. **Video Resolution**: Lower resolution videos process faster
3. **System Resources**: Ensure adequate RAM and CPU power
4. **GPU Support**: PyTorch will use GPU if available

### Accuracy vs Speed Balance
- **High Accuracy**: Frame skip = 1, processes every frame
- **Balanced**: Frame skip = 2-3, good speed with minimal accuracy loss
- **Fast Processing**: Frame skip = 5-10, fastest but may miss events

## 🔧 Technical Details

### Detection Classes
- **Cat**: COCO class index 15
- **Dog**: COCO class index 16
- **Confidence**: Adjustable threshold (default optimized)

### Line Crossing Algorithm
- **Method**: Geometric distance calculation
- **Threshold**: Configurable sensitivity
- **Tracking**: Center-bottom point of bounding box

### Heatmap Generation
- **Method**: Gaussian blur intensity mapping
- **Radius**: 20-pixel heat area per detection
- **Normalization**: Intensity scaled to 0-1 range
- **Visualization**: OpenCV COLORMAP_JET

## 📊 Statistics and Analytics

The system provides comprehensive statistics:

### Frame Processing
- Total frames in video
- Frames processed (with skip ratio)
- Processing time per frame
- Average FPS achieved

### Detection Metrics
- Frames with pets detected
- Separate counts for cats and dogs
- Pet detection rate percentage
- Line crossing events

### Performance Metrics
- Total processing time
- Average detection time
- Processing efficiency ratio
- Notification count

## 🐛 Troubleshooting

### Common Issues

#### Model Loading Errors
```bash
# If YOLOv5 fails to load, try:
git clone https://github.com/ultralytics/yolov5
pip install -r yolov5/requirements.txt
```

#### Video Processing Errors
```bash
# Check video file format and integrity
# Ensure OpenCV can read the file
```

#### Notification Failures
```bash
# SMS: Verify Twilio credentials and phone number format
# WhatsApp: Ensure PyWhatKit is properly installed
```

### Performance Issues
- **Slow Processing**: Increase frame skip value
- **High Memory Usage**: Process shorter video segments
- **Low Detection Rate**: Reduce frame skip value

## 🤝 Contributing

Contributions are welcome! Areas for improvement:

- Additional notification channels
- Advanced behavior analysis
- Multi-camera support
- Real-time webcam processing
- Mobile app integration
- Cloud deployment options

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- [Ultralytics YOLOv5](https://github.com/ultralytics/yolov5) for the object detection model
- [Twilio](https://www.twilio.com/) for SMS notification services
- [PyWhatKit](https://github.com/Ankit404butfound/PyWhatKit) for WhatsApp integration
- OpenCV community for computer vision tools

## 📞 Contact

For questions, issues, or contributions:
- **Email**: [katyalhunar921@gmail.com]
- **GitHub Issues**: For bug reports and feature requests

---

⭐ **Note**: This system is designed for educational and home monitoring purposes. Ensure compliance with local privacy laws when deploying in shared or public spaces.

Made with ❤️ for pet safety and smart home automation.
