# Smart Traffic Analysis With YOLO

## Smart Traffic Monitoring: Real-Time CCTV Analysis with YOLOv12N

Traffic management and road safety are crucial for modern smart cities. Detecting traffic violations, ensuring road safety, and improving urban transportation require innovative solutions. This is where the "Smart Traffic Monitoring: Real-Time CCTV Analysis with YOLOv12N" project comes in.

## Purpose of the Project

In big cities, monitoring traffic flow and detecting violations instantly can help reduce traffic accidents and optimize urban mobility. The project aims to:

- **Detect emergency lane violations** and identify vehicles that block emergency vehicles.
- **Analyze lane-based traffic flow speed** and congestion to determine traffic conditions.
- **Count vehicles and classify types** to provide data on different vehicle types.

This system can be integrated into smart city management, helping to create a fair and efficient traffic system.

## Technology and Methods Used

This project is built using YOLOv12N, a deep learning and computer vision model. The model was trained for 250 epochs using a large vehicle dataset from Roboflow Universe.

### Roboflow Polygon Tool Integration

- **Region-Based Detection**: The Polygon Tool from Roboflow was used to mark lanes and roads in CCTV footage.
- **Flexible Zone Analysis**: Each lane was analyzed separately to track vehicles and measure speeds.

### Real-Time Processing

- **CCTV Video Analysis**: The model analyzed real-time footage from Istanbul's Kozyatagi CCTV cameras.
- **NVIDIA Optimization**: The model can be converted to .onnx or .engine format to run efficiently on NVIDIA-powered devices.

## Installation

1. Clone the repository:
```
git clone https://github.com/yourusername/smart-traffic-analysis.git
cd smart-traffic-analysis
```

2. Install required dependencies:
```
pip install -r requirements.txt
```

3. Download the YOLO model weights (not included in repository due to size):
```
# Place your trained model weights in the project root directory
```

## Usage

Run the lane detection script:

```
python lane_vehicle_detection.py --source_video_path /path/to/your/video.mp4 --target_video_path /path/to/output.mp4
```

Additional options:
```
--source_weights_path /path/to/model/weights.pt  # Custom model path
--confidence_threshold 0.3                       # Detection confidence (0-1)
--iou_threshold 0.7                              # IOU threshold (0-1)
--display                                        # Show processing in real-time
```

## Technical Details: Code and Structure

This project follows a modular approach. Below are the key components:

### 1. LaneDetector Class

- **Loads Polygon Data**: Reads lane regions from a JSON file and scales them to match video resolution.
- **Determines Lane Positions**: Checks if a detected vehicle is inside a lane using its bounding box.
- **Tracks Vehicle Counts and Speed**: Counts vehicles and calculates average speed per lane.

### 2. LaneVehicleProcessor Class

- **Integrates YOLO and ByteTrack**: YOLO detects vehicles, and ByteTrack tracks them across frames.
- **Analyzes Detection Zones**: Compares detected vehicles with predefined lane regions.
- **Displays Traffic Data**: Uses OpenCV and Supervision libraries to overlay real-time data on the video.

### 3. Traffic Flow Management

- **Entry and Exit Zones**: Tracks which lanes vehicles enter and exit.
- **Speed Estimation**: Assigns random but realistic speed values to vehicles.
- **Emergency Lane Warning**: Detects vehicles in the emergency lane and issues warnings.

## Results and Future Improvements

This project provides a real-time solution for traffic monitoring using CCTV footage. The collected data can:

- Improve traffic management systems for better control of congestion.
- Reduce traffic violations and accidents through automated detection.
- Ensure emergency vehicles can reach their destinations faster.

### Future Enhancements

- **Model Optimization**: Convert YOLOv12N to .onnx or .engine format for better real-time performance.
- **Dataset Expansion**: Train with images from different angles and weather conditions to improve accuracy.
- **Advanced Analysis**: Use machine learning for predictive modeling of traffic patterns.

## Conclusion

The "Smart Traffic Monitoring: Real-Time CCTV Analysis with YOLOv12N" project demonstrates how AI can improve road safety and traffic management. By integrating real-time vehicle detection and lane-based traffic analysis, this system can help cities manage traffic more effectively and ensure better road safety.

Technology is shaping the future of smart cities, and projects like this are crucial in making urban areas more efficient and safe for everyone.

## License

[MIT License](LICENSE)

## Contributors

- Your Name - Initial work and development
