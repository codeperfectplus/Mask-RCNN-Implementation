# Mask-RCNN-Implementation
Mask RCNN Implementation on Custom Data(Labelme)

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