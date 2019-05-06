# Mobile Vision, Fast

## Mobile Vision
- Google:
	- **MobileNet**: A. G. Howard, M. Zhu, B. Chen, D. Kalenichenko, W. Wang, T. Weyand, M. Andreetto, and H. Adam. Mobilenets: Efficient convolutional neural networks for mobile vision applications. CoRR 2017
		- Depthwise separable
		- Input: DF x DF x M, output: DF x DF x N, kernel size: DK
		- Traditional: DK^2 * M * N * DF^2
		- DS:
			- DK x DK x 1 kernel: DK^2 * M * DF^2
			- 1 x 1 x N kernel: M * N * DF^2
	- **MobileNet-V2**: M. Sandler, A. G. Howard, M. Zhu, A. Zhmoginov, and L. Chen. Inverted residuals and linear bottlenecks: Mobile networks for classification, detection and segmentation. CVPR 2018
		- SSDLite, Mobile DeepLabv3
		- Linear bottlenecks
		- Inverted Residuals
- **ShuffleNet**: X. Zhang, X. Zhou, M. Lin, and J. Sun. ShuffleNet: An extremely efficient convolutional neural network for mobile devices. CVPR 2018
	- Traditional Bottleneck: ReLU[x + (conv1x1 BN-ReLU DWconv3x3 BN-ReLU conv1x1 BN)]
	- ShuffleNet: ReLU[x + (**Gconv**1x1 BN-ReLU **Channel-Shuffle** DWconv3x3 BN-ReLU **Gconv**1x1 BN)]

## Fast
- Separable:
	-  F. Chollet. Xception: Deep learning with depthwise separable convolutions. CVPR 2017

## Small/Compress
- **Song Han**:
	- S. Han, H. Mao, and W. J. Dally. Deep compression: Compressing deep neural networks with pruning, trained quantization and huffman coding. 2015
	- **Squeezenet**: F. N. Iandola, S. Han, M. W. Moskewicz, K. Ashraf, W. J.Dally, and K. Keutzer. Squeezenet: Alexnet-level accuracy with 50x fewer parameters and 0.5 mb model size. 2016
	- S. Han, J. Pool, J. Tran, and W. Dally. Learning both weights and connections for efficient neural network. NIPS'15
- Quantization:
	- D. Soudry, I. Hubara, and R. Meir. Expectation backpropagation: Parameter-free training of multilayer neural networks with continuous or discrete weights. NIPS'14
	- M. Rastegari, V. Ordonez, J. Redmon, and A. Farhadi. Xnornet: Imagenet classification using binary convolutional neural networks. ECCV'16
	- J. Wu, C. Leng, Y. Wang, Q. Hu, and J. Cheng. Quantized convolutional neural networks for mobile devices. CVPR'16
	- A. Zhou, A. Yao, Y. Guo, L. Xu, and Y. Chen. Incremental network quantization: Towards lossless cnns with lowprecision weights. 2017
	-  S. Zhou, Y. Wu, Z. Ni, X. Zhou, H. Wen, and Y. Zou. Dorefa-net: Training low bitwidth convolutional neural networks with low bitwidth gradients. 2016
- Factorization:
	- M. Jaderberg, A. Vedaldi, and A. Zisserman. Speeding up convolutional neural networks with low rank expansions. 2014
	- J. Jin, A. Dundar, and E. Culurciello. Flattened convolutional neural networks for feedforward acceleration.
- W. Wen, C. Wu, Y. Wang, Y. Chen, and H. Li. Learning structured sparsity in deep neural networks. NIPS'16
