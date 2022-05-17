# Rapid Detection of Juvenile White Sharks in the Costal Zone

This repository contains the necessary files to implement a modified version of the YOLOv5 model to draw bounding 
boxes around instances of juvenile white sharks near the surface of the ocean. The YOLOv5 repository can be found 
here: https://github.com/ultralytics/yolov5. For this project, the custom model was trained on drone footage captured 
off the coast of Santa Barbra, CA. 

To utlize the three files, first move shark_data.yaml to the data sub-directory of the YOLOv5 direcotry. 
Then, at training time specify the three in the command line argument (for example: python train.py --cfg yolov5m.yaml 
--batch 32 --epochs 150 --data shark_data.yaml --weights yolov5m.pt --freeze 10 --name yolo_shark_det_150). Note, you 
must have your data set directory in the same parent directory as the YOLOv5 model. 

For baseline testing, we used the YOLOv5m architecture with a batch size of 32 and froze the backbone that was pretrained 
on the Pascal VOC dataset to iterate quickly. Training was done on an AWS EC2 instance to further speed up the process. 
