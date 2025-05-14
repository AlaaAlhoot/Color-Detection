
# 🎨 Color Detection System using OpenCV

![Python](https://img.shields.io/badge/Python-3.11-blue)
![OpenCV](https://img.shields.io/badge/OpenCV-4.5+-brightgreen)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

## 🧠 Project Overview

This project implements a **real-time and batch image color detection system** using Python and OpenCV. The system is capable of identifying basic colors (Red, Green, Blue), annotating the image with the detected color, extracting hex values, and logging the results into an Excel file—formatted with actual color fills for intuitive visualization.

> 📁 Supports both **webcam video input** and **folder-based image processing**!

---

## 🔍 Why is Color Detection Important?

- 🎯 Fundamental to computer vision applications: object detection, tracking, and classification.
- 🏭 Used in industrial inspection and quality control.
- 🤖 Powers intelligent systems with human-like visual perception.
- 🧪 Applied in medical imaging for diagnostics.
- 📚 Excellent learning tool for beginners in image processing.

---

## 🧰 Tools & Technologies Used

| Tool        | Purpose                                |
|-------------|----------------------------------------|
| Python 3.11 | Core programming language              |
| OpenCV      | Image processing and color detection   |
| NumPy       | Array operations and logical masks     |
| Pandas      | Structured data management             |
| openpyxl    | Excel writing and color formatting     |
| datetime, os| File management and timestamping       |

> See full dependencies in [`requirements.txt`](./requirements.txt)

---

## 🧭 How It Works

### ⚙️ Mode Selection
- **Mode 1**: Real-time webcam color detection.
- **Mode 2**: Batch processing of all images in `/img_test` folder.

### 🖼️ Image Processing Pipeline

1. **Image Capture**:
   - Webcam feed via `cv2.VideoCapture(0)` or image reading from disk.

2. **Color Space Conversion**:
   - Convert image from BGR to HSV using `cv2.cvtColor`.

3. **Color Masking & Detection**:
   - HSV range masking for Red, Green, and Blue.
   - Noise reduction using Gaussian blur.
   - Mask refinement using morphological opening.

4. **Fallback Handling**:
   - If no color is detected, convert to grayscale and label as "Other".

5. **Annotation**:
   - Draw a rectangle with the detected color.
   - Overlay color name and hex code using `cv2.putText`.

6. **Excel Export**:
   - Save detection results (`Image name`, `Color name`, `Hex`) to Excel.
   - Auto-fill cell background color to match detected color.

7. **Statistics Summary**:
   - Print total occurrences of each color across the dataset.

---

## 🖼️ Output Samples

### 📷 Real-Time Detection Example

![Real-Time](https://img.shields.io/badge/Webcam-Active-green)

- Detected color is displayed on the live feed.
- Hex value and color label are shown on the image.

### 📊 Excel Report

| Image       | Detected Color | Hex Code | Color Preview |
|-------------|----------------|----------|----------------|
| image1.jpg  | Blue           | #123ABC  | ![Blue](https://via.placeholder.com/15/123ABC/000000?text=+) |
| image2.jpg  | Red            | #C3211F  | ![Red](https://via.placeholder.com/15/C3211F/000000?text=+) |

> The Excel file is fully formatted with visual color previews.

---

## 📈 Sample Statistics

After processing 10 test images:

- 🔵 **Blue**: 3 occurrences  
- 🟢 **Green**: 2 occurrences  
- 🔴 **Red**: 1 occurrence  
- ⚫ **Other**: 4 occurrences  

---

## 💡 Lessons Learned

- HSV is better suited for color segmentation than RGB.
- Proper masking with blur and morphological operations improves accuracy.
- Data presentation matters—Excel formatting boosts interpretability.
- Modular coding enables easier updates and feature additions.

---

## 🚀 Future Enhancements

- 🔧 Add GUI using Tkinter or PyQt
- 🌈 Extend color detection to Yellow, Orange, Purple, etc.
- 🧠 Integrate ML models for mixed/subtle color detection
- 🎥 Support video file input
- 📊 Create a real-time dashboard for monitoring and logging

---

## 📂 Project Structure

```
Color-Detection/
│
├── img_test/                    # Folder of test images to be processed (Mode 2)
├── results.xlsx                 # Excel log file with detection results and color formatting (auto-generated)
├── Color Detection Code.ipynb  # Main Jupyter Notebook containing full implementation
├── requirements.txt            # List of dependencies required to run the project
├── README.md                   # Project documentation (this file)
└── Color Detection Report.docx # Full academic report explaining the system in depth
```

---

## ✅ Installation & Running

1. **Clone the repository**:

```bash
git clone https://github.com/your-username/color-detection.git
cd color-detection
```

2. **Install dependencies**:

Make sure you have Python 3.11 installed, then run:

```bash
pip install -r requirements.txt
```

3. **Run the Jupyter Notebook**:

```bash
jupyter notebook "Color Detection Code.ipynb"
```

4. **Follow On-Screen Prompt**:

- Input `1` → For real-time detection using the webcam.  
- Input `2` → To process all images inside the `/img_test` folder.

---

## 🧑‍💻 Author

**🎓 Alaa Emad Al Hout**  
🆔 120233046  
👨‍🏫 Supervised by: Dr. Ashraf Younis Al-Maghari
📘 Course: Advanced Image Processing  
🏫 Islamic University of Gaza - Postgraduate Studies (Master's) - Faculty of Information Technology 
📅 Date: May 14, 2025  

---

## 📜 License

This project is released under the [MIT License](https://opensource.org/licenses/MIT).  
You are free to use, modify, and distribute this software with proper attribution.

---

## 📘 Additional Documentation

For a deeper explanation of the project background, objectives, methodology, and results, refer to the full academic report:

📄 [`Color Detection Report.docx`](./Color%20Detection%20Report.docx)

---

> 🚀 *“Simple systems can lead to powerful results when built on solid fundamentals.”*
