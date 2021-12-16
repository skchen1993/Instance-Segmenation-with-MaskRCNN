NYCU VRDL hw3 : use MaskRCNN for nuclei instance segmentation

[Roport is here!!](https://drive.google.com/file/d/13a14cF253CwnXkNg_hnNqUOrDvI3w5Bt/view?usp=sharing)

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
- Download project:
 `git clone https://github.com/skchen1993/VRDL_3_MaskRCNN.git`  
- Install mmdetection:  
  Follow the official setup instruction in mmdetection github ([link](https://github.com/open-mmlab/mmdetection/blob/master/docs/en/get_started.md))  
  
- Download annotayion files:  
[Annotation file](https://drive.google.com/drive/folders/1Ef7VlM0ZSpsSWA4JDs-y_N9nVYlcEDux?usp=sharing)    
Download the annotation files and put them into `./data/coco/annotations/`  

- Download model weight:    
[checkpoints]()  
Download the model weight and put them into `./checkpoints`   
   


###  Model config setting
check the model config file in `./configs/mask_rcnn/VRDL_HW3_nuclei.py`  
modified the `work_dir`, `load_from`, `ann_file`  


### Training
- Training the model
  First, download the ResNext101 pretrained model([here](https://github.com/open-mmlab/mmdetection/tree/master/configs/mask_rcnn)) weight and then put it into `./checkpoints/`   , and remember to modified the  `load_from` path in model config.
  
- use command below to train  
  `./tools/dist_train.sh ./configs/mask_rcnn/VRDL_HW3_nuclei.py {number of GPU}`  
  
### Testing
- Prepare the trained model weight and put it into `./checkpoints/`, and remember to modified the  `load_from` path in model config.
- use command below to test and generate json.file    
`python tools/test.py ./configs/mask_rcnn/VRDL_HW3_nuclei.py {path of trained model}  --format-only --options "jsonfile_prefix={path of result}" `

- if you want to visualize testing result, cau use command below:  
 `python tools/test.py ./configs/mask_rcnn/VRDL_HW3_nuclei.py {path of trained model} --eval bbox segm --show`   
 
 
  
  


# Reference
[mmdetection](https://github.com/open-mmlab/mmdetection)  
