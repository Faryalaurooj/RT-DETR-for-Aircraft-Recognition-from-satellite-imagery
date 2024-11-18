# RT-DETR-for-Aircraft-Recognition-from-satellite-imagery

Real-Time Detection Transformer (RT-DETR) will be used for Aircraft Recognition task by using my own custom dataset of satellite imagery 

![image](https://github.com/user-attachments/assets/73b3396a-44c7-4429-b921-9bba9faae597)

The RT-DETR model architecture diagram shows the last three stages of the backbone {S3, S4, S5} as the input to the encoder. The efficient hybrid encoder transforms multiscale features into a sequence of image features through intrascale feature interaction (AIFI) and cross-scale feature-fusion module (CCFM). The IoU-aware query selection is employed to select a fixed number of image features to serve as initial object queries for the decoder. Finally, the decoder with auxiliary prediction heads iteratively optimizes object queries to generate boxes and confidence scores. 




`
# Setting up 
To download a model from ultralatytics. 1) activate an environmet 2) write python 3) copy the command from the ultralytics to load model
`
conda activate yolov10
python 
>>> from ultralytics import RTDETR
>>> model = RTDETR("rtdetr-l.pt")`
or if you donot have an environment

Create new environment for your model
` conda create --name DETR `
>>> pip install requirements
>>> Activate new environment
` conda activate DETER `

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

