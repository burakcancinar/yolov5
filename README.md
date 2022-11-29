<div align="left">
  <p>
    <a align="left" href="http://egerobot.com.tr" target="_blank">
      <img width="850" src="egerobot_logo_01.png"></a>
  </p>

  English | [简体中文](.github/README_cn.md)
  <br>
  <div>
    <a href="https://github.com/ultralytics/yolov5/actions/workflows/ci-testing.yml"><img src="https://github.com/ultralytics/yolov5/actions/workflows/ci-testing.yml/badge.svg" alt="YOLOv5 CI"></a>
    <a href="https://zenodo.org/badge/latestdoi/264818686"><img src="https://zenodo.org/badge/264818686.svg" alt="YOLOv5 Citation"></a>
    <a href="https://hub.docker.com/r/ultralytics/yolov5"><img src="https://img.shields.io/docker/pulls/ultralytics/yolov5?logo=docker" alt="Docker Pulls"></a>
    <br>
    <a href="https://bit.ly/yolov5-paperspace-notebook"><img src="https://assets.paperspace.io/img/gradient-badge.svg" alt="Run on Gradient"></a>
    <a href="https://colab.research.google.com/github/ultralytics/yolov5/blob/master/tutorial.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a>
    <a href="https://www.kaggle.com/ultralytics/yolov5"><img src="https://kaggle.com/static/images/open-in-kaggle.svg" alt="Open In Kaggle"></a>
  </div>

## <div align="left">Forklift and Person Recognation From Video</div>
>This project uses yolov5 and custom dataset to detect forklifts and people.  This dataset can also be created by labeling individually, but a custom dataset has been used to save time.

>Some images for training data

![](images/01FVZIGPUGWI_jpg.rf.272f9ea3336a11f2c4390ccc97244242.jpg)
![](images/01FVZIGPUGWI_jpg.rf.58c3cdf7cf8fff4a71b96cb60a6ebc6e.jpg)

![](images/0PVKVE0CITYQ_jpg.rf.5a59aa224b7dd1742da21618d45dbcf9.jpg)
![](images/0Q86CMPW8GGE_jpg.rf.058d9f3a13922ba2fc4aa1d25cd71f13.jpg)

## <div align="left">Code</div>

```python3
!git clone https://github.com/ultralytics/yolov5  # clone repo
!pip install -U -r yolov5/requirements.txt  # install dependencies
```
>Custom Dataset
```python3
!pip install roboflow

from roboflow import Roboflow
rf = Roboflow(api_key="djen2bv91273ZmVErkfR")
project = rf.workspace("mohamed-traore-2ekkp").project("forklift-dsitv")
dataset = project.version(5).download("yolov5")
```
```python3
%cd /content/yolov5
```
>Training
```python3
!python train.py --img 640 --batch 16 --epochs 30 --data /content/Forklift-5/data.yaml --weights yolov5x.pt
```
 ![](https://github.com/burakcancinar/yolov5/blob/b0b78096096946b4464e3798429a3d88b11149fc/images/graph.png)
  
 ![](https://github.com/burakcancinar/yolov5/blob/d90996013ad1a8ca5290462751a6ff51e3e34271/images/trained_data.png)


>Results
```python3
!python detect.py --weights runs/train/exp2/weights/best.pt --img 640 --conf 0.25 --source /content/forklift.mp4

```


## <div align="center">Youtube Video</div>
<a href="http://www.youtube.com/watch?feature=player_embedded&v=bAzlnjdmSVg
" target="_blank"><img src="http://img.youtube.com/vi/bAzlnjdmSVg/0.jpg" 
alt="Video" width="1280" height="720" border="10" /></a>
