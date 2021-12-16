<h1 align="center">Yolov5-with-Custom-Dataset-easy</h1>

Today I will explain how to use yolov5 with a custom dataset
## Steps
- [Installation LabelImg](#Installation-LabelImg)
- [Creation of folders](#Creation-of-folders)
- [Installation of Yolov5](#Installation-of-Yolov5)
- [Creation Custom Dataset](#Creation-Custom-Dataset)
- [Creation Dataset.yaml](#Creation-Dataset.yaml)
- [Training Custom Dataset](#Training-Custom-Dataset)
- [Testing Custom Dataset](#Testing-Custom-Dataset)

# Let's Start

### Installation LabelImg

To Build and Open, just run
```
$ sudo install labelImg or pip install labelImg or pip3 install labelImg
$ labelImg
```

### Creation of folders

Go in the Deskopt and create a folder called " *Custom Dataset* "
![Creation Cartel](https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/Creation%20Cartel1.png)

In the Folder called " *Custom Dataset* " create a folder called " *Dataset* "

![Creation Cartel](https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/Creation%20Cartel2.png)

In the Folder called " *Dataset* " create 2 folders called " *images* " and " *labels* "

![Creation Cartel](https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/Creation%20Cartel3.png)

### Installation of Yolov5

To Build and Setup, just run in <b> /home/stiven/Scrivania/CUSTOM DATASET <b>
  ![Path](https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/Path.png)
```
$ git clone https://github.com/ultralytics/yolov5
$ cd yolov5
$ pip install -r requirements.txt or sudo install -r requirements.txt  or pip3 install -r requirements.txt 
```
https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/Yolov5%20folder.png

### Creation Custom Dataset

# TODO

### Creation Dataset.yaml
<b>  Go into the Path <b> 
![Path](https://github.com/StivSha/Yolov5-with-Custom-Dataset-easy/blob/main/Tutorial%20Images/Path.png)

In this Example: /home/stiven/Scrivania/CUSTOM DATASET/Dataset

<b> Create a File in the Dataset Cartel called: " *Dataset.yaml* "  <b>

<b> Open it and write <b>
  
```yaml
path: /home/stiven/Scrivania/CUSTOM DATASET/Dataset
train: images/
val: images/
nc: "Number of classes"
names: ['Class, Class2, Class3 ...']
```


### Training Custom Dataset
for <b> TRAIN GO INTO THE YOLOV5 FOLDER, OPEN TERMINAL<b> , just run
```
$  python train.py --data your_data.yaml --weights any_model.pt
```  

### Testing Custom Dataset
