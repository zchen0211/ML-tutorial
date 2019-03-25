# Video Understanding

## Benchmarks
- **HMDB-51**: H. Kuehne, H. Jhuang, E. Garrote, T. Poggio, and T. Serre. HMDB: a large video database for human motion recognition. ICCV 2011
- **UCF-101**: K. Soomro, A. R. Zamir, and M. Shah. Ucf101: A dataset of 101 human actions classes from videos in the wild. 2012
- **MPII-Pose**: M. Andriluka, L. Pishchulin, P. Gehler, and B. Schiele. 2d human pose estimation: New benchmark and state of the art analysis. CVPR 2014
- **Activitynet**: F. Caba Heilbron, V. Escorcia, B. Ghanem, and J. C. Niebles.
Activitynet: A large-scale video benchmark for human activity understanding. CVPR 2015
- **ACT**: X. Wang, A. Farhadi, and A. Gupta. Actions ˜ transformations. CVPR 2016
- Google:
	- **Sports-1M**: Andrej Karpathy; George Toderici; Sanketh Shetty; Thomas Leung; Rahul Sukthankar; Li Fei-Fei. Large-scale Video Classification with Convolutional Neural Networks. CVPR 2014;
	- **YouTube-8M**: YouTube-8M: A Large-Scale Video Classification Benchmark
	- **Kinetics**: Quo Vadis, Action Recognition? A New Model and the Kinetics Dataset, CVPR 2017
		- 240k train, 20k val, 400 action classes, 10s each clip;
		- Classification;
		- De-duplicate: word synonymy; class by class, a clip per video + inception-V1 feature after average pooling, 25 sampled frames, cosine similarity matrix;
		- Dataset bias: gender
		- Baseline: ConvNet + LSTM, Two-Stream, 3D ConvNets, 

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