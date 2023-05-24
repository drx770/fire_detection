# Fire detection system

## Install
Clone this repo and use the following script to install [YOLOv5](https://github.com/ultralytics/yolov5.git).
```
cd yolov5
pip install -r requirements.txt  # install
```

## Datasets
- Download [here](https://drive.google.com/file/d/1klIBKVx0eFteGuo8skYaT--wVR48mcY2/view?usp=sharing).
- Unzip it and put it into "Datasets" folder (e.g. /Datasets/Fire_Default/).

## Testing code
To use the pretrained model, run the codes as follows:
```
python classify/val.py --weights runs/train-cls/exp1/weights/best.pt --data ../Datasets/Fire_Default

```

## Predict

```
python classify/predict.py --weights runs/train-cls/exp1/weights/best.pt --source $TEST_IMAGE_PATH
```

## Results
![Results](https://github.com/drx770/fire_detection/blob/main/result.png)


