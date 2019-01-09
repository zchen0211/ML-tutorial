# 3D Generative, Reconstruction and Synthesis

## 2D with 3D Input
- Alexey Dosovitskiy, Jost Tobias Springenberg, Maxim Tatarchenko, Thomas Brox. Learning to Generate Chairs, Tables and Cars with Convolutional Networks. PAMI 2017
- Multi-view 3D Models from Single Images with
a Convolutional Network. ECCV 2016
	- Encoder/Decoder
	- Input RGB, output RGB/D conditioned on any shape input (angle, ...)
	- https://github.com/lmb-freiburg/mv3d

## Recurrent
- Jimei Yang. Weakly-supervised Disentangling with Recurrent Transformations for 3D View Synthesis. NIPS 2015
	- Input/output: images
	- https://github.com/jimeiyang/deepRotator
- Christopher B. Choy Danfei Xu? JunYoung Gwak?
Kevin Chen Silvio Savarese. 3D-R2N2: A Unified Approach for Single and Multi-view 3D Object Reconstruction. ECCV 2016
	- Update model with RNN each time with a new image.
	- https://github.com/chrischoy/3D-R2N2

## Template-Based
- Legacy:
	- A.-L. Chauve, P. Labatut, and J.-P. Pons. Robust piecewiseplanar 3d reconstruction and completion from large-scale unstructured point data. CVPR 2010
	- F. Lafarge and P. Alliez. Surface reconstruction through point set structuring. Computer Graphics Forum 2013
	- S. N. Sinha, D. Steedly, R. Szeliski, M. Agrawala, and M. Pollefeys. Interactive 3d architectural modeling from unordered photo collections. TOG 2008
	- A. Bodis-Szomoru, H. Riemenschneider, and L. Van Gool. Fast, approximate piecewise-planar modeling based on sparse structure-from-motion and superpixels. CVPR 2014
- Haibin Huang, Evangelos Kalogerakis, Benjamin Marlin. Analysis and synthesis of 3D shape families via deep-learned generative models of surfaces. Eurographics 2015
- **Voxlet**: Michael Firman, Oisin Mac Aodha, Simon Julier, Gabriel J. Brostow. Structured Prediction of Unobserved Voxels From a Single Depth Image. CVPR 2016
	- Shape prior
	- https://github.com/mdfirman/voxlets
- Jiajun Wu. 3D-INN. ECCV 2016
- S. Tulsiani, H. Su, L. J. Guibas, A. A. Efros, and J. Malik. Learning shape abstractions by assembling volumetric primitives. CVPR 2017
	- Input: voxel; output: mesh parts (triangles);
	- Each part (z, q, t): z, shape; q rotation; t translation;
	- Loss design:
		- Coverage loss: distance of primitives; penalize to confirm O in Pm
		- Consistency loss:
	- Variable number of primitives: (z, q, t, p), p binary for existence
	- REINFORCE; parsimony reward for fewer parts
	- Experiment: ShapeNet, 32x32x32, ADAM;
- GRASS: Generative Recursive Autoencoders for Shape Structures. SIGGRAPH 2017
- Im2Struct: Recovering 3D Shape Structure from a Single RGB Image (2018 CVPR)

## Reconstruction
- Warping, Flow:
	- Tinghui Zhou, Shubham Tulsiani, Weilun Sun, Jitendra Malik, Alexei A. Efros. View Synthesis by Appearance Flow. ECCV 2016
		- https://github.com/tinghuiz/appearance-flow
- Rohit Girdhar, David F. Fouhey, Mikel Rodriguez, Abhinav Gupta. Learning a Predictable and Generative Vector Representation for Objects. ECCV 2016

## GAN
- Jimei:
	- Perspective Transformer Nets: Learning Single-View 3D Object Reconstruction without 3D Supervision. NIPS 2016
		- https://github.com/xcyan/ptnbhwd
- MIT Series:
	- **3D-GAN**: Jiajun Wu, Learning a probabilistic latent space of object shapes via 3d generative-adversarial modeling, NIPS 2016
		- GAN / GAN-VAE;
		- Noisy / Blurry;
- **PrGAN**: Matheus Gadelha, Subhransu Maji and Rui Wang. 3D Shape Induction from 2D Views of Multiple Objects. 3DV 2017
	- https://github.com/matheusgadelha/PrGAN

