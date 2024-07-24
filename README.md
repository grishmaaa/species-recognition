# YOLO Object Detection

This project demonstrates object detection using the YOLO (You Only Look Once) algorithm. The provided code processes an input image and detects objects using a pre-trained YOLO model.

## Project Structure

```
yolo-object-detection/
│
├── yolo.py                # Main script to run YOLO object detection
├── images/                # Directory for input images
├── output/                # Directory to save output images
├── .gitattributes         # Git attributes configuration
└── yolo-coco/             # Directory containing YOLO configuration files
    ├── yolov3.cfg         # YOLO model configuration file
    ├── yolov3.weights     # YOLO pre-trained weights
    └── coco.names         # COCO dataset class labels
```

## Setup

1. **Clone the repository**:
    ```sh
    git clone https://github.com/your-username/yolo-object-detection.git
    cd yolo-object-detection
    ```

2. **Download YOLOv3 weights**:
    - Download the YOLOv3 weights from [this link](https://pjreddie.com/media/files/yolov3.weights).
    - Place the downloaded `yolov3.weights` file in the `yolo-coco` directory.

3. **Install dependencies**:
    ```sh
    pip install numpy opencv-python
    ```

## Usage

To run the object detection script, use the following command:

```sh
python yolo.py --image path/to/your/image.jpg --yolo yolo-coco
```

### Arguments

- `--image`: Path to the input image.
- `--yolo`: Base path to the YOLO directory containing the configuration files.
- `--confidence`: Minimum confidence threshold to filter weak detections (default: 0.5).
- `--threshold`: Threshold for non-maxima suppression to filter overlapping bounding boxes (default: 0.3).

## Example

```sh
python yolo.py --image images/dog.jpg --yolo yolo-coco
```

This command will load the YOLO model, process the `dog.jpg` image, and display the image with detected objects.

## Notes

- Ensure that the `yolov3.weights`, `yolov3.cfg`, and `coco.names` files are present in the `yolo-coco` directory.
- The output image with detected objects will be displayed using OpenCV's `imshow` function.

## Acknowledgments

- The YOLO algorithm was developed by Joseph Redmon et al. More information can be found on the [YOLO website](https://pjreddie.com/darknet/yolo/).
- The COCO dataset is used for training the model, providing a comprehensive set of class labels.
