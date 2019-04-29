# Benchmarks

## Benchmarks
- ShapeNet-Series:
	- **ShapeNet**: Angel X Chang, Thomas Funkhouser, Leonidas Guibas, et al. Shapenet: An information-rich 3d model repository. 2015
		- https://www.shapenet.org/
		- 55 classes, 51,300 unique 3D models (ShapeNetCore)
		- Part label available
	- **ModelNet**: Zhirong Wu, Shuran Song, Aditya Khosla, Fisher Yu, Linguang Zhang, Xiaoou Tang, and Jianxiong Xiao. 3d shapenets: A deep representation for volumetric shapes. In CVPR, 2015.
		- http://3dshapenets.cs.princeton.edu/
		- 30 x 30 x 30 voxels
		- 662 classes, 151,128 CAD models (3D)
		- ModelNet10: 4899 models from 10 categories 
		- ModelNet40: 12311 models from 40 categories, all are uniformly orientated
	- **PartNet**: Kaichun Mo, Shilin Zhu, Angel X. Chang, Li Yi, Subarna Tripathi, Leonidas J. Guibas, Hao Su. PartNet: A Large-scale Benchmark for Fine-grained and Hierarchical Part-level 3D Object Understanding.
		- https://cs.stanford.edu/~kaichun/partnet/
		- 573,585 parts, 26,671 3D models, 24 categories
		- Based on ShapeNet-Core
		- Hierarchical labeling
		- Compare 4 SOA
- **PASCAL-3D**: Yu Xiang, Roozbeh Mottaghi, and Silvio Savarese. Beyond pascal: A benchmark for 3d object detection in the wild. In WACV, 2014.
	- 12 categories, 3k+ objects
- **IKEA**: Joseph J. Lim, Hamed Pirsiavash, and Antonio Torralba. Parsing ikea objects: Fine pose estimation. ICCV 2013.
	- http://ikea.csail.mit.edu/
	- Goal: evaluate fine pose estimation based on 3D models
	- 759 images, 219 3D-models
- **ObjectNet3D**: Yu Xiang, Wonhui Kim, Wei Chen, Jingwei Ji, Christopher Choy, Hao Su, Roozbeh Mottaghi, Leonidas Guibas, Silvio Savarese. A Large Scale Database for 3D Object Recognition, ECCV 2016
- Other 3D benchmarks:
	- Trimble 3D Warehouse: https://3dwarehouse.sketchup.com/
	- Yobi3D: https://yobi3d.com
	- P. Shilane, P. Min, M. Kazhdan, and T. Funkhouser. The princeton shape benchmark. In Shape Modeling Applications, 2004
		- 6,670 CAD models, 161 categories
	- FAUST: Dataset and evaluation for 3D mesh registration, CVPR 2014
	- **LabelMe 3d**: B. C. Russell and A. Torralba. Building a database of 3d scenes from user annotations. In CVPR, 2009
	- P. Shilane, P. Min, M. Kazhdan, and T. Funkhouser. The princeton shape benchmark. In Shape Modeling Applications 2004. 
	- **NYU-D** N. Silberman, D. Hoiem, P. Kohli, and R. Fergus. Indoor segmentation and support inference from rgbd images. ECCV 2012
- Robotic Grasping 3d:
	- Benchmarking in manipulation research: The YCB object and model set and benchmarking protocols, RAM 2015
- RGB-D:
	- M. Firman. Rgbd datasets: Past, present and future. In CVPR Workshop, 2016
	- S. Choi and Q. Zhou and S. Miller and V. Koltun. A Large Dataset of Object Scans, 2016
		- 10K scans of RGBD, in .PLY format.
	- T. Hodan, P. Haluza, S. Obdrzalek, J. Matas, M. Lourakis, and X. Zabulis. T-less: An rgb-d dataset for 6d pose estimation of texture-less objects. In WACV, 2017
	- K. Lai, L. Bo, X. Ren, and D. Fox. A large-scale hierarchical multi-view rgb-d object dataset. ICRA 2011
- X. Puig, K. Ra, M. Boben, J. Li, T. Wang, S. Fidler, and A. Torralba. Virtualhome: Simulating household activities
via programs. CVPR 2018
- C. Yan, D. Misra, A. Bennnett, A. Walsman, Y. Bisk, and Y. Artzi. Chalet: Cornell house agent learning environment. 2018
- L. Yi, L. Guibas, A. Hertzmann, V. G. Kim, H. Su, and E. Yumer. Learning hierarchical shape segmentation and
labeling from online repositories. TOG 2017
- L. Yi, V. G. Kim, D. Ceylan, I. Shen, M. Yan, H. Su, C. Lu, Q. Huang, A. Sheffer, L. Guibas, et al. A scalable active framework for region annotation in 3D shape collections. TOG 2016

## 3D Scenes
- **NYU Depth Dataset V2**: 2012
	- indoor scene, 1449 densely labeled pairs of RGB-D (Kinect)
- **SUNRGB-D**:
	- 10,355 training, 2,860 testing;
- **SceneNN**: 2016
	- 100+ indoor scene meshes;
- **ScanNet**: 2017
- **Matterport3D**: RGB-D indoor Environment;
- **SUNCG**:
- **MINOS: Multimodal Indoor Simulator**: 2017;
- **Facebook House3D**: A Rich and Realistic 3D Environment 2017;
- **HoME**;
- **AI2-THOR**;
- **UnrealCV**;
- **Gibson Environment**: Real-World Perception for Embodied Agents;