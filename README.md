# 🐾 Pet Monitoring System using YOLOv8

A real-time pet monitoring system that uses YOLOv8 object detection to track pets and send alerts when they cross predefined boundary lines. Perfect for home safety, keeping pets away from restricted areas, or monitoring their activity indoors.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Demo](#demo)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [How It Works](#how-it-works)
- [Development Status](#development-status)
- [Use Cases](#use-cases)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [Team](#team)
- [License](#license)

## 🎯 Overview

The Pet Monitoring System is designed to provide real-time surveillance of pets using computer vision. By leveraging YOLOv8's powerful object detection capabilities, the system can detect pets in video feeds and trigger alerts when they cross user-defined virtual boundaries.

### Key Capabilities
- ✅ Real-time pet detection and tracking
- ✅ Virtual boundary line crossing detection
- ✅ Instant alert notifications
- ✅ Modular and extensible architecture
- ✅ Support for webcam and video file input

## 🚀 Features

### Current Features
- **Real-time Detection**: Uses YOLOv8 for accurate pet detection in live video streams
- **Boundary Monitoring**: Configurable virtual lines to monitor restricted areas
- **Alert System**: Immediate notifications when pets cross predefined boundaries
- **Multi-pet Support**: Can track multiple pets simultaneously
- **Flexible Input**: Works with webcam feeds or pre-recorded videos

### Planned Features
- 🌙 Low-light condition optimization
- 📈 Advanced behavior analysis
- 🎥 Multi-camera integration
- 📱 Mobile app notifications
- 🔊 Audio alert system
- 📊 Activity dashboard

## 🛠️ Installation

### Prerequisites
- Python 3.8 or higher
- OpenCV
- YOLOv8 (Ultralytics)
- NumPy

### Setup

1. **Clone the repository**
```bash
git clone https://github.com/hunarkatyak/pet-monitoring-system.git
cd pet-monitoring-system
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Download YOLOv8 weights**
```bash
# The system will automatically download YOLOv8 weights on first run
# Or manually download from Ultralytics
```

## 📖 Usage

### Basic Usage

1. **Run with webcam**
```bash
python main.py --source 0
```

2. **Run with video file**
```bash
python main.py --source path/to/video.mp4
```

3. **Configure boundary line**
```bash
python main.py --source 0 --line-coords 100,200,400,200
```

### Configuration Options

- `--source`: Input source (0 for webcam, or path to video file)
- `--line-coords`: Boundary line coordinates (x1,y1,x2,y2)
- `--confidence`: Detection confidence threshold (default: 0.5)
- `--output`: Save output video path

## 📁 Project Structure

```
Pet-Monitoring-System/
│
├── model/               # YOLOv8 trained weights (.pt file)
├── utils/               # Custom scripts (e.g., line_crossing.py)
├── data/                # Sample input videos or image frames
├── output/              # Saved output videos with detection overlay
├── notebooks/           # Google Colab or Jupyter Notebooks
├── main.py              # Main script for running the system
├── requirements.txt     # Python dependencies
├── README.md            # Project documentation
└── LICENSE              # License file
```

## 🔧 How It Works

### 1. Pet Detection
- YOLOv8 processes each frame to detect pets (dogs, cats, etc.)
- Returns bounding boxes with confidence scores for detected pets

### 2. Boundary Monitoring
- User-defined virtual lines are drawn on the video feed
- System tracks the center point of each pet's bounding box
- Monitors movement relative to the boundary line

### 3. Alert System
- When a pet's center point crosses the boundary line, an alert is triggered
- Notifications can be visual, audio, or sent to external systems

### 4. Real-time Processing
- OpenCV handles frame capture and processing
- Continuous monitoring with minimal latency

## 📊 Development Status

| Feature | Status |
|---------|--------|
| YOLOv8 detection | ✅ Complete |
| Line-crossing detection | ✅ Working |
| Alert/Notification trigger | ✅ Basic alert |
| MATLAB testing | ⏳ Upcoming |
| Low-light handling | ⏳ Planned |
| Behavior analysis | ⏳ Planned |
| Multi-camera support | ⏳ Planned |

## 🎯 Use Cases

- **Home Safety**: Prevent pets from entering restricted areas (kitchen, balconies)
- **Stair Safety**: Alert when pets approach stairs or dangerous areas
- **Door Monitoring**: Track pets entering/exiting rooms
- **Smart Homes**: Integration with home automation systems
- **Pet Care Centers**: Monitor multiple pets in shelters or daycare
- **Behavioral Studies**: Foundation for advanced pet behavior analysis

## 🚀 Future Enhancements

### Short-term Goals
- [ ] Sound alert integration
- [ ] Mobile app notifications
- [ ] GUI for boundary configuration
- [ ] Performance optimization for low-end devices

### Long-term Vision
- [ ] AI-powered behavior analysis
- [ ] Multi-camera surveillance system
- [ ] Cloud-based monitoring dashboard
- [ ] Integration with smart home platforms
- [ ] Advanced analytics and reporting

## 🤝 Contributing

We welcome contributions to improve the Pet Monitoring System! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Areas for Contribution
- Performance optimization
- New detection algorithms
- UI/UX improvements
- Documentation enhancements
- Bug fixes and testing

## 👥 Team

- **Hunar Katyal** - Object detection & system architecture
- **Piyush** - Problem statement & solution analysis
- **Madhav** - Project updates & future development

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics) for the object detection model
- OpenCV community for computer vision tools
- All contributors and testers

## 📞 Contact

For questions, suggestions, or collaboration opportunities, please reach out:

- Project Issues: [GitHub Issues](https://github.com/yourusername/pet-monitoring-system/issues)
- Email: [katyalhunar921@gmail.com]

---

⭐ If you find this project helpful, please give it a star on GitHub!

Made with ❤️ for pet safety and smart home automation.
