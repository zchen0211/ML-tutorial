# Classification, Detection

## Classification, Network Design
- **AlexNet** A. Krizhevsky, I. Sutskever, and G. Hinton (AlexNet): ImageNet classification with deep convolutional neural networks. NIPS, 2012.
- **VGGNet** K. Simonyan and A. Zisserman. Very deep convolutional networks for large-scale image recognition (VGGNet): arXiv:1409.1556, 2014
- **GoogleNet** C. Szegedy, W. Liu, Y. Jia, P. Sermanet, S. Reed, D. Anguelov, D. Erhan, V. Vanhoucke, and A. Rabinovich (GoogleNet): Going deeper with convolutions. CVPR, 2015
- **DenseNet**: https://github.com/bamos/densenet.pytorch
- **NIN** Lin, Min, Chen, Qiang, and Yan, Shuicheng (NIN): Network in network. Arxiv, 1312.4400, 2013.
- **FAIR**:
	- Kaiming He, Ross Girshick, Piotr Dollar. Rethinking ImageNet Pre-training. CVPR 2019

## Detection
- FAIR, previous MSR:
	- **R-CNN**: R. Girshick, J. Donahue, T. Darrell, and J. Malik. Rich feature hierarchies for accurate object detection and semantic segmentation. CVPR 2014
	- **Fast R-CNN**: R. Girshick. Fast R-CNN. ICCV 2015
		- RoIPool: faster, better accuracy
	- **Faster R-CNN**: S. Ren, K. He, R. Girshick, and J. Sun. Faster r-cnn:Towards real-time object detection with region proposal networks. NIPS 2015 
		- https://github.com/mahyarnajibi/fast-rcnn-torch
		- https://github.com/chenyuntc/simple-faster-rcnn-pytorch
		- Two stage
		- Stage 1: RPN (attention)
			- Anchor k -> 4k;
			- Regression loss;
			- Positives: IoU with largest overlap with ground-truth and >.7 with any ground truth;
		- Stage 2: R-CNN
	- **FPN**: T.-Y. Lin, P. Dollar, R. Girshick, K. He, B. Hariharan, and S. Belongie. Feature pyramid networks for object detection. CVPR 2017.
	- **Mask R-CNN**: ICCV 2017
		- ROI-Align (improves mask accuracy by 10%-15%): solved quantization error
		- Decouple mask and class
		- Loss: cls + box + mask
			- cls, box (same as faster R-CNN)
			- mask: K * m^2 (K class, m resolution)
		- Experiments:
			- COCO instance segmentation
			- COCO keypoint
		- Speed: 5fps
	- **Detectron**: https://github.com/facebookresearch/Detectron
	- **Focal Loss**: Tsung-Yi Lin Priya Goyal Ross Girshick Kaiming He Piotr Dollar. Focal Loss for Dense Object Detection. ICCV 2017
		- Reduce loss for well-classified classess; focus on harder classes;
		- Foreground/background imbalance;
- One-stage detector:
	- SSD:
		- W. Liu, D. Anguelov, D. Erhan, C. Szegedy, and S. Reed. SSD: Single shot multibox detector. ECCV 2016
		-  C.-Y. Fu, W. Liu, A. Ranga, A. Tyagi, and A. C. Berg. DSSD: Deconvolutional single shot detector. 2016
	- YOLO:
		- J. Redmon, S. Divvala, R. Girshick, and A. Farhadi. You only look once: Unified, real-time object detection. CVPR 2016
		-  J. Redmon and A. Farhadi. YOLO9000: Better, faster, stronger. CVPR 2017
- **FCN**:
	- https://github.com/wkentaro/pytorch-fcn
	- https://github.com/shelhamer/fcn.berkeleyvision.org
- Proposals:
	- **Selective Search**: J. R. Uijlings, K. E. van de Sande, T. Gevers, and A. W. Smeulders. Selective search for object recognition. IJCV 2013
	- **EdgeBoxes**:  C. L. Zitnick and P. Dollar. Edge boxes: Locating object proposals from edges. ECCV 2014
	- **DeepMask**:
		- P. O. Pinheiro, R. Collobert, and P. Dollar. Learning to segment object candidates. NIPS 2015
		- P. O. Pinheiro, T.-Y. Lin, R. Collobert, and P. Dollar. Learning to refine object segments. ECCV 2016
	- **RPN**

## Pose Estimation
- OpenPose: https://github.com/CMU-Perceptual-Computing-Lab/openpose

## Segmentation
- **U-Net**, Olaf Ronneberger, Philipp Fischer, Thomas Brox: Convolutional Networks for Biomedical Image Segmentation, MICCAI 2015