# AutoML, Architecture Search

## A Summary
- https://github.com/markdtw/awesome-architecture-search

## Optimize Tensor Program
- Auto-TVM:
	- Tianqi Chen and Thierry Moreau and Ziheng Jiang and Lianmin Zheng and Eddie Yan. TVM: An Automated End-to-End Optimizing Compiler for Deep Learning. OSDI 2018
	- Tianqi Chen and Lianmin Zheng and Eddie Yan and Ziheng Jiang and Thierry Moreau and Luis Ceze and Carlos Guestrin and Arvind Krishnamurthy. Learning to Optimize Tensor Programs. NIPS 2018
		- Input: a program, output: an efficient execution;
		- Model 1: GBT (XGBoost);
		- Model 2: TreeGRU; (Kai Sheng Tai, Richard Socher, and Christopher D Manning. Improved semantic representations from tree-structured long short-term memory networks.)
		- Loss: ranking loss;
		- Optimization process (Sub-Modular): simulated annealing to collect candidates; diversity-aware optimization;
		- Transfer Learning;
- **Polyhedral**:
	- Uday Bondhugula, Albert Hartono, J. Ramanujam, and P. Sadayappan. A practical automatic polyhedral parallelizer and locality optimizer. SIGPLAN, PLDI 2008
	- **Tensor comprehension**: Nicolas Vasilache, Oleksandr Zinenko, Theodoros Theodoridis, Priya Goyal, Zachary DeVito, William S. Moses, Sven Verdoolaege, Andrew Adams, and Albert Cohen. Tensor comprehensions: Frameworkagnostic high-performance machine learning abstractions. CoRR 2018
	- Sven Verdoolaege, Juan Carlos Juega, Albert Cohen, José Ignacio Gómez, Christian Tenllado, and Francky Catthoor. Polyhedral parallel code generation for cuda. ACM 2013
- **Halide**: Jonathan Ragan-Kelley, Connelly Barnes, Andrew Adams, Sylvain Paris, Frédo Durand, and Saman Amarasinghe. Halide: A language and compiler for optimizing parallelism, locality, and recomputation in image processing pipelines. PLDI 2013
- Black box:
	- **FFTW**: M. Frigo and S. G. Johnson. Fftw: an adaptive software architecture for the fft. ICASSP 1998
	-  Daniel Golovin, Benjamin Solnik, Subhodeep Moitra, Greg Kochanski, John Karro, and D. Sculley. Google vizier: A service for black-box optimization. KDD 2017
	- **Atlas**: R. Clint Whaley and Jack J. Dongarra. Automatically tuned linear algebra software. 1998
- DSL:
	- Fredrik Kjolstad, Shoaib Kamil, Stephen Chou, David Lugato, and Saman Amarasinghe. The tensor algebra compiler. OOPSLA 2017
	- **Weld**: Shoumik Palkar, James J. Thomas, Deepak Narayanan, Anil Shanbhag, Rahul Palamuttam, Holger Pirk, Malte Schwarzkopf, Saman P. Amarasinghe, Samuel Madden, and Matei Zaharia. Weld: Rethinking the interface between data-intensive applications. PLDI CoRR 2017
	- Michel Steuwer, Toomas Remmelg, and Christophe Dubach. Lift: A functional data-parallel ir for high-performance gpu code generation. CGO 2017
	- Arvind K. Sujeeth, HyoukJoong Lee, Kevin J. Brown, Hassan Chafi, Michael Wu, Anand R. Atreya, Kunle Olukotun, Tiark Rompf, and Martin Odersky. Optiml: An implicitly parallel domain-specific language for machine learning. ICML 2011

## RL
- **NasNet**:
	- Zoph, Le: Neural architecture search with reinforcement learning, ICLR 2017
	- Zoph, Le (NASNET): 2017 Learning transferable architectures for scalable image recognition.
	- https://github.com/tensorflow/models/tree/master/research/slim/nets/nasnet
