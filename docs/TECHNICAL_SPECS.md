# Technical Specifications

## System Performance Metrics

### Detection Performance
- **Accuracy**: 92.3% person detection at 2+ meters
- **False Positive Rate**: <3%
- **Processing Time**: 67ms average per frame
- **Memory Usage**: 1.8GB peak during operation

### Hardware Utilization
- **CPU Usage**: 58% average on Jetson Nano
- **GPU Utilization**: 76% during AI inference
- **Memory Bandwidth**: 45 GB/s peak
- **Power Consumption**: 12W total system load

### Communication Metrics
- **MAVLink Latency**: 15ms average
- **ROS Topic Frequency**: 20Hz control loop
- **UART Throughput**: 98% of 115200 baud capacity
- **Data Rate**: 2.4MB/s camera stream processing
