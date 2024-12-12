
# Traffic Management System

This project implements a Traffic Management System using YOLOv5 for object detection and tracking. It processes traffic videos to detect and track vehicles, providing insights and analytics for effective traffic management.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [License](#license)

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/yourusername/traffic-management-system.git
    cd traffic-management-system
    ```

2. Install the required dependencies:
    ```sh
    pip install -r yolov5/requirements.txt
    ```

3. (Optional) Set up a virtual environment:
    ```sh
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

## Usage

1. To detect objects in a video, run:
    ```sh
    python yolov5/detect.py --source path/to/your/video.mp4
    ```

2. To train the model with custom data, run:
    ```sh
    python yolov5/train.py --data path/to/your/data.yaml --cfg yolov5/models/yolov5s.yaml --weights yolov5s.pt
    ```

3. To validate the model, run:
    ```sh
    python yolov5/val.py --data path/to/your/data.yaml --weights yolov5s.pt
    ```

## Project Structure

- `content/UA-DETRAC/DETRAC_Upload/`: Contains the UA-DETRAC dataset.
- `results/`: Directory for storing results.
- `yolov5/`: Contains the YOLOv5 implementation.
  - `classify/`: Classification scripts.
  - `data/`: Data processing scripts.
  - `models/`: Model definitions.
  - `utils/`: Utility functions.
  - `detect.py`: Script for object detection.
  - `train.py`: Script for training the model.
  - `val.py`: Script for validating the model.
- `traffic-management-v2.ipynb`: Jupyter notebook for traffic management analysis.
- `README.md`: Project documentation.
- `requirements.txt`: List of dependencies.

## License

This project is licensed under the MIT License. See the [LICENSE](yolov5/LICENSE) file for details.

# YOLOv5s Object Detection with ONNX and TensorRT

This project implements object detection using YOLOv5s models in both ONNX and TensorRT formats. It processes video sources, detects objects, and performs lane management with vehicle counting for various use cases.

## Project Structure

```plaintext
common/
	__pycache__/
	utils.py
datas/
	coco.names
implementation_with_yolov5s_onnx_model/
	.main.py.swp
	datas/
		coco.names
	main.py
	outputs/
implementation_with_yolov5s_tensorrt_model/
	__pycache__/
	main.py
	Processor (copy).py
	Processor.py
models/
	yolov5s_1.onnx
	yolov5s.onnx
	yolov5s.trt
requirement.txt
screenshots/
```

## Prerequisites

Ensure you have Python 3.6 or higher installed and the required dependencies:

### Installing Dependencies

Install the dependencies listed in `requirement.txt`:

```plaintext
python>=3.6
numpy==1.18.5
opencv
tensorrt==7.1.3.0
pycuda
tqdm
protobuf
onnx
netron
openCv
```

Run:

```sh
pip install -r requirement.txt
```

## Data Preparation

- The `datas/coco.names` file contains class names for object detection. This file maps class IDs to class names used during model inference.

## Common Utilities

- `utils.py` contains utility classes and functions for bounding box management, lane processing, vehicle counting, result display, and model output processing.

## YOLOv5s ONNX Model Implementation

### File: `implementation_with_yolov5s_onnx_model/main.py`

- **Initialization**:
  - Loads video sources and the YOLOv5s ONNX model using OpenCV's DNN module.
  - Configures lane management.

- **Main Loop**:
  - Captures frames, assigns them to lanes, processes using `final_output`, and displays results.

### Running ONNX Implementation

```sh
python implementation_with_yolov5s_onnx_model/main.py --sources video1.mp4,video2.mp4,video3.mp4,video4.mp4
```

## YOLOv5s TensorRT Model Implementation

### File: `implementation_with_yolov5s_tensorrt_model/main.py`

- **Initialization**:
  - Loads video sources and the YOLOv5s TensorRT model using the `Processor` class.
  - Configures lane management.

- **Main Loop**:
  - Captures frames, assigns them to lanes, processes using `final_output_tensorrt`, and displays results.

### TensorRT Processor Class

- **File: `Processor.py`**
  - Handles TensorRT engine loading, input/output memory allocation, and inference.
  - Includes methods for image preprocessing, inference, and object detection.

### Running TensorRT Implementation

```sh
python implementation_with_yolov5s_tensorrt_model/main.py --sources video1.mp4,video2.mp4,video3.mp4,video4.mp4
```

## Outputs

- Detected objects and lane management results are displayed in real-time.
- Outputs are stored in `implementation_with_yolov5s_onnx_model/outputs/` or displayed directly.

## Key Features

- ONNX and TensorRT model compatibility.
- Real-time object detection and lane-based vehicle counting.
- Modular design with reusable utilities.

## Screenshots

Include screenshots of detected objects and results in the `screenshots/` directory.

## Notes

- Ensure that the TensorRT engine is built for your hardware configuration.
- Adjust confidence thresholds in the utility functions to optimize detection performance.

---

For any issues, please raise an issue in the repository or contact the maintainer.
