<p align="center">
  <a href="https://github.com/codePerfectPlus/Mask-RCNN-Implementation"><img src="https://capsule-render.vercel.app/api?type=rect&color=009ACD&height=100&section=header&text=Mask-R-Implementation&fontSize=60%&fontColor=ffffff" alt="website title image"></a>
  <h2 align="center">👉 Mask RCNN Implementation on LabelMe Annotations Data 👈</h2>
</p>

<p align="center">
<img src="https://img.shields.io/badge/Python-3.8.5-lightgrey?style=for-the-badge" alt="repo language">
<a href="https://github.com/codePerfectPlus/Mask-RCNN-Implementation/stargazers"><img src="https://img.shields.io/github/stars/codePerfectPlus/Mask-RCNN-Implementation?style=for-the-badge" alt="github stars"></a>
<a href="https://github.com/codePerfectPlus/Mask-RCNN-Implementation/network/members"><img src="https://img.shields.io/github/forks/codePerfectPlus/Mask-RCNN-Implementation?style=for-the-badge" alt="github forks"></a>
<img src="https://img.shields.io/github/languages/code-size/codePerfectPlus/Mask-RCNN-Implementation?style=for-the-badge" alt="code size">

## Prepare Data

### DataSet Folder Structure

[Labelme](https://github.com/wkentaro/labelme/) Annotations tools

```
- Data_folder
    - train
        - img1.jpg
        - img1.json
        - img2.jpg
        - img2.json
        ...
    - val
        - img3.jpg
        - img2.json
        - img4.jpg
        - img4.json
        ...
```

## Training 

```python
# Configuration
# Adjust according to your Dataset and GPU

IMAGES_PER_GPU = 2 # 1
 
# Number of classes (including background)
NUM_CLASSES = 1 + 1 # Background

# typically after labeled, class can be set from Dataset class
# if you want to test your model, better set it corectly based on your trainning dataset

# Number of training steps per epoch
STEPS_PER_EPOCH = 100
```
The easiest way to get started is to simply try out on Colab: [<img src="https://colab.research.google.com/assets/colab-badge.svg" align="center">](https://colab.research.google.com/drive/142qQPGuzz7AemMVDl8iKw0fEe-hnIL1p?usp=sharing)
### Training the model on Custom Data

```bash
python customTrain.py train --dataset=path_to_Data_folder --weights=coco
```

### ReTraining from Last Checkpoint

```bash
python customTrain.py train --dataset=path_to_Data_folder --weights=last
```

## Requirements

- Python3.6
- Tensorflow-gpu==1.15
- keras==2.0.8


For more details check [Mask RCNN Repo](https://github.com/matterport/Mask_RCNN)
