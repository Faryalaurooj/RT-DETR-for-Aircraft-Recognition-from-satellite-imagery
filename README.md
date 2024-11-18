# RT-DETR-for-Aircraft-Recognition-from-satellite-imagery
Real-Time Detection Transformer (RT-DETR) will be used for Aircraft Recognition task by using my own custom dataset of satellite imagery 

Create new environment for your model
` conda create --name DETR `
Activate new environment
` conda activate DETER `
# Stting up 
To download a model from ultralatytics. 1) activate an environmet 2)write python 3) copy the command from the ultralytics to load model
`
(base) faryal@faryal-pc:~/Downloads/RT-DETR$ conda activate yolov10
(yolov10) faryal@faryal-pc:~/Downloads/RT-DETR$ python 
Python 3.9.19 (main, May  6 2024, 19:43:03) 
[GCC 11.2.0] :: Anaconda, Inc. on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from ultralytics import RTDETR
>>> model = RTDETR("rtdetr-l.pt")`

# Load a COCO-pretrained RT-DETR-l model and train it on the COCO8 example dataset for 100 epochs
yolo train model=rtdetr-l.pt data=coco8.yaml epochs=100 imgsz=640

when we run this command , first of all the model downloads weights file .pt of the RT_DETR from Downloading https://github.com/ultralytics/assets/releases/download/v8.2.0/rtdetr-l.pt to 'rtdetr-l.pt'and then it trains the models on the data that we have specified

# Load a COCO-pretrained RT-DETR-l model and run inference on the 'bus.jpg' image
yolo predict model=rtdetr-l.pt source=path/to/bus.jpg

# Train on Custom Dataset
Now if we want to train the model on our custom aircraft data then we need to have our dataset in this format output-train, test, val folders then inside train-images, labels similarly for the remaining
once data is adjusted in this format then we can have a yaml file that defines our data path and also defines our classes, like in our case here we have following 10 classes : 
F_16
F_35
SU_27
WB
Other
Pens
Ammo
A10
Rafale
F_15