## Other
- **FAIR-3D, Berkeley**:
	- Shubham Tulsiani, Tinghui Zhou, Alexei A. Efros, Jitendra Malik. Multi-view Supervision for Single-view Reconstruction via Differentiable Ray Consistency. CVPR 2017
		- https://github.com/shubhtuls/drc
- **DeepMind**:
	- Unsupervised Learning of 3D Structure from Images
	- Andrew Brock, Theodore Lim, J.M. Ritchie, Nick Weston. Generative and Discriminative Voxel Modeling with Convolutional Neural Networks
		- https://github.com/ajbrock/Generative-and-Discriminative-Voxel-Modeling
		- VAE, GAN

## Generation
- **3D-INN**:
	- Jiajun Wu, Tianfan Xue, Joseph J. Lim, Yuandong Tian, Joshua B. Tenenbaum, Antonio Torralba, and William T. Freeman. Single Image 3D Interpreter Network, ECCV 2016
		- Detect 2d keypoints as well as 3d structure;
		- Keypoint detection (CNN) -> keypoint refinement (mini-network like auto-encoder) -> 3D interpreter -> Projection Layer;
	- Jiajun Wu, Chengkai Zhang, Xiuming Zhang, Zhoutong Zhang, William T. Freeman, and Joshua B. Tenenbaum: Learning 3D Shape Priors for Shape Completion and Reconstruction, ECCV 2018
		- Extension of **3D-INN**
		- An "adversarial" Naturalness Network to determine quality, with Wasserstein-GAN loss;
- **Marr-Net**: 3d shape reconstruction via 2.5 d sketches, NIPS 2017
	- First predict a 2.5-D (normal, depth, silhouette)
	- Reprojection consistency;
- Haibin Huang, Evangelos Kalogerakis, and Benjamin Marlin. Analysis and synthesis of 3d shape families via
deep-learned generative models of surfaces. CGF, 34(5):25–38, 2015.
- Interactive 3D modeling with a generative adversarial network, 3D Vision 2017
- Amir Arsalan Soltani, Haibin Huang, Jiajun Wu, Tejas D. Kulkarni, Joshua B. Tenenbaum. Synthesizing 3D Shapes via Modeling Multi-View Depth Maps and Silhouettes with Deep Generative Networks. CVPR 2017
	- https://github.com/Amir-Arsalan/Synthesize3DviaDepthOrSil

## 2.5-D, Intrinsic Images
- H. G. Barrow and J. M. Tenenbaum, “Recovering intrinsic scene characteristics from images,” Computer Vision Systems, 1978

## 3D-Reconstruction, Render
- W. Jakob, “Mitsuba renderer,” 2010, http://www.mitsuba-renderer.org.
- Hao Su, Charles R Qi, Yangyan Li, and Leonidas Guibas. Render for cnn: Viewpoint estimation in images using cnns trained with rendered 3d model views. In ICCV, 2015b.
- Xinchen Yan, Jimei Yang, Ersin Yumer, Yijie Guo, and Honglak Lee. Perspective transformer nets: Learning single-view 3d object reconstruction without 3d supervision. In NIPS, 2016.
- Hao Su, Haoqiang Fan, Leonidas Guibas. A Point Set Generation Network for 3D Object Reconstruction from a Single Image, CVPR 2017
- **PointNet**: Hao Su, Charles Qi, Kaichun Mo, Leonidas Guibas. PointNet: Deep Learning on Point Sets for 3D Classification and Segmentation, CVPR 2017
	- Define Conv on point cloud 
- A. Dai, C. R. Qi, and M. Nießner,  **Shape completion using 3d-encoder-predictor cnns and shape synthesis, CVPR 2017**
	- https://github.com/angeladai/cnncomplete
- SurfNet: Generating 3D shape surfaces using deep residual networks, CVPR 2017
- **DRC**: Shubham Tulsiani, Tinghui Zhou, Alexei A Efros, and Jitendra Malik. Multi-view supervision for single-view reconstruction via differentiable ray consistency. CVPR 2017
- Maxim Tatarchenko, Alexey Dosovitskiy, Thomas Brox. Octree Generating Networks:
Efficient Convolutional Architectures for High-resolution 3D Outputs.
