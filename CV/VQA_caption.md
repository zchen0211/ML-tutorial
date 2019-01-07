# VQA, Image/Video Caption

## Video
- Video caption: https://github.com/xiadingZ/video-caption.pytorch

## VQA
- MSR:
	- Vqa: Visual question answering. ICCV 2015.
- Devi, Dhruv:
	- Visual Dialog. CVPR 2017
- Stanford:
	- Visual genome: Connecting language and vision using crowd- sourced dense image annotations.
- Bottom-up and top-down attention for image captioning and visual question answering. CVPR 2018

## Reasoning
- Kexin Yi, Jiajun Wu, Chuang Gan, Antonio Torralba, Pushmeet Kohli and Joshua B. Tenenbaum. Neural-Symbolic VQA: Disentangling Reasoning from Vision and Language Understanding, NIPS 2018
	- An interpretable VQA model that disentangles language reasoning from visual understanding
	- For visual understanding, first perform objects segmentation and then learn to obtain structural scene representation (with supervision) such as color, size, shape, position.
	- For language reasoning, they learn to translate natural language question into a deterministic program such as filter_shape(scene, large) or count(scene). 
	- Finally, they execute the program on the structural scene representation to obtain the final answer
	- 99.8% on CLEVR