- Baker, B.; Gupta, O.; Naik, N.; and Raskar, R (MetaQNN). Designing neural network architectures using reinforcement learning. ICLR 2017
	- https://github.com/bowenbaker/metaqnn
- H Pham, M. Guan, B. Zoph, Q. Le (ENAS): 2018 Efficient neural architecture search via parameter sharing
	- Key contribution: Parameter sharing
	- Penn TreeBank: 55.8 Perplexity, CIFAR-10: 2.89%
	- https://github.com/melodyguan/enas/tree/2734eb2657847f090e1bc5c51c2b9cbf0be51887
	- https://github.com/carpedm20/ENAS-pytorch
- H Cai, T Chen, (EAS): Efficient architecture search by network transformation, AAAI 2018
	- Initialize with DenseNet, evolve by widen and deepen
	- CIFAR-10: 4.23%, SVHN 1.73%
	- https://github.com/han-cai/eas
- H Cai, S Han (PathLevel-EAS): Path-Level Network Transformation for Efficient Architecture Search, ICML 2018
	- https://github.com/han-cai/PathLevel-EAS
- Zhong, Zhao, Yan, Junjie, and Liu, Cheng-Lin. Practical network blocks design with q-learning. AAAI, 2018.

## Evolution:
- H Liu, K simonyan, et.al. Hierarchical representations for efficient architecture search, ICLR 2018
- Baker, Bowen, Otkrist, Gupta, Raskar, Ramesh, and Naik, Nikhil. Accelerating neural architecture search using performance prediction. Arxiv, 1705.10823, 2017b.
- Real, E.; Moore, S.; Selle, A.; Saxena, S.; Suematsu, Y. L.; Le, Q.; and Kurakin, A. 2017. Large-scale evolution of image classifiers. ICML 2017
- E. Real, Q. Le, (AmoebaNet): 2018 Regularized evolution for image classifier architecture search.
- Lingxi Xie and Alan Yuille. Genetic CNN. ICCV'17
	- https://github.com/aqibsaeed/Genetic-CNN
- AutoKeras 2018: Efficient Neural Architecture Search with Network Morphism

## Performance Prediction
- Eric Xing: Neural architecture search with bayesian optimisation and optimal transport. NIPS 2018
	- Gaussian Process to predict performance from history
	- Measure Network distance from graph theory
	- https://github.com/kirthevasank/nasbot
- Bowen Baker, Otkrist Gupta, Ramesh Raskar, Nikhil Naik. Accelerating Neural Architecture Search using Performance Prediction. ICLR 2018 Workshop

## SMBO
- C. Liu, B. Zoph, J Shlens, W. Hua, A Yuille, K. Murphy (PNAS): 2017 Progressive neural architecture search
- Negrinho, Renato and Gordon, Geoff: Deeparchitect: Automatically designing and training deep architectures, CVPR 2017
	- MCTS
	- https://github.com/negrinho/deep_architect

## Differential
- DARTS: Differentiable Architecture Search
	- 2.83% error CIFAR, 73.1% ImageNet top-1
	- 56.1 Perplexity PTB
	- https://github.com/quark0/darts

## Legacy
- D. Floreano, P. Durr, and C. Mattiussi. Neuroevolution: from architectures to learning. Evolutionary Intelligence, 1(1):47–62, 2008
- K. Stanley and R. Miikkulainen. Evolving neural networks through augmenting topologies. Evolutionary Computation, 10(2):99–127, 2002. 2

## misc
- Brock, Andrew, Lim, Theodore, Ritchie, James M., and Weston, Nick. SMASH: one-shot model architecture search through hypernetworks. ICLR, 2018.
- Thomas Elsken, Jan-Hendrik Metzen, Frank Hutter. Simple and efficient architecture search for Convolutional Neural Networks. Invited to ICLR'18 Workshop
- Jin-Dong Dong, An-Chieh Cheng, Da-Cheng Juan, Wei Wei, Min Sun. DPP-Net: Device-aware Progressive Search for Pareto-optimal Neural Architectures. ECCV'18