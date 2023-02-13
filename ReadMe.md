# Fire detection system

## Install
Clone this repo and use the following script to install [YOLOv5](https://github.com/ultralytics/yolov5.git).
```
cd yolov5
pip install -r requirements.txt  # install
```

## Datasets
- Download [here](https://drive.google.com/file/d/1L2HsROH0Zt_0wJC21cEC-92CVxE0T_k-/view?usp=sharing).
- Unzip it and put it into "Datasets" folder (e.g. /Datasets/Fire_Default/).

## Testing code
To use the pretrained model, run the codes as follows:
```
python classify/val.py --weights runs/train-cls/exp1/weights/best.pt --data ../Datasets/Fire_Default

```

## Results
![Results](https://github.com/drx770/fire_detection/blob/main/result.png)


## If you want to train a new model
If you want to train your own model (maybe with a custom dataset), use the following commands.

Download some pre-trained weights:
```
%cd ../yolov5
from utils.downloads import attempt_download

p5 = ['n', 's', 'm', 'l', 'x']  # P5 models
cls = [f'{x}-cls' for x in p5]  # classification models

for x in cls:
    attempt_download(f'weights/yolov5{x}.pt')
```

Training:
```
python classify/train.py --model yolov5s-cls.pt --data $DATASET_NAME --epochs 5 --img 128 --pretrained weights/yolov5s-cls.pt
```
