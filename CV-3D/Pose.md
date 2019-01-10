# 3D Pose Estimation

## Tutorials
- S. Savarese and L. Fei-Fei. 3d generic object categorization, localization and pose estimation, ICCV 2017

## Berkeley
- Shubham Tulsiani, Joao Carreira and Jitendra Malik. Pose Induction for Novel Object Categories. ICCV 2015
	- Input: images, output three Euler Angles
	- SCT (Similar Class Transfer): 
		- Train a CNN for each class (shared base layers, output heads)
		- |C| x Na x Nθ, class, euler angle, angle bin
		- For an unknown class c', find most similar class known
	- GC (Generalized Classifier):
		- VGG, Na x Nθ