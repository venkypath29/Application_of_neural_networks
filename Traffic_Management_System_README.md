
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
