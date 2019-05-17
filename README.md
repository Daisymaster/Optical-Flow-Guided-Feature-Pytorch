# OFF-Action-Recogniton
Optical Flow Guided Feature for Action Recognition-Pytorch

Paper reference [CVPR2018 OFF for Action Recogniton](https://arxiv.org/pdf/1711.11152.pdf)

## DataSet & Weights Preparation
+ Prepare UCF-101 and HMDB51 dataset follow instruction of [tsn-pytorch](https://github.com/yjxiong/tsn-pytorch);
+ Prepare pretrained UCF-101 weights from tsn-pytorch;
+ Follow data split by official website;

## Network Modules
+ Temporal Segment Network (TSN) & DataLoader, follow [tsn-pytorch](https://github.com/yjxiong/tsn-pytorch)
+ Original Optical Flow Guided Feature, follow [caffe prototxt](https://github.com/kevin-ssy/Optical-Flow-Guided-Feature/blob/master/models/ucf101/rgb_off/1/train.prototxt)
+ Sobel Operator, follow [wiki](https://en.wikipedia.org/wiki/Sobel_operator)
+ Temporal Segment Consensus module in basic_ops.py
+ Translated OFF Network in RGB_OFF.py/Flow_OFF.py
+ Rewrite dataset.py to dataset_off.py, for frame sampling interval consistency, as mentioned in the paper Section 4.2, last paragraph;
+

## Evaluate Performance
+ RGB OFF evaluation score [link](https://drive.google.com/file/d/1e5yHqC-BX22lXoSnB2GM2NqINxGbcyId/view?usp=sharing)
+ Flow OFF evaluation score [ling](https://drive.google.com/file/d/1O3P2UH0_kWvhW_0VVBIcsJIk_iX2xJI0/view?usp=sharing)
+ score_fusion.ipynb to fuse scores from RGB and Flow; Try different weight for optimal accuracy;
+ Current best accuracy is 95.24%, which is 0.26% less than 95.5% of the original caffe implementaion [link](https://github.com/kevin-ssy/Optical-Flow-Guided-Feature)
