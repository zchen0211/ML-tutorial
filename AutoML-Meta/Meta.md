# Meta-Learning

## Summary
- https://github.com/floodsung/Meta-Learning-Papers
- LSTM Learner:
	- S. Ravi and H. Larochelle. Optimization as a model for fewshot learning. ICLR 2017
- Parameter Prediction
	- L. Bertinetto, J. F. Henriques, J. Valmadre, P. Torr, and A. Vedaldi. Learning feed-forward one-shot learners. NIPS 2016
	- H. Qi, M. Brown, and D. G. Lowe. Low-shot learning with imprinted weights. 2017
- Metric:
	-  O. Vinyals, C. Blundell, T. Lillicrap, D. Wierstra, et al. Matching networks for one shot learning. NIPS 2016
- Conv-learner:
	- **SNAIL**: Pieter Abbeel, et. al. A Simple Neural Attentive Meta-Learner, ICLR 2018
		- Temporal 1D-Conv + Attention;

## MAML (Chelsea Finn)
- MAML: https://github.com/cbfinn/maml
- MAML for RL: https://github.com/cbfinn/maml_rl
- MAML Pytorch: https://github.com/katerakelly/pytorch-maml

## Uncertainty
- **BMAML** Bayesian Model-Agnostic Meta-Learning (Yoshua Bengio, NIPS 2018)
	- BMAML
	- Add uncertainty on both initial model and update
	- Stein Variational Gradient Descent (SVGD)
	- Extend uncertainty-awareness to meta-update
- **Probabilistic Model-Agnostic Meta-Learning** (Chelsea Finn, NIPS 2018)
	- Uncertainty
	- A graphical model view

## SOA
- F. Sung, Y. Yang, L. Zhang, T. Xiang, P. H. Torr, and T. M. Hospedales. Learning to compare: Relation network for fewshot learning. CVPR, 2018.

## Detection
- Bingyi Kang, Zhuang Liu, Xin Wang, Fisher Yu, Jiashi Feng, Trevor Darrell. Few-shot Object Detection via Feature Reweighting. 2018
	- Built on YOLOv2
	- Assumptions: feature can be reused, different features play important roles in specific classes
	- Train a meta-conv module as weight, to reweight features
- Y.-X. Wang and M. Hebert. Model recommendation: Generating object detectors from few samples. CVPR 2015