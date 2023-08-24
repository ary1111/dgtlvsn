# dgtl.vsn
![movingwin](/Resources/GIFs/RecordingDetectorExampleGIF.gif)
An object detection model for digital user interfaces

## Installation

### Fresh Docker Container setup
1. `docker run --gpus all -it -p 8888:8888 --name dgtlvsn tensorflow/tensorflow:latest/gpu`
2. `apt-get update && apt-get install git`
3. `apt-get install protobuf-compiler`
4. `apt-get install wget`
5. `python -m venv my-env`
6. `source my-env/bin/activate`
7. `python -m pip install --upgrade pip`
8. `pip install ipykernel`
9. `python -m ipykernel install --user --name=my-kernel`
10. `python -m pip install --upgrade jupyter`

### Existing python environment
11. Clone this repository.
12. Open 1_Setup.ipynb to install packages, creates folders, and ensure the check is satisfied.
13. Download sample dataset or place images in `/Tensorflow/workspace/images/train` and `/Tensorflow/workspace/images/test`.

## Result Summary
Training and evaluation were performed within a Docker container on a Windows machine (16gb RAM, RTX 3080)

Model: SSD Mobile Net 640x640
| Sites | Images | Steps  | AP    | AR    | CL     | TL     |
|-------|--------|--------|-------|-------|--------|--------|
| 5     | 10     | 2000   | 0.839 | 0.421 | 0.0995 | 0.4056 |
| 5     | 10     | 5000   | 0.872 | 0.429 | 0.1002 | 0.2400 |
| 5     | 50     | 2000   | 0.871 | 0.489 | 0.0260 | 0.1722 |
| 5     | 50     | 5000   | 0.896 | 0.498 | 0.0292 | 0.1540 |
| 5     | 50     | 10000  | 0.966 | 0.539 | 0.0213 | 0.1149 |
| 5     | 100    | 2000   | 0.909 | 0.452 | 0.0639 | 0.2225 |
| 5     | 100    | 5000   | 0.927 | 0.464 | 0.0184 | 0.1463 |
| 5     | 100    | 10000  | 0.879 | 0.439 | 0.0267 | 0.1220 |