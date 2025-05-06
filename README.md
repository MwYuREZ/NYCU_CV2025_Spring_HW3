# NYCU_CV2025_Spring_HW3
| StudentID |   110550065 |
| --------- | :-----|
| Name  |    尤茂為 |

## Introduction  
In this assignment, we tackle an instance segmentation task on colored medical microscopy images. The goal is to accurately detect and delineate individual cells of four distinct types. 
We build upon the standard `maskrcnn_resnet50_fpn_v2` implementation from TorchVision, but replacement its ResNet50 backbone with a custom Swin-Transformer + FPN encorder. 

## Environment Setup  
Execution environment: Ubuntu 24.04.2
```sh
pip3 install -r requirements.txt  
```

## How to exexute  
Clone the repo  
```sh
git clone https://github.com/MwYuREZ/NYCU_CV2025_Spring_HW3.git
```
Data & Project Structure  
```sh
/NYCU_CV2025_Spring_HW3
├── train_swin.py              # Training script with default anchor settings
├── train_swin_anc.py          # Training script with customized anchors
├── infer_swin.py              # Inference script for default model
├── infer_swin_anc.py          # Inference script for anchor-tuned model
├── /data
│   ├── /test_release          # Test images
│   └── /train                 # Training set (labeled)
│       ├── /<image1_uuid>
│       │   ├── image.tif      # Raw input image
│       │   ├── class1.tif     # Binary mask for cell type 1
│       │   ├── class2.tif     # Binary mask for cell type 2
│       │   ├── class3.tif     # Binary mask for cell type 3
│       │   └── class4.tif     # Binary mask for cell type 4
│       ├── /<image2_uuid>
│       │   └── ...
│       └── ...
```
#### With default anchor setting  
Train:  
```sh
python train_swin.py
```
Test:
```sh
python infer_swin.py
```
#### With customized anchor setting  
Train:  
```sh
python train_swin_anc.py
```
Test:
```sh
python infer_swin_anc.py
```

## Performance Snapshot  


