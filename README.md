# Smart Traffic Surveillance System  
**YOLOv5 | OpenCV | Python | Real-Time Object Detection**

---

## 🚀 Overview  
The **Smart Traffic Surveillance System** is an AI-powered solution designed to enhance urban traffic management and road safety by automatically detecting helmet and license plate violations in real time. Leveraging the YOLOv5 object detection model and OpenCV, this system enables intelligent monitoring for smart city applications.

This project demonstrates a complete pipeline—from data collection and model training to real-time video inference and edge deployment—providing actionable insights for traffic enforcement teams.

---

## 🔍 Key Features  
✅ **High-Accuracy Detection**  
- Trained YOLOv5 model on **5,000+ annotated images**  
- Achieves **92% detection accuracy** for helmets and license plates  

✅ **Real-Time Video Analysis**  
- Integrated with **OpenCV** for live video stream processing  
- Instant alerts triggered upon violation detection  

✅ **Edge-Optimized Inference**  
- Model optimized for **low-power devices** (e.g., Jetson Nano, Raspberry Pi)  
- **40% reduction in inference time**, ideal for edge deployment in smart cities  

✅ **End-to-End Pipeline**  
- Full workflow: Data collection → Annotation → Training → Real-time inference → Alert system  

✅ **Scalable & Deployable**  
- Designed for integration into existing city surveillance infrastructure  

---

## 🧰 Technologies Used  
- **YOLOv5**: State-of-the-art object detection model (PyTorch-based)  
- **OpenCV**: Real-time video capture and processing  
- **Python 3.x**: Core programming and scripting  
- **PyTorch**: Deep learning framework  
- **TensorRT (optional)**: For edge optimization and acceleration  
- **LabelImg / CVAT**: For image annotation  

---

## 📦 Project Structure  
```
smart-traffic-surveillance/
│
├── data/                   # Dataset (images & labels)
├── models/                 # Trained YOLOv5 weights (.pt files)
├── runs/                   # Training & detection logs
├── utils/                  # Custom scripts (preprocessing, alerting, etc.)
├── detect.py               # Real-time detection script
├── train.py                # Training script (YOLOv5-compatible)
├── requirements.txt        # Python dependencies
├── README.md               # This file
└── config/                 # Configuration files (e.g., alert thresholds, camera feeds)
```

---

## 🛠️ Installation & Setup  

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/smart-traffic-surveillance.git
cd smart-traffic-surveillance
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

> ⚠️ Requires PyTorch. Install from [pytorch.org](https://pytorch.org) based on your CUDA version.

### 3. Download Pre-Trained Model (Optional)
Place your trained `best.pt` model in the `models/` directory or retrain using your dataset.

### 4. Run Real-Time Detection
```bash
python detect.py --weights models/best.pt --source 0  # Webcam
python detect.py --weights models/best.pt --source input_video.mp4  # Video file
python detect.py --weights models/best.pt --source rtsp://camera-stream-url  # IP camera
```

---

## 📊 Training Your Own Model  
To retrain on custom data:

1. Annotate images using LabelImg or CVAT (YOLO format).
2. Organize dataset in `data/` with `images/` and `labels/` folders.
3. Update `data.yaml` with class names and paths.
4. Start training:
```bash
python train.py --img 640 --batch 16 --epochs 100 --data data/data.yaml --weights yolov5s.pt
```

---

## 📢 Real-Time Alerts  
When a violation (e.g., no helmet, obscured plate) is detected:
- Bounding box is drawn on the video feed
- Alert message is printed/logged
- Optional: Send notification via email/SMS or API to enforcement dashboard

---

## 🖥️ Edge Deployment  
Optimized for deployment on edge devices:
- Use TensorRT or ONNX for faster inference
- Quantize model to FP16/INT8 precision
- Tested on NVIDIA Jetson Nano with <0.1s latency per frame

---

## 🌆 Use Cases  
- **Traffic violation monitoring** at intersections  
- **Automated enforcement** without manual surveillance  
- **Smart city integration** with centralized traffic control systems  
- **Safety compliance** in high-risk zones  

---

## 📈 Performance Metrics  
| Metric                     | Value           |
|---------------------------|-----------------|
| Detection Accuracy        | 92%             |
| Inference Time (Edge)     | Reduced by 40%  |
| Model Size                | ~14MB (YOLOv5s) |
| Frames Per Second (FPS)   | 25+ (on edge)   |

---

## 📂 Dataset  
- **5,000+ annotated images** collected from urban traffic cameras  
- Classes: `Helmet`, `No Helmet`, `License Plate`  
- Augmented with brightness, blur, and scale variations for robustness  

> *Note: Dataset available upon request (contact or provide link if public)*

---

## 📢 Future Enhancements  
- License plate recognition (OCR integration)  
- Vehicle type classification (car, bike, truck)  
- Cloud dashboard for live monitoring  
- Integration with municipal traffic systems  

---

## 📄 License  
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 📬 Contact  
**Developer**: [Your Name]  
**Email**: your.email@example.com  
**GitHub**: [@yourusername](https://github.com/yourusername)  

---

🔧 *Empowering safer cities with intelligent vision.* 🏙️🚦
