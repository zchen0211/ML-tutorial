# Video Understanding

## Benchmarks
- Google:
	- **Sports-1M**: Andrej Karpathy; George Toderici; Sanketh Shetty; Thomas Leung; Rahul Sukthankar; Li Fei-Fei. Large-scale Video Classification with Convolutional Neural Networks. CVPR 2014;
		- 1 Million videos, 487 classes x (1k-3k) videos per class; test: 70% training, 10% val, 20% testing;
		- 360 x 640 resolution
	- **YouTube-8M**: Sami Abu-El-Haija, Nisarg Kothari, Joonseok Lee, Paul Natsev, George Toderici, Balakrishnan Varadarajan, Sudheendra Vijayanarasimhan. YouTube-8M: A Large-Scale Video Classification Benchmark
		- https://research.google.com/youtube8m/
		- 6.1 Million, 350,000 hours
		- 2.6 billion audio/visual features
		- 3,862 classes (from knowledge graph: https://developers.google.com/knowledge-graph/)
	- **Kinetics**: Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset, CVPR 2017
		- 240k train, 20k val, 400 action classes, 10s each clip;
		- Classification;
		- De-duplicate: word synonymy; class by class, a clip per video + inception-V1 feature after average pooling, 25 sampled frames, cosine similarity matrix;
		- Dataset bias: gender
		- Baseline: ConvNet + LSTM, Two-Stream, 3D ConvNets
	- W. Kay, J. Carreira, K. Simonyan, B. Zhang, C. Hillier, S. Vijayanarasimhan, F. Viola, T. Green, T. Back, P. Natsev, et al. The kinetics human action video dataset. 2017
	- **AVA**: C. Gu, C. Sun, D. A. Ross, C. Vondrick, C. Pantofaru, Y. Li, S. Vijayanarasimhan, G. Toderici, S. Ricco, R. Sukthankar, et al. AVA: A video dataset of spatio-temporally localized atomic visual actions. CVPR 2018
		- https://research.google.com/ava/index.html
		- 80 categories
		- 15 min long clips from 430 movies
		- 1.62M action labels
- Other large-scale:
	- **Something something**: Goyal, R., Kahou, S.E., Michalski, V., Materzynska, J., Westphal, S., Kim, H., Haenel, V., Fruend, I., Yianilos, P., Mueller-Freitag, M., et al.: The something something video database for learning and evaluating visual common sense. ICCV 2017
		- Need to understand physical interactions
	- **Activitynet**: F. Caba Heilbron, V. Escorcia, B. Ghanem, and J. C. Niebles. Activitynet: A large-scale video benchmark for human activity understanding. CVPR 2015
	- **Charades**: Sigurdsson, G.A., Varol, G., Wang, X., Farhadi, A., Laptev, I., Gupta, A.: Hollywood in homes: Crowdsourcing data collection for activity understanding. ECCV 2016
- **HMDB-51**: H. Kuehne, H. Jhuang, E. Garrote, T. Poggio, and T. Serre. HMDB: a large video database for human motion recognition. ICCV 2011
	- 51 categories, 7,000 annotated
- **UCF-101**: K. Soomro, A. R. Zamir, and M. Shah. Ucf101: A dataset of 101 human actions classes from videos in the wild. 2012
	- 101 categories, 13k clips, 27 hours
- **MPII-Pose**: M. Andriluka, L. Pishchulin, P. Gehler, and B. Schiele. 2d human pose estimation: New benchmark and state of the art analysis. CVPR 2014
	- 25k images, 40k people
	- 410 human activities
- **ACT**: X. Wang, A. Farhadi, and A. Gupta. Actions transformations. CVPR 2016
- M. Monfort, A. Andonian, B. Zhou, K. Ramakrishnan, S.A. Bargal, Y. Yan, L. Brown, Q. Fan, D. Gutfreund, C. Vondrick, et al. Moments in time dataset: one million videos for event understanding. TPAMI, 2019.
- **Slac**: H. Zhao, Z. Yan, H. Wang, L. Torresani, and A. Torralba. Slac: A sparsely labeled dataset for action classification and localization. 
- **YouCook II**: L. Zhou, C. Xu, and J. J. Corso. Towards automatic learning of procedures from web instructional videos. AAAI 2018
- **Cooking**: David Chen, William Dolan. Collecting Highly Parallel Data for Paraphrase Evaluation. ACL 2011
	- 2,089 videos; 85,550 English descriptions
- A. Rohrbach, M. Rohrbach, W. Qiu, A. Friedrich, M. Pinkal, and B. Schiele. Coherent multi-sentence video description with variable level of detail. GCPR 2014

## Classification, Action Recognition
- FAIR:
	- Non-local Neural Networks, 2018
		- Video classification
		- THW 512 dimension, attention with every other location
		- Softmax sum;
	- SlowFast Networks for Video Recognition, CVPR 2019 Submission
		- Slow pathway: 2 fps;
		- Fast pathway: 16 fps; lightweight computation; (same net, small hyper)
	- New attention:
		- https://github.com/takatosp1/pytorch-CycleGAN-and-pix2pix/commit/d10e1f6b090ee5efb1fa5418c47ba16389f4d4b4#diff-ac5552fd6a3c08ad22387efbe42d137d
- AML:
	- **R(2+1)D**: D. Tran, H. Wang, L. Torresani, J. Ray, Y. LeCun, and M. Paluri. A closer look at spatiotemporal convolutions for action recognition. CVPR 2018
	- **CSN**: Du Tran. Video Classification with Channel-Separated Convolutional Networks. ICCV 2019 submission
		- Bottleneck: 1x1x1 -> 3x3x3 -> 1x1x1
		- ip-CSN: 1x1x1 -> 1x1x1 -> 3x3x3(dw) -> 1x1x1
		- ir-CSN: 1x1x1 -> 1x1x1 -> 3x3x3(dw) -> 1x1x1
		- Group Convolution.
		- Experiments:
			- Kinetics: 71.8% (ip-CSN, res-101), 71.3% (ir-CSN, res-101), 70.6% (ResNet3D); 78.5% top1, 93.4% top5 with Sports1M pretrain
			- Sports1M: 75.5%, 92.7% (ir-CSN res-152)
- Google:
	- **S3D**: S. Xie, C. Sun, J. Huang, Z. Tu, and K. Murphy. Rethinking spatiotemporal feature learning for video understanding. ECCV 2018
		- I3D (inflate the 2D conv in Inception)
		- Bottom-Heavy-I3D
		- Top-Heavy-I3D (faster, more accurate)
		- S3D: 7x7x7 Conv -> 1x7x7 Conv + 7x1x1 Conv
		- With optical-flow: 77.2% top-1, 93.0% top-5
	- VideoBERT: A Joint Model for Video and Language Representation Learning. ICCV 2019
		- Vector-quantization: S3D for feature extraction;
		- WordPiece for text (ASR API);
		- BLEU-4 1.42 to 5.42 on YouCook II;
- MSRA:
	- X Zhu, Y Wang, J Dai, L Yuan, and Y Wei. Flow-Guided Feature Aggregation for Video Object Detection. ICCV'17
	- X Zhu, J Dai, L Yuan, and Y Wei. Towards High Performance Video Object Detection. CVPR'18 
	- Z Zhang, Dazhi Cheng, X Zhu, S Lin, and J Dai. Integrated Object Detection and Tracking with Tracklet-Conditioned Detection. 2018
- Instructional:
	- J. Malmaud, J. Huang, V. Rathod, N. Johnston, A. Rabinovich, and K. Murphy. What’s cooking? interpreting cooking videos using text, speech and vision. NAACL 2015
	- J.-B. Alayrac, P. Bojanowski, N. Agrawal, J. Sivic, I. Laptev, and S. Lacoste-Julien. Unsupervised learning from narrated instruction videos. CVPR 2016
- **P3D**: Z. Qiu, T. Yao, , and T. Mei. Learning spatio-temporal representation with pseudo-3d residual networks. ICCV 2017
- **ARTNet**: H. Wang and C. Schmid. Action recognition with improved trajectories. CVPR 2018
- K. Hara, H. Kataoka, and Y. Satoh. Can spatiotemporal 3d cnns retrace the history of 2d cnns and imagenet? CVPR 2018
- **MFNet**: Y. Chen, Y. Kalantidis, J. Li, S. Yan, and J. Feng. Multi-fiber networks for video recognition. In ECCV, 2018.

## Multimodal
- Y. Aytar, C. Vondrick, and A. Torralba. Soundnet: Learning sound representations from unlabeled video. NIPS 2016.
- A. Owens, P. Isola, J. McDermott, A. Torralba, E. H. Adelson, and W. T. Freeman. Visually indicated sounds. CVPR 2016
- A. Owens, J. Wu, J. H. McDermott, W. T. Freeman, and A. Torralba. Ambient sound provides supervision for visual learning. ECCV 2016

## Video Caption
- Video caption: https://github.com/xiadingZ/video-caption.pytorch
- R. Krishna, K. Hata, F. Ren, L. Fei-Fei, and J. C. Niebles. Dense-Captioning events in videos. ICCV 2017
- **SOA**: L. Zhou, Y. Zhou, J. J. Corso, R. Socher, and C. Xiong. End-to-end dense video captioning with masked transformer. CVPR 2018
	- SOA on YouCook II dataset

## Video Prediction
- Google, Berkeley:
	- M. Babaeizadeh, C. Finn, D. Erhan, R. H. Campbell, and S. Levine. Stochastic variational video prediction. ICLR 2018
	- A. X. Lee, R. Zhang, F. Ebert, P. Abbeel, C. Finn, and S. Levine. Stochastic adversarial video prediction. 2018
- FAIR:
	- M. Mathieu, C. Couprie, and Y. LeCun. Deep multi-scale video prediction beyond mean square error. ICLR 2016
	- E. Denton and R. Fergus. Stochastic video generation with a learned prior. ICML 2018
- NVIDIA:
	- **MoCoGAN**: S. Tulyakov, M.-Y. Liu, X. Yang, and J. Kautz. MoCoGAN: Decomposing motion and content for video generation.
- CMU:
	- J. Walker, C. Doersch, A. Gupta, and M. Hebert. An uncertain future: Forecasting from static images using variational autoencoders. ECCV 2016
	- I. Misra, C. L. Zitnick, and M. Hebert. Shuffle and learn: unsupervised learning using temporal order verification. In ECCV, 2016
- MIT:
	- T. Xue, J. Wu, K. Bouman, and B. Freeman. Visual dynamics: Probabilistic future frame synthesis via cross convolutional networks. NIPS 2016
	- C. Vondrick, H. Pirsiavash, and A. Torralba. Generating videos with scene dynamics. In NeurIPS, 2016.

## Legacy, Hand-Designed
- P. Dollar, V. Rabaud, G. Cottrell, and S. Belongie. Behavior recognition via sparse spatio-temporal features. ICCV 2005
- **STIP**: I. Laptev and T. Lindeberg. Space-time interest points. ICCV 2003
- S. Sadanand and J. Corso. Action bank: A high-level representation of activity in video. CVPR 2012
- H. Wang and C. Schmid. Action recognition with improved trajectories. ICCV 2013
