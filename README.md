<div align="center">

# 🪄 Invisible Cloak using Python & OpenCV

<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
<img src="https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white" alt="OpenCV"/>
<img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy"/>

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=for-the-badge)](http://makeapullrequest.com)
[![GitHub Stars](https://img.shields.io/github/stars/deepakrajjs-29/invisible-cloak?style=for-the-badge)](https://github.com/deepakrajjs-29/invisible-cloak/stargazers)

*Bringing Harry Potter magic to life with Computer Vision* ✨

[Features](#-features) • [Demo](#-demo) • [Installation](#-installation) • [Usage](#-usage) • [Contributing](#-contributing) • [License](#-license)

</div>

---

## 🌟 Overview

Ever wanted to own an **Invisibility Cloak** like Harry Potter? Now you can create one using the power of Computer Vision! This project uses **Python** and **OpenCV** to make a cloak of a specific color disappear in real-time video, creating a magical augmented reality experience.

### How It Works

The magic happens through these steps:

1. **📷 Background Capture** - The system captures the initial background scene
2. **🎨 Color Detection** - Identifies the cloak based on color (default: red)
3. **🔍 Mask Creation** - Generates a precise mask of the cloak area
4. **✨ Background Replacement** - Replaces the masked area with the saved background
5. **🎬 Real-time Magic** - Displays the invisible effect live!

---

## ✨ Features

- 🎯 **Real-time Processing** - Instant invisibility effect with live video
- 🎨 **Customizable Colors** - Configure any cloak color (red, blue, green, etc.)
- 🖼️ **Background Replacement** - Seamless background integration
- 🔧 **Easy Setup** - Minimal dependencies, quick to get started
- 📚 **Educational** - Perfect for learning Computer Vision concepts
- 🆓 **Open Source** - Free to use, modify, and contribute

---

## 🎬 Demo

https://github.com/user-attachments/assets/ddab1871-df9c-4651-92d0-00915ac5f04a

*Experience the magic of becoming invisible in real-time!*

---

## 🛠️ Tech Stack

| Technology | Purpose |
|------------|---------|
| **Python 3.x** | Core programming language |
| **OpenCV** | Computer vision and image processing |
| **NumPy** | Numerical operations and array handling |

---

## 📦 Installation

### Prerequisites

- Python 3.7 or higher
- Webcam or camera device
- Operating System: Windows, macOS, or Linux

### Setup Steps

1. **Clone the Repository**

```bash
git clone https://github.com/deepakrajjs-29/invisible-cloak.git
cd invisible-cloak
```

2. **Create Virtual Environment (Recommended)**

```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

3. **Install Dependencies**

```bash
pip install -r requirements.txt
```

Or install manually:

```bash
pip install opencv-python numpy
```

---

## 🚀 Usage

### Quick Start

Run the script with default settings (red cloak):

```bash
python invisible_cloak.py
```

### Controls

| Key | Action |
|-----|--------|
| **ESC** | Exit the program |
| **Space** | Recapture background |
| **C** | Toggle cloak detection |

### Step-by-Step Guide

1. **Position yourself** away from the camera view
2. **Press Space** to capture the background (ensure cloak is not visible)
3. **Wear the cloak** and move into the frame
4. **Watch the magic** happen in real-time!
5. **Press ESC** to exit

---

## 🎨 Customization

### Changing Cloak Color

The project uses HSV color space for detection. Modify these values in `invisible_cloak.py`:

**Red Cloak (Default):**
```python
lower_red = np.array([0, 120, 70])
upper_red = np.array([10, 255, 255])
```

**Blue Cloak:**
```python
lower_blue = np.array([94, 80, 2])
upper_blue = np.array([126, 255, 255])
```

**Green Cloak:**
```python
lower_green = np.array([40, 40, 40])
upper_green = np.array([80, 255, 255])
```

### Finding Your Color Range

Use this helper code to find HSV values for any color:

```python
import cv2
import numpy as np

def find_hsv_range(image_path):
    img = cv2.imread(image_path)
    hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
    # Click on the color you want to detect
    print(f"HSV Value: {hsv[y, x]}")  # Replace x, y with clicked coordinates
```

---

## 📁 Project Structure

```
invisible-cloak/
│
├── invisible_cloak.py       # Main application script
├── requirements.txt          # Python dependencies
├── README.md                 # Project documentation
├── LICENSE                   # MIT License
├── .gitignore               # Git ignore file
│
├── assets/                   # Media files for README
│   └── demo.mp4
│
└── examples/                 # Example configurations
    ├── red_cloak.py
    ├── blue_cloak.py
    └── green_cloak.py
```

---

## 🧠 How It Works (Technical)

### Algorithm Overview

```
1. Color Space Conversion
   ├─ BGR → HSV conversion
   └─ Better color detection in HSV
   
2. Mask Generation
   ├─ cv2.inRange() for color detection
   ├─ Morphological operations (opening/dilation)
   └─ Noise removal
   
3. Background Replacement
   ├─ Bitwise operations
   ├─ Mask inversion
   └─ Frame composition
   
4. Real-time Display
   └─ cv2.imshow() for output
```

### Key Concepts

- **HSV Color Space**: More intuitive for color detection than RGB
- **Morphological Operations**: Remove noise and refine mask
- **Bitwise Operations**: Combine foreground and background seamlessly
- **Background Subtraction**: Core technique for invisibility effect

---

## 🤝 Contributing

We love contributions! Whether it's bug fixes, new features, or documentation improvements, all contributions are welcome.

### How to Contribute

1. **Fork the repository**
2. **Create your feature branch**
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add some AmazingFeature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/AmazingFeature
   ```
5. **Open a Pull Request**

### Contribution Ideas

- [ ] Add support for multiple cloak colors simultaneously
- [ ] Implement GUI for color selection
- [ ] Add video recording functionality
- [ ] Improve mask refinement algorithms
- [ ] Create mobile app version
- [ ] Add AR effects and filters
- [ ] Implement machine learning for better segmentation
- [ ] Add performance optimization

### Code Style

- Follow PEP 8 guidelines
- Add comments for complex logic
- Update documentation for new features
- Write meaningful commit messages

---

## 📖 Learning Resources

### Concepts Used in This Project

- **Computer Vision Basics**
  - Image processing fundamentals
  - Color space transformations
  - Morphological operations
  
- **OpenCV Techniques**
  - Video capture and display
  - Image masking and filtering
  - Bitwise operations

- **Python Programming**
  - NumPy array operations
  - Real-time video processing
  - Event handling

### Recommended Reading

- [OpenCV Documentation](https://docs.opencv.org/)
- [Python NumPy Tutorial](https://numpy.org/doc/stable/user/quickstart.html)
- [HSV Color Space Explained](https://en.wikipedia.org/wiki/HSL_and_HSV)

---

## 🐛 Troubleshooting

### Common Issues

**Camera not detected:**
```python
# Try changing camera index
cap = cv2.VideoCapture(1)  # Try 0, 1, 2, etc.
```

**Color not detected properly:**
- Ensure good lighting conditions
- Adjust HSV range values
- Use a solid color cloak without patterns

**Laggy performance:**
- Reduce frame resolution
- Close other applications
- Update OpenCV to latest version

---

## 🗺️ Roadmap

- [x] Basic invisibility effect
- [x] Red cloak detection
- [ ] Multi-color support
- [ ] GUI interface
- [ ] Mobile app version
- [ ] AR filters integration
- [ ] Machine learning segmentation
- [ ] Cloud processing support

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

```
MIT License - You are free to:
✓ Use commercially
✓ Modify
✓ Distribute
✓ Private use
```

---

## 🙏 Acknowledgments

- **J.K. Rowling** - For inspiring the magical world of Harry Potter
- **OpenCV Community** - For the amazing computer vision library
- **Contributors** - Thanks to everyone who has contributed to this project!

---

## 📞 Contact & Support

<div align="center">

**Have questions or suggestions?**

[![GitHub Issues](https://img.shields.io/badge/GitHub-Issues-red?style=for-the-badge&logo=github)](https://github.com/deepakrajjs-29/invisible-cloak/issues)
[![Email](https://img.shields.io/badge/Email-Contact-blue?style=for-the-badge&logo=gmail)](mailto:deepakrajjs2909@gmail.com)

**Show your support!**

⭐ Star this repository if you found it helpful!

[![GitHub followers](https://img.shields.io/github/followers/deepakrajjs-29?style=social)](https://github.com/deepakrajjs-29)

</div>

---

<div align="center">

### 🌟 Made with ❤️ and Python

**Happy Coding! 🚀**

</div>
