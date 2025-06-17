# DDPC-DD
### Usage 
We run the code with torch version: 1.7.0, python version: 3.7.16
* Train FPC2025
```
# python train.py --workers 8 --device 0 --batch 24 --data data/coco.yaml --img 640 --cfg models/detect/gelan-c.yaml --weights '' --name baseline --hyp hyp.scratch-high.yaml --min-items 0 --epochs 100 --close-mosaic 15
# python train_GAN.py --workers 8 --device 0 --batch 24 --data data/coco.yaml --img 640 --cfg models/detect/trian_GAN.yaml --base_cfg models/detect/base-c.yaml --weights runs/train/baseline/weights/best.pt --name gelan-c-det --hyp hyp.scratch-high.yaml --min-items 0 --epochs 100 --close-mosaic 10 --freeze 9
# python train_CIOD.py --workers 8 --device 0 --batch 24 --data data/coco.yaml --img 640 --cfg models/detect/IC-OD-c.yaml --weights runs/train/GAN_FPC/weights/last.pt --name gelan-c-det --hyp hyp.scratch-high.yaml --min-items 0 --epochs 300 --close-mosaic 10 --freeze 9
```
