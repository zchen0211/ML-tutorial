# 3D Understanding and Synthesis

## Tutorials
- https://github.com/timzhang642/3D-Machine-Learning

## SOA
- **Chamfer distance** (a strong baseline)
	- Sum of closest point distances
	- Asymmetric
	- For Hausdorff distance, simply a distance transform?
- B. Graham, M. Engelcke, and L. van der Maaten. 3D semantic segmentation with submanifold sparse convolutional networks. CVPR 2018
	- SSCN (submanifold sparse Conv Net)
	- https://github.com/facebookresearch/SparseConvNet
	- SSCN(m, n, f, s): m input, n output, f filter-size, s stride;
	- Implementation: a hash table (https://github.com/sparsehash/sparsehash) and a matrix;
	- **Sparse Voxelized**: applied on Submanifold FCN and U-Nets;
	- CPU-only;
	- Experiments: ShapeNet; NYU depth;
- P. Hermosilla, T. Ritschel, P.-P. Vazquez, A. Vinacua,  and T. Ropinski. Monte carlo convolution for learning on non-uniformly sampled point clouds. 2018
	- Point Clouds (generally non-uniform);
	- Estimate sample density distribution;
	- https://github.com/viscom-ulm/MCCNN
- R. Klokov and V. Lempitsky. Escape from cells: Deep Kd-networks for the recognition of 3D point cloud models. ICCV 2017
	- Point clouds
	- http://sites.skoltech.ru/compvision/kdnets/
	- Work with Kd-tree; (top-down, every node split the axis with largest span);
	- Recursive bottom-up;
	- Properties:
		- Layerwise parameter sharing;
		- Hierarchical representation;
		- Partial invariance to jitter;
		- Non-invariance to rotations;
		- Role of kd-tree structure;
	- Experiments: MNIST 2D points; ModelNet;
- T. Le and Y. Duan. PointGrid: A deep network for 3D shape understanding. CVPR 2018
- J. Li, B. M. Chen, and G. H. Lee. SO-Net: Self-organizing network for point cloud analysis. CVPR 2018
- Y. Li, R. Bu, M. Sun, and B. Chen. PointCNN: Convolution on X -transformed points. NIPS 2018
- Detection:
	- **PointNet++**: Deep Hierarchical Feature Learning on Point Sets in a Metric Space, Charles R. Qi, Li Yi, Hao Su, Leonidas J. Guibas, NIPS 2017
		- **Classification mode**: [SA module x 3] + FC_layers;
		- SA module #1, #2: xyz, features = model(xyz, features=None), xyz: (B, 2048, 3)
			- Gather operation (furtherest point sampling): from 2048 points, select 512 centers as new_xyz (B, 512, 3)
			- Group-Query-MLP x 3 (with different radius)
				- Group and Query: to (B, d, 512, nS), dim: feature dim; each 512 centers will be assigned nS=16 members
				- Shared MLPs: with dim like [d, 32, 32, 64], output (B, 64, 512, nS), implement FC with 2D-Conv with kernel-size (1, 64)
				- Max-pooling along last dimension (B, 64, 512)
			- After SA-1: xyz=(B, 512, 3), feat=(B, 320, 512)
			- After SA-2: xyz=(B, 128, 3), feat=(B, 640, 128)
		- SA module #3:
			- No gather operation: new_xyz=None
			- GroupAll: (B, 643, 1, nS), 643=640+3, nS=128
			- Shared MLPs: (B, 1024, 1)
		- FC_layers: [1024, 512, 256, nClass]
		- Finally a 256-dim feature
		- **Semantic Segmentation mode**: [SA-module x3] + [FP-modules x4] + [Conv1d x2]
		- FP-modules are used to interpolate features back;
```python
feat[i-1] = self.FP_modules[i](xyz[i-1], xyz[i], feat[i-1], feat[i])
```
		- With shape: (B, n, 3), (B, m, 3), (B, C1, n), (B, C2, m), returns (B, mlp[-1], n)
	- **PointNet**: Charles R. Qi, Wei Liu, Chenxia Wu, Hao Su, Leonidas Guibas. Frustum PointNets for 3D Object Detection from RGB-D Data, CVPR 2018
- **SplatNet**: H. Su, V. Jampani, D. Sun, S. Maji, E. Kalogerakis, M.-H. Yang, and J. Kautz. SplatNet: Sparse lattice networks for point cloud processing. CVPR 2018
	- Input: point clouds and images; output semantic for each point;
	- BCL (Bilateral Convolution Layer)
		- Splat: project onto lattice
		- Convolve
		- Slice
- M. Sung, H. Su, R. Yu, and L. Guibas. Deep functional dictionaries: Learning consistent semantic structures on 3D models from functions. NIPS 2018
	- Input n points; output:  n x k dictionary;
	- Structured sparsity;
	- https://github.com/mhsung/deep-functional-dictionaries
	- Different deep dictionaries;
	- Applications with adaptation in co-segmentation, keypoint correspondence, smooth functional approximation (modeled as constraint);
	- Given an input X, At = A(X; theta) to get basis
	- Solve x = argmin||At x - f||^2 s.t. C(x)
	- Update theta = theta - eta * d L(A(X, theta); f, x) / dx
- P.-S. Wang, Y. Liu, Y.-X. Guo, C.-Y. Sun, and X. Tong. OCNN: Octree-based convolutional neural networks for 3D shape analysis. TOG 2017
- Y. Wang, Y. Sun, Z. Liu, S. E. Sarma, M. M. Bronstein, and J. M. Solomon. Dynamic graph cnn for learning on point clouds. 2018
- X. Wang, B. Zhou, H. Fang, X. Chen, Q. Zhao, and K. Xu. Learning to group and label fine-grained shape components. SIGGRAPH Asia 2018
- Z. Wang and F. Lu. VoxSegNet: Volumetric CNNs for semantic part segmentation of 3D shapes. 2018
- Z. Wu, X. Wang, D. Lin, D. Lischinski, D. Cohen-Or, and H. Huang. Structure-aware generative network for 3d-shape modeling. 2018
- Y. Xu, T. Fan, M. Xu, L. Zeng, and Y. Qiao. SpiderCNN: Deep learning on point sets with parameterized convolutional filters. ECCV 2018
- L. Yi, H. Su, X. Guo, and L. J. Guibas. SyncSpecCNN: Synchronized spectral CNN for 3D shape segmentation. CVPR 2017

## Co-Segmentation
- R. Hu, L. Fan, and L. Liu. Co-segmentation of 3D shapes via subspace clustering. CGF 2012
- Y. Wang, S. Asafi, O. Van Kaick, H. Zhang, D. Cohen-Or, and B. Chen. Active co-analysis of a set of shapes. TOG 2012

## Part
- R. Hu, W. Li, O. Van Kaick, A. Shamir, H. Zhang, and H. Huang. Learning to predict part mobility from a single static snapshot. TOG 2017
- R. Hu, O. van Kaick, B. Wu, H. Huang, A. Shamir, and H. Zhang. Learning how objects function via co-analysis
of interactions. TOG 2016
- R. Hu, Z. Yan, J. Zhang, O. van Kaick, A. Shamir, H. Zhang, and H. Huang. Predictive and generative neural networks for object functionality. CGF 2018
- **Hao Su Summary**: http://cseweb.ucsd.edu/~haosu/slides/PartInduction.pdf
- **ISIN**: Cewu Lu, Hao Su, Yongyi Lu, Li Yi, Chi-Keung Tang, Leonidas Guibas. Beyond Holistic Object Recognition: Enriching Image Understanding with Part States. CVPR 2018
	- Objerect Part-State Dataset
	- Iterative Part-state Inference Network (ISIN)

## Classification
- Voxel:
	- **ModelNet**: Z. Wu, S. Song, A. Khosla, F. Yu, L. Zhang, X. Tang and J. Xiao. 3D ShapeNets: A Deep Representation for Volumetric Shapes
		- Predict next best angle (most uncertain by max entropy diff)
	- Daniel Maturana and Sebastian Scherer. VoxNet: A 3D Convolutional Neural Network for Real-Time Object Recognition. IROS 2015
		- https://github.com/dimatura/voxnet
- 2D images:
	- Hang Su, Subhransu Maji, Evangelos Kalogerakis, Erik Learned-Miller. Multi-view Convolutional Neural Networks for 3D Shape Recognition. ICCV 2015
		- https://github.com/jongchyisu/mvcnn_pytorch
		- Multi-view pooling
	- DeepPano: Deep Panoramic Representation for 3-D Shape Recognition.
- Multi-mode:
	- Vishakh Hegde, Reza Zadeh. FusionNet: 3D Object Classification Using Multiple Data Representations. NIPS 2016
	- Charles R. Qi, Hao Su, Matthias Nießner Angela Dai Mengyuan Yan Leonidas J. Guibas. Volumetric and Multi-View CNNs for Object Classification on 3D Data. CVPR 2016
		- https://github.com/charlesq34/<3dcnn class="torch"></3dcnn>

## Understanding, Classification
- Robotics (grasping, with touch):
	- M. Bjorkman, Y. Bekiroglu, V. Hogman, and D. Kragic, “Enhancing visual perception of shape through tactile glances,” IROS 2013.
	- 3D Shape Perception from Monocular Vision, Touch, and Shape Priors, Shaoxiong Wang, Jiajun Wu, Xingyuan Sun, Wenzhen Yuan, William T. Freeman, Joshua B. Tenenbaum, and Edward H. Adelson
	- W. Yuan, S. Dong, and E. H. Adelson, Gelsight: High-resolution robot tactile sensors for estimating geometry and force, Sensors 2017.
- Representation for Voxel data:
	- Rohit Girdhar, David F Fouhey, Mikel Rodriguez, and Abhinav Gupta. Learning a predictable and generative vector representation for objects. In ECCV, 2016.
	- Hang Su, Subhransu Maji, Evangelos Kalogerakis, and Erik Learned-Miller. Multi-view convolutional neural networks for 3d shape recognition. In ICCV, 2015a.
	- Charles R Qi, Hao Su, Matthias Niessner, Angela Dai, Mengyuan Yan, and Leonidas J Guibas. Volumetric and multi-view cnns for object classification on 3d data. In CVPR, 2016.
- 3D-Conv:
	- Daniel Maturana and Sebastian Scherer. Voxnet: A 3d convolutional neural network for real-time object
recognition. In IROS, 2015.
	- Nima Sedaghat, Mohammadreza Zolfaghari, and Thomas Brox. Orientation-boosted voxel nets for 3d object
recognition. arXiv preprint arXiv:1604.03351, 2016.
	- Jiajun Wu, Tianfan Xue, Joseph J Lim, Yuandong Tian, Joshua B Tenenbaum, Antonio Torralba, and William T
Freeman. Single image 3d interpreter network. In ECCV, 2016.
	- Uber-AI-Lab: An intriguing failing of convolutional neural networks and the CoordConv solution
- Unsupervised:
	- Danilo Jimenez Rezende, SM Eslami, Shakir Mohamed, Peter Battaglia, Max Jaderberg, and Nicolas Heess. Unsupervised learning of 3d structure from images. In NIPS, 2016.
- Orientation-boosted voxel nets for 3D object recognition, T. Brox, 2016
- **3d-r2n2**: A unified approach for single and multi-view 3d object reconstruction
- T. Groueix, M. Fisher, V. G. Kim, B. Russell, and M. Aubry. AtlasNet: A Papier-Mach ˆ e Approach to Learning 3D Surface Generation. CVPR 2018
- J. Gwak, C. B. Choy, M. Chandraker, A. Garg, and S. Savarese. Weakly supervised 3d reconstruction with adversarial constraint. 3DV 2017
- S. Savarese and L. Fei-Fei. 3d generic object categorization, localization and pose estimation, ICCV 2017
- X. Yan, J. Yang, E. Yumer, Y. Guo, and H. Lee. Perspective transformer nets: Learning single-view 3d object reconstruction without 3d supervision. In NIPS, 2016.
