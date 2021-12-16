NYCU VRDL hw3 : use MaskRCNN for nuclei instance segmentation

[Roport is here!!](https://drive.google.com/file/d/1twQbimZkz0-bdYcr5HEDyhw3WVxKiarY/view?usp=sharing)

# MaskRCNN for nuclei instance segmentation
- nuclei dataset: 24 training image (each with hundreds of mask label), 6 testing image 

## Environment
- Python 3.7.3
- Pytorch 1.7.0
- CUDA 10.2  

## step for producing submission
1. Install requirement
2. Download pretrained model and annotaion files
3. Model config setting
4. Training
5. Testing


### Install requirement
-Download project:
 `git clone https://github.com/skchen1993/VRDL_3_MaskRCNN.git`  
 
-Doenload annotayion files:
[link]()

   
 
   
     
-For data preposses (.mat file)  
 `pip install h5py`  
 
   
Download the SVHN dataset and place them into `VRDL_2_YOLOv5/datasets/images/train/`

###  Model config setting


### Training


### Testing


# Reference
[mmdetection](https://github.com/open-mmlab/mmdetection)  
