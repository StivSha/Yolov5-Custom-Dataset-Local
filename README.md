<h1 align="center">Yolov5 Custom Dataset in Local (Easy) </h1>

 Today I will explain how to use yolov5 with a custom dataset. <br> 
It will be a easy version to how to do it.
## Steps
- [Installation LabelImg](#Installation-LabelImg)
- [Creation of folders](#Creation-of-folders)
- [Installation of Yolov5](#Installation-of-Yolov5)
- [Creation Custom Dataset](#Creation-Custom-Dataset)
- [Creation Dataset.yaml](#Creation-Dataset.yaml)
- [Training Custom Dataset](#Training-Custom-Dataset)
- [Testing Custom Dataset](#Testing-Custom-Dataset)

# Let's Start

## Installation LabelImg

To Build and Open, just run
```
$ sudo install labelImg 
$ labelImg
```

## Creation of folders

Go in the Deskopt and create a folder called " *Custom Dataset* "

<img src="https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/Creation%20Cartel1.png" width="500" height="250">

In the Folder called " *Custom Dataset* " create a folder called " *Dataset* "

<img src="https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/Creation%20Cartel2.png" width="500" height="250">

In the Folder called " *Dataset* " create 2 folders called " *images* " and " *labels* "

<img src="https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/Creation%20Cartel3.png" width="500" height="250">

## Installation of Yolov5

To Build and Setup, just run in <b> /home/stiven/Scrivania/CUSTOM DATASET </b>

```
$ cd home/stiven/Scrivania/CUSTOM\ DATASET/  "EXAMPLE" 
$ git clone https://github.com/ultralytics/yolov5
$ cd yolov5
$ pip install -r requirements.txt or sudo install -r requirements.txt  or pip3 install -r requirements.txt 
```

<img src="https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/Yolov5%20folder.png" width="500" height="250">

## Creation Custom Dataset

Open labelImg: 
```
$ labelImg
```
<img src="https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/label.png" width="500" height="250">

CLICK IN THE BLOCK LEFT UNTIL IS WRITED YOLO 

<img src="https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/label2.png" width="500" height="250">

AFTER OPEN AN IMAGE AND CREATE A RECTBOX, AFTER WRITE THE NAME OF THE CLASS

<img src="https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/label3.png" width="500" height="250">

<b> SAVE ALL IMAGES INTO THE IMAGES FOLDER OF THE DATASET ("home/stiven/Scrivania/CUSTOM DATASET/Dataset/images" EXAMPLE),
      ALL LABELS CREATED WITH LABELIMG (TXT FILES) SAVE IT INTO THE LABELS FOLDER OF THE DATASET ("home/stiven/Scrivania/CUSTOM DATASET/Dataset/labels" EXAMPLE)

## Creation Dataset.yaml
<b>  Go into the Path </b> 
 
<img src="https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/Path.png" width="500" height="250">  

In this Example: /home/stiven/Scrivania/CUSTOM DATASET/Dataset

<b> Create a File in the Dataset Cartel called: " *Dataset.yaml* "  </b>

<b> Open it and write </b>
  
```yaml
path: /home/stiven/Scrivania/CUSTOM DATASET/Dataset
train: images/
val: images/
nc: "Number of classes"
names: ['Class, Class2, Class3 ...']
```
 
<img src="https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/dataset.png" width="500" height="250">  



## Training Custom Dataset
for <b> TRAIN GO INTO THE YOLOV5 FOLDER, OPEN TERMINAL</b> ("/home/stiven/Scrivania/CUSTOM DATASET/Yolov5" EXAMPLE)
  
```
$  python3 train.py --data ../dataset/NAME.yaml --weights yolov5s.pt
```  
If you don't have yolov5s.pt download it in: https://github.com/ultralytics/yolov5/releases
and after save it in the Yolov5 Folder ("/home/stiven/Scrivania/CUSTOM DATASET/Yolov5" Example)


## Testing Custom Dataset
  <b> When the Train FINISHED go into the folder ("/home/stiven/Scrivania/CUSTOM DATASET/Yolov5/runs/train/exp... EXAMPLE)
          take the LAST EXP, open it and go into WEIGHTS folder
    copy LAST.PT OR BEST.PT   </b>
          
    
<img src="https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/best.png" width="500" height="250">     
    
<b>PASTE THE FOLDER "LAST.PT OR BEST.PT" IN THE YOLOV5 FOLDER </b>
 
<img src="https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/best2.png" width="500" height="250">     

for <b> TEST GO INTO THE YOLOV5 FOLDER, OPEN TERMINAL</b> , just run
  in this example was /home/stiven/Scrivania/CUSTOM DATASET/Yolov5
  
```
$   python3 detect.py --source PATH, EXAMPLE:"../scene0-30_view\=12.jpeg" (THE IMAGE YOU WANNA TEST)  --weights best.pt or last.pt
```  
<b> When the Test FINISHED go into the folder /home/stiven/Scrivania/CUSTOM DATASET/Yolov5/runs/DETECT/exp... </b>
