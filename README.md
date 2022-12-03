# Road Lane Instance Segmentation Using YOLOv7 Segmentation Model

YOLOv7 Segmentation model forked from [here](https://github.com/RizwanMunawar/yolov7-segmentation).

## THS-ST1 & CSC930M Disclosure

This repository contains the code for the CSC930M small-scale project (Amoguis, Hermida, & Madrid) and also serves as the experimental implementation for the THS-ST1 thesis proposal by Amoguis, Dy, Guerrero, & Marquez. Both groups were advised by Dr. Joel P. Ilao.

## Training the Model

Model training is done using the `train.py` script and behaves exactly like the usual YOLO training scripts. The training script here is based on YOLOv5, but the model architecture is based on YOLOv7. The training script is modified to support the segmentation model by the original repository author, [Rizwan Munawar](https://github.com/RizwanMunawar). This README will no longer go more in-depth on the training process, as it is already well-documented in the [original repository](https://github.com/RizwanMunawar/yolov7-segmentation).

## Running Inference

Inference is done by either invoking the `segment/detect.py` script from the original repository, or by using the `lane_inference.py` script that the authors of this repository have created as a convenience wrapper for the purposes of demonstrating the THS-ST1 and CSC930M experiments.

### Using `segment/predict.py`

```
python segment/predict.py \
    --source <path/to/image/or/video> \     # Pass a valid path
    --weights <path/to/weights> \           # Path to weights file
    --conf <conf_threshold> \               # Confidence threshold
    --iou-thres <iou_threshold> \           # IOU threshold
    --device <device> \                     # Device to use for inference, uses GPU if detected and supported. Otherwise, CPU.
    --save-txt --save-conf                  # Save detection results as text files
    --hide-labels --view-img                # Hide labels and show images in real-time
```

## Available Trained Weights

Weights are trained on this [dataset](https://universe.roboflow.com/demarcationbased-road-lane-segmentation/road-lane-instance-segmentation).

Proof-of-concept weights are available for download [here](https://github.com/AdrielAmoguis/Road-Lane-Detection-With-YOLOv7/releases/tag/proof-of-concept-weights).
