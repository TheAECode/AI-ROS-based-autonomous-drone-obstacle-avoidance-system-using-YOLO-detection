# AI-ROS-based-autonomous-drone-obstacle-avoidance-system-using-YOLO-detection
 Deep learning drone obstacle avoidance for autonomous delivery and campus security surveillance that is YOLOv5-based, real-time person and obstacle detection with intelligent flight path replanning and seamless transition between Auto to Guided using QGC, and engineered with ROS/MAVROS integration ensures safe navigation in monitored zones.
 
# Core Technology Stack
### Hardware Platform: 

- NVIDIA Jetson Nano 4GB companion computer
- Pixhawk 2.4.8 flight controller running ArduPilot firmware
- Intel RealSense D435i RGB-D camera for environmental perception

### Software Framework: 

-  Robot Operating System (ROS) Noetic for middleware and communication
- YOLOv5 neural network for object detection and classification
- MAVROS for MAVLink protocol communication with flight controller
- OpenCV and PyTorch for computer vision processing

### Communication Protocol: 

- MAVLink 2.0 over UART serial connection at 115200 baud rate
- ROS topic-based inter-process communication
- Real-time data streaming between perception and control systems

# System Capabilities 
### Intelligent Detection and Classification 
The system employs a YOLOv5 neural network optimized for real-time inference on edge computing hardware. Key detection capabilities include:

- Real-time person detection with confidence-based filtering
- Size-based proximity estimation for distance approximation
- Multi-object tracking and temporal consistency validation
- Processing optimization achieving sub-second response times

### Mission-Aware Flight Control
The flight control system seamlessly integrates with existing autopilot missions through intelligent mode switching:

- Automatic mission interruption upon obstacle detection
- Temporary transition to guided flight mode for avoidance maneuvers
- State preservation and mission resumption after obstacle clearance
- Fail-safe mechanisms with timeout-based recovery protocols

| Metric | Value |
|--------|-------|
| Detection Range | 2+ meters for human-sized objects |
| Processing Latency | Less than 1 second detection-to-response |
| Frame Processing Rate | 15 FPS with 424x240 resolution |
| Detection Accuracy | Greater than 90% for target objects |
| Mission Recovery Time | Automatic resumption within 2 seconds |

# Interfaces with Intel RealSense camera hardware
- Provides RGB and depth data streams at 30 FPS
- Implements optimized resolution and frame rate settings for real-time performance

### Detection Layer (yolo_node.py)

- Executes YOLOv5 neural network inference on GPU hardware
- Implements CUDA optimizations for enhanced processing speed
- Provides object classification with confidence scoring and bounding box localization

### Decision Layer (person_avoidance.py)

- Processes detection results and evaluates threat levels
- Implements size-based distance estimation algorithms
- Generates avoidance commands based on proximity thresholds

### Control Layer (mavros_node.py)

- Manages communication with Pixhawk flight controller
- Handles flight mode transitions and mission state management
- Converts high-level avoidance commands to MAVLink protocol messages

### Monitoring Layer (status_monitor.py)

- Provides real-time system status visualization
- Implements comprehensive logging and diagnostic capabilities
- Displays mission progress and system health metrics

## Data Flow Architecture

```bash
Intel RealSense D435i
         |
    RGB/Depth Frames
         |
    YOLOv5 Neural Network
         |
    Object Detection Results
         |
    Obstacle Avoidance Logic
         |
    Flight Control Commands
         |
    MAVROS Interface
         |
    Pixhawk Flight Controller
```
    
# Commercial Applications
### Autonomous Delivery Operations
- The system enables safe package delivery in populated areas by automatically detecting and avoiding pedestrians while maintaining mission objectives. The implementation ensures regulatory compliance and operational safety in urban environments.

### Campus Security and Surveillance
- Designed for monitoring restricted areas while maintaining appropriate distances from detected individuals. The system provides continuous surveillance capabilities with intelligent human detection and respectful avoidance behaviors.

# Development and Testing
### System Integration
- The project demonstrates comprehensive systems engineering principles, including:
- Multi-threaded real-time processing architecture
- Hardware-software integration across multiple platforms
- Communication protocol implementation and optimization
- Fail-safe system design with robust error handling

### Performance Optimization
Significant engineering effort focused on real-time performance requirements:
- GPU acceleration implementation using CUDA frameworks
- Memory management optimization for embedded systems
- Algorithmic improvements for latency reduction
- Resource utilization monitoring and optimization

# Validation and Testing
### Comprehensive testing procedures ensure system reliability:

- Bench testing protocols with safety procedures
- Performance metric validation and documentation
- Integration testing with flight hardware
- Failure mode analysis and recovery procedures

# Technical Documentation
## Project Structure

```bash
├── src/
│   └── drone_ws/
│       └── src/
│           ├── custom_msgs/
│           │   ├── msg/
│           │   │   └── Detection2D.msg
│           │   ├── CMakeLists.txt
│           │   └── package.xml
│           └── drone_vision/
│               ├── scripts/
│               │   ├── realsense_node.py
│               │   ├── yolo_node.py
│               │   ├── person_avoidance.py
│               │   ├── mavros_node.py
│               │   └── status_monitor.py
│               ├── launch/
│               │   ├── pixhawk.launch
│               │   └── bench_test.launch
│               ├── CMakeLists.txt
│               └── package.xml
└── scripts/
    └── bench_test2.sh
```
# Installation Requirements
- Ubuntu 20.04 LTS operating system
- ROS Noetic with MAVROS packages
- Python 3.8+ with PyTorch and OpenCV libraries
- Intel RealSense SDK 2.0
- CUDA toolkit for GPU acceleration

# Professional Impact
This project demonstrates advanced capabilities in several key technical domains:
Artificial Intelligence and Machine Learning:

- Implementation of state-of-the-art object detection neural networks
- Real-time AI inference optimization for embedded systems
- Computer vision algorithm development and integration

# Robotics and Autonomous Systems:

- Multi-robot system architecture and communication protocols
- Real-time control system implementation
- Integration of perception, planning, and control subsystems

# Software Engineering:

- Distributed system architecture design and implementation
- Real-time software development with strict latency requirements
- Hardware-software integration and system-level optimization

# Systems Integration:

- Cross-platform development and deployment
- Communication protocol implementation and optimization
- Safety-critical system design with fail-safe mechanisms

# Results and Achievements
The completed system successfully demonstrates:

- Reliable real-time object detection with sub-second response times
- Seamless integration with commercial autopilot systems
- Robust operation in dynamic environments with multiple obstacles
- Professional-grade software architecture suitable for commercial deployment

This project represents a comprehensive solution combining cutting-edge AI technology with practical robotics applications, showcasing the ability to deliver complex technical solutions from concept through implementation and testing.

