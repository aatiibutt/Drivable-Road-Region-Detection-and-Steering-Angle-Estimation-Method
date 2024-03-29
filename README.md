# [Pixel Level Segmentation Based Drivable Road Region Detection and Steering Angle Estimation Method for Autonomous Driving on Unstructured Roads](https://ieeexplore.ieee.org/abstract/document/9646953)
# Abstract
With the recent emergence of deep learning, computer vision-based applications have demonstrated better applicability in accomplishing driving tasks including drivable road region detection, lane keeping and steering control in self-driving cars. Till recently, numerous lane-marking detection based steering control and lane keeping methods have been proposed to perform autonomous driving on urban well-structured roads. But the matter of fact is that these methods are not feasible on roads where lane markings are not available or faded over time which makes drivable road region detection a crucial task. Moreover, it is highly arduous task to estimate steering angle on deteriorated roads using existing road detection and steering angle estimation methods. To the best of our knowledge, there is no standard benchmark available for drivable road region detection and steering angle estimation on unstructured roads. To this end, we present a large-scale dataset for drivable region road detection, comprising of 15,000-pixel level high quality fine annotations. Alongside dataset, we also present an end-to-end drivable road region detection and steering angle estimation method to ensure the autonomous driving on generalized urban, rural, and unstructured road conditions. The proposed method performs pixel-level segmentation to extract drivable road region and quantifies lane interception to estimate the steering angle of self-driving cars. A comprehensive qualitative and quantitative analysis has been carried out to demonstrate the effectiveness of our proposed dataset, road detection and steering angle estimation methods.
![image](https://user-images.githubusercontent.com/71174927/147829471-91ccb571-7df0-4eae-877e-7ebfa1e45d7f.png)

**End to End semantic segmentation based drivable road detection and steering angle estimation on unstructured roads for self driving cars**
# Discription of Project 
A PyTorch implementation of drivable road region detection and steering angle estimation methods proposed for the autonomous vehicle. The dataset has been taken from [CARL-DATASET](https://carl-dataset.github.io/index/ "CARL-DATASET").

![4 13693_ov](https://user-images.githubusercontent.com/71174927/147745756-f0d18207-a9f5-4b88-872b-73b80f1d3731.jpg)
![5 09315_ov](https://user-images.githubusercontent.com/71174927/147828110-3b6c4ae7-2f37-4adc-9644-d903d4508e05.jpg)
![4 21168_ov](https://user-images.githubusercontent.com/71174927/147745788-05eb26a4-f6a4-4761-87ca-c86e16e761ca.jpg)
![4 24633_ov](https://user-images.githubusercontent.com/71174927/147745840-9df41a44-f05c-4ce5-be18-3a3c221327e4.jpg)
# Prerequisites
1. Windows
2. Anaconda Python
3. PyTorch (https://pytorch.org/get-started/locally/)
4. Albumentations (https://pypi.org/project/albumentations/), (pip install albumentations)
5. Tensorboard (https://pypi.org/project/tensorboard/), (pip install tensorboard)
6. TensorboardX (https://pypi.org/project/tensorboardX/), (pip install tensorboardX)
# Dataset 
We have extended [CARL-Dataset](https://carl-dataset.github.io/index/ "CARL-DATASET") for road detection and segmentation task. As CARL-Dataset has been constructed over video sequences from 100+ cities of Pakistan.

This dataset contains diversities in terms of road types such as 
-   Highways 
-   Motorways 
-   Rural and Urban streets 
-   Provincial 
-   District
-   Hilly and Distressed roads

To ensure generalization of our proposed method, equal subsets of images from video sequences of all types of captured roads have been selected for the training and evaluation of proposed method.

Some samples taken from the video sequences of diverse roadways are shown Below.

![4 24633 - Copy](https://user-images.githubusercontent.com/71174927/147830350-3eaa930d-e5e7-4903-a5aa-ddc76c7fe9bc.jpg)
![P2 00001 - Copy](https://user-images.githubusercontent.com/71174927/147830299-c1aa16a8-eb2b-4d86-8d81-e6b941afba4f.jpg)
![GH011260 0063 - Copy](https://user-images.githubusercontent.com/71174927/147830309-3a35af95-53b9-410f-b582-0f91cfe0cc84.jpg)
## Pixel-Level Annotations of dataset
-  We present a pixel-level annotations benchmark comprising of high resolution (1920×1080 ) images and annotations, having road variability and diversity. 
-  Our dataset consists of 15000 pixel-level annotations, in which each image is labeled as (i) road, and (ii) background, respectively. 
-  To accomplish this task, we have used annotation tool [SuperAnnotate](https://www.superannotate.com/) to perform binary class-based pixel-level annotations. 
-  In our binary class annotations, we have used RGB based colored polygons to represent defined classes. 

Some of the pixel-level annotation examples are depicted below.

![4 24633 jpg___fuse - Copy](https://user-images.githubusercontent.com/71174927/147830360-05e511d9-c18f-4917-bed1-788ee8422c4f.png)
![P2 00001 jpg___fuse - Copy](https://user-images.githubusercontent.com/71174927/147830433-847dbc04-8a81-4724-a4ac-bf1256ea98da.png)
![GH011260 0063 jpg___fuse - Copy](https://user-images.githubusercontent.com/71174927/147830371-9207f2c6-fcfc-476e-893e-3e5444a23e81.png)

**Download the complete dataset from [Here](https://carl-dataset.github.io/index/ "CARL-DATASET")**.

# Description of folders and scripts
My project includes the following files scripts and folders:
-  [CARL_DATASET](https://github.com/aatiibutt/Driveable-Road-Region-Detection--Angle-Estimation/tree/main/CARL_DATASET) folder consists of six subfolders i.e. test, test_label, train, train_label, val, and val_label containing road images and corresponding label images.
-  [runs](https://github.com/aatiibutt/Driveable-Road-Region-Detection--Angle-Estimation/tree/main/runs) folder contains the segmentation logs of the validation data.
-  [train_seg_maps](https://github.com/aatiibutt/Driveable-Road-Region-Detection--Angle-Estimation/tree/main/train_seg_maps) folder is used to save the prediction of the trained model on rondomly selected image during validation process.
-  [utils](https://github.com/aatiibutt/Driveable-Road-Region-Detection--Angle-Estimation/tree/main/utils) folder contains the files such as (i) helper.py and (ii) metrics.py. 
-  [config.py](https://github.com/aatiibutt/Driveable-Road-Region-Detection--Angle-Estimation/blob/main/config.py) is the configation file, where dataset path, name and number of classes mentioned. Check every other parameters in config.py as per your requirement.
-  [dataset.py](https://github.com/aatiibutt/Driveable-Road-Region-Detection--Angle-Estimation/blob/main/dataset.py) includes the functions regarding dataset.
-  [helper.py](https://github.com/aatiibutt/Driveable-Road-Region-Detection--Angle-Estimation/blob/main/utils/helpers.py) includes some helper functions.
-  [train.py](https://github.com/aatiibutt/Driveable-Road-Region-Detection--Angle-Estimation/blob/main/train.py) is used to train the model. 
-  [road_detection_test.py](https://github.com/aatiibutt/Driveable-Road-Region-Detection--Angle-Estimation/blob/main/road_detection_test.py) is used to test the model on randomly selected image.
-  [road_detection_angle_estimation_test.py](https://github.com/aatiibutt/Driveable-Road-Region-Detection--Angle-Estimation/blob/main/road_detection_angle_estimation_test.py) is used to test the model on the test image and predict the angle. 
-  [SteeringAngleUtils.py](https://github.com/aatiibutt/Driveable-Road-Region-Detection--Angle-Estimation/blob/main/SteeringAngleUtils.py) is used for computing the steering angle against the given test image. 
-  [test_vid.py](https://github.com/aatiibutt/Driveable-Road-Region-Detection--Angle-Estimation/blob/main/test_vid.py) is used to detect driveable road region on given video input. 
-  [model.py](https://github.com/aatiibutt/Driveable-Road-Region-Detection--Angle-Estimation/blob/main/model.py) is used to train the model from scratch.
-  [engine.py](https://github.com/aatiibutt/Driveable-Road-Region-Detection--Angle-Estimation/blob/main/engine.py) is used to save the model as a model.pth.
-  [metrics.py](https://github.com/aatiibutt/Driveable-Road-Region-Detection--Angle-Estimation/blob/main/utils/metrics.py) includes helper functions in order to measure the performance matrics.

# How to run the Python scripts
## For Training 
- Train the model for the first time on the road detection dataset CARL-DATASET. Before starting training, please place the downloaded dataset folders (train, train_labels, test, test_labels, val, and val_labels) in CARL-Dataset directory. After completion, verify the root paths and other configurations in 'config.py'.
```
python train.py --resume-training no
```
## For Testing 
### Test the model on the image 
-  Use this python script to apply pixel level segmentation on any image of your choice.
```
python test_road_detection.py --model-path <path to saved checkpoint/weight file> --input <path to vid>.
```
example: python test.py --model-path model.pth --input abc.jpg
### Test the model on the video 
-  Use this python script to apply pixel level segmentation on any videos of your choice.
```
python test_vid.py --input <path to vid> --model-path <path to saved checkpoint/weight file>.
```
example: python test_vid.py --input DSC_0006.mp4 --model-path model.pth
# Result
### Prediction results of the model over images 
![4 01351](https://user-images.githubusercontent.com/71174927/147828141-769fc8b3-a53c-41c7-b06c-8a3e85635685.jpg)
![4 01351_ov](https://user-images.githubusercontent.com/71174927/147745717-d3065341-ab39-4c1f-8c7a-e3ec09dd443b.jpg)
![4 01351_angle](https://user-images.githubusercontent.com/71174927/147828142-0f12be59-411c-41fd-b653-07c31cc9f93a.jpg)
![430611](https://user-images.githubusercontent.com/71174927/147827952-05d927d2-433a-413b-b881-0df1495cc7df.jpg)
![4 30611_ov](https://user-images.githubusercontent.com/71174927/147827946-8c578d35-8984-46e4-97af-fd4553667882.jpg)
![4 30611_angle](https://user-images.githubusercontent.com/71174927/147827953-33cc81ba-db0e-4305-b31a-b2a192a746cc.jpg)
![4 36892](https://user-images.githubusercontent.com/71174927/147828016-32237704-7e56-438d-9180-f05859b3fba2.jpg)
![4 36892_ov](https://user-images.githubusercontent.com/71174927/147828013-b2af225e-40fe-48fb-90cc-e8021dfde8c0.jpg)
![4 36892_angle](https://user-images.githubusercontent.com/71174927/147828011-aad564df-fbe6-404d-8589-0e47ac0b329e.jpg)


### Prediction results of the model over video

https://user-images.githubusercontent.com/71174927/147828349-4829a38e-8310-4bab-be8e-b1cc58a079e3.mp4

https://user-images.githubusercontent.com/71174927/147775570-bc58cbf2-7bcb-4c8b-9c40-09ffe39feb7f.mp4
 
 
# Citation
- If you follow the code or ideas from our paper, please cite our paper:
```
@ARTICLE{9646953,
  author={Rasib, Marya and Butt, Muhammad Atif and Riaz, Faisal and Sulaiman, Adel and Akram, Muhammad},
  journal={IEEE Access}, 
  title={Pixel Level Segmentation Based Drivable Road Region Detection and Steering Angle Estimation Method for Autonomous Driving on Unstructured Roads}, 
  year={2021},
  volume={9},
  number={},
  pages={167855-167867},
  doi={10.1109/ACCESS.2021.3134889}}
```

# Acknowledgments
This code inspired by [Sovit Ranjan Rath](https://github.com/sovit-123/CamVid-Image-Segmentation-using-FCN-ResNet50-with-PyTorch#readme). Some snippets of steering angle estimation code from [David Tain](https://github.com/dctian/DeepPiCar/blob/master/driver/code/hand_coded_lane_follower.py).
