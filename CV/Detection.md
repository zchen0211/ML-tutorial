# Detection, Semantic-Segmentation

## Metrics
- mAP (average of the maximum precisions at different recall values)

## Benchmarks
- **COCO**: T.-Y. Lin, M. Maire, S. Belongie, J. Hays, P. Perona, D. Ramanan, P. Dollar, and C. L. Zitnick. Microsoft coco: Common objects in context. ECCV 2014

## Detection
- A very good blog (Lilian Weng, OpenAI):
	- https://lilianweng.github.io/lil-log/2017/10/29/object-recognition-for-dummies-part-1.html
- FAIR, previous MSR:
	- **R-CNN**: R. Girshick, J. Donahue, T. Darrell, and J. Malik. Rich feature hierarchies for accurate object detection and semantic segmentation. CVPR 2014
		- **PASCAL-VOC: 54.2% (2007), 50.2% (2010), 49.6% (2012)**
		- **ImageNet 200: 31.4%**
	- **SPP**: K. He, X. Zhang, S. Ren, and J. Sun. Spatial pyramid pooling in deep convolutional networks for visual recognition. ECCV 2014
	- **Fast R-CNN**: R. Girshick. Fast R-CNN. ICCV 2015
		- Backbone CNN;
		- RoIPool to a fixed spatial extent W x H (7x7)
		- Faster, better accuracy
		- Loss 1: (K+1) class on each RoI;
		- Loss 2: L1-loss; bounding-box regression (x, y, w, h);
		- **PASCAL-VOC: 66.9% (2007), 66.1% (2010), 65.7% (2012)**
		- **COCO: mAP 35.9%**
	- **Faster R-CNN**: S. Ren, K. He, R. Girshick, and J. Sun. Faster r-cnn: Towards real-time object detection with region proposal networks. NIPS 2015 
		- https://github.com/mahyarnajibi/fast-rcnn-torch
		- https://github.com/chenyuntc/simple-faster-rcnn-pytorch
		- Two stage
		- Stage 0: backbone CNN (VGG, ResNet)
		- Stage 1: **RPN** (attention)
			- Anchor k -> 4k; (x, y, w, h), WHk anchors in total;
			- Regression loss;
			- Positives: IoU with largest overlap with ground-truth and >.7 with any ground truth;
		- Stage 2: R-CNN
		- **PASCAL-VOC mAP: 73.2% (2007), 73.2% (2012)**
	- **R-FCN**: J. Dai, Y. Li, K. He, and J. Sun. R-fcn: Object detection via region-based fully convolutional networks. NIPS 2016
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
		- Reduce loss for well-classified classes; focus on harder classes;
		- Foreground/background imbalance;
- One-stage detector:
	- SSD:
		- W. Liu, D. Anguelov, D. Erhan, C. Szegedy, and S. Reed. SSD: Single shot multibox detector. ECCV 2016
			- Improves YOLO by using default bounding boxes
		- C.-Y. Fu, W. Liu, A. Ranga, A. Tyagi, and A. C. Berg. DSSD: Deconvolutional single shot detector. 2016
	- YOLO:
		- **YOLO**: J. Redmon, S. Divvala, R. Girshick, and A. Farhadi. You only look once: Unified, real-time object detection. CVPR 2016
		- **YOLOv2**: J. Redmon and A. Farhadi. YOLO9000: Better, faster, stronger. CVPR 2017
			- Multi-scale training
			- DarkNet-19
		- **YOLOv3**: J. Redmon and A. Farhadi. Yolov3: An incremental improvement. 2018
- Proposals:
	- **Selective Search**: J. R. Uijlings, K. E. van de Sande, T. Gevers, and A. W. Smeulders. Selective search for object recognition. IJCV 2013
	- **EdgeBoxes**:  C. L. Zitnick and P. Dollar. Edge boxes: Locating object proposals from edges. ECCV 2014
	- **DeepMask**:
		- P. O. Pinheiro, R. Collobert, and P. Dollar. Learning to segment object candidates. NIPS 2015
		- P. O. Pinheiro, T.-Y. Lin, R. Collobert, and P. Dollar. Learning to refine object segments. ECCV 2016
	- **RPN**
- **MSRA**:
	- 

## Pose Estimation
- OpenPose: https://github.com/CMU-Perceptual-Computing-Lab/openpose

## Semantic Segmentation
- **U-Net**, Olaf Ronneberger, Philipp Fischer, Thomas Brox: Convolutional Networks for Biomedical Image Segmentation, MICCAI 2015
- **FCN**: J. Long, E. Shelhamer, and T. Darrell. Fully convolutional networks for semantic segmentation. CVPR 2015
	- https://github.com/wkentaro/pytorch-fcn
	- https://github.com/shelhamer/fcn.berkeleyvision.org
	- Pyramid (like SSD)