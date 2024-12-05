# Deepstream People Trajectory CCTV

This project utilizes NVIDIA's DeepStream SDK to track the trajectory of people in a CCTV feed. The application processes video streams, detects objects, and visualizes their paths in real-time. It can be particularly useful for analyzing foot traffic in retail environments or monitoring public spaces.

![Sample Output](images/trajectory_output.gif)

## Overview

The application draws the trajectory paths of people walking through a defined region of interest (ROI). It can help identify areas with high demand, such as locations near advertisement hoardings or popular sections in a store.

### Use Cases
- **Retail Analysis**: Understand customer movement patterns and optimize store layouts.
- **Security Monitoring**: Track individuals in sensitive areas for enhanced security.
- **Traffic Management**: Analyze pedestrian traffic in public spaces.

## Requirements

- Python 3.x
- GStreamer
- NVIDIA DeepStream SDK
- Required Python packages (e.g., `gi`, `pyds`, `argparse`, `configparser`)

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd Deepstream_people_trajectory_CCTV
   ```

2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Ensure you have the NVIDIA DeepStream SDK installed and configured on your system.

## Configuration

The application requires configuration files for the primary and secondary inference engines, as well as the tracker. These files should be placed in the project directory:

- `dstest2_pgie_config.txt`: Configuration for the primary inference engine.
- `dstest2_tracker_config.txt`: Configuration for the tracker.

### Model Information

The models used in this project can be found in the `model` folder. Ensure that the model files are compatible with the DeepStream SDK and are properly configured in the respective configuration files.

## Usage

To run the application, use the following command:

```bash
python trajectory.py -i <input_stream>
```

Replace `<input_stream>` with the path to your input H264 elementary stream or RTSP URL. You can specify multiple input streams by separating them with spaces.

### Command Line Arguments

- `-i`, `--input`: Path to input H264 elementary stream (required).
- `-g`, `--gie`: Choose GPU inference engine type (`nvinfer` or `nvinferserver`, default is `nvinfer`).
- `-c`, `--codec`: RTSP Streaming Codec (`H264` or `H265`, default is `H264`).
- `-b`, `--bitrate`: Set the encoding bitrate (default is `4000000`).
- `--rtsp-ts`: Attach NTP timestamp from RTSP source (optional).

## License

This project is licensed under the Apache License, Version 2.0. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- NVIDIA for the DeepStream SDK.
- The open-source community for various libraries and tools used in this project.


