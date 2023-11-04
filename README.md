# Cross-Attention Vision Transformer for Few-Shot Semantic Segmentation

Thanks for your interest in our work! This is the official implementation for our "*Cross-Attention Vision Transformer for Few-Shot Semantic Segmentation
*".

> **Abstract:** *Computer vision has experienced remarkable advancements thanks to the rapid progress of deep learning techniques and the availability of extensive reference datasets. However, training models in the presence of limited annotated data remains a challenging task due to data dependency. To address this issue, few-shot learning has emerged as a promising solution, particularly in domains such as medical image analysis, in which accurate segmentation is crucial despite limited sample availability. Typically, a few-shot semantic segmentation model consists of a CNN encoder, a CNN decoder, and a simple classifier that must be learned in most of the existing approaches. However, an effective adaptation of a model considering all three components to the new class is very difficult since there are only a few support set images available. In this work, we focus on reducing meta-learning task complexity by concentrating only on the classifier, using a pre-trained encoder-decoder. Thus, we propose a new method, named Cross-Attention in Classifier Weight Transformer (Cross-CWT), that explores cross-attention to dynamically adjust the classifier’s weights to each query image. Experimental results show that the proposed approach can achieve competitive performance compared to other state-of-the-art methods with lesser training costs, making the few-shot semantic segmentation task much more tractable.*

## Get Started

### Environment

- torch==1.6.0
- numpy==1.19.1
- cv2==4.4.0
- pyyaml==5.3.1

Other configurations can also work, although the outcomes may differ slightly.

### Dataset
Please download the following datasets:

+ PASCAL-5<sup>i</sup>: [**PASCAL VOC 2012**](http://host.robots.ox.ac.uk/pascal/VOC/voc2012/) and [**SBD**](http://home.bharathh.info/pubs/codes/SBD/download.html)

+ COCO-20<sup>i</sup>: [**COCO 2014**](https://cocodataset.org/#download).

We follow the lists generation and process dataset as that in [PFENet](https://github.com/dvlab-research/PFENet). After processing, please change the "data_root" and "train/val_list" in config files accordingly.

## Architecture


## Scripts

- The general training script
```python
sh scripts/train.sh {data} {split} {[gpu_ids]} {layers} {shots}
```
- Example with 1-shot, ResNet-50, split-0 on PASCAL and GPU device [0].
```python
sh scripts/train.sh pascal 0 [0] 50 1
```
- Inference script
```python
sh scripts/test.sh {data} {shot} {[gpu_ids]} {layers} {split}
```

## References

This repository owes its existence to the exceptional contributions of other projects:

* CWT: https://github.com/zhiheLu/CWT-for-FSS
* PFENet: https://github.com/dvlab-research/PFENet
* PSPNet: https://github.com/hszhao/semseg

Many thanks to their invaluable contributions.

## BibTeX

