# Model-based RL

## Learn a Model
-  World Model:
	- DeepMind
		- Neural Predictive Belief Representations, ICLR 2019
			- Contrastive-Predictive Coding (CPC)
		- Representation Learning with Contrastive Predictive Coding (NIPS 2018)
	- Google Brain:
		- **Recurrent World Models Facilitate Policy Evolution**， NIPS 2018
			- VAE for compression and regularization
			- Predict next step
			- https://worldmodels.github.io
		- Łukasz Kaiser, Mohammad Babaeizadeh, Piotr Miłos, Błazej Osinski, Roy H Campbell, Konrad Czechowski, Dumitru Erhan, Chelsea Finn, Piotr Kozakowski, Sergey Levine, Ryan Sepassi, George Tucker, Henryk Michalewski. Model Based Reinforcement Learning for Atari. 2019
			- SimPLe
			- https://ai.googleblog.com/2019/03/simulated-policy-learning-in-video.html
			- Open sourced at https://github.com/tensorflow/tensor2tensor
			- Main loop:
				- The agent starts interacting with the real environment.
				- The collected observations are used to update the current world model.
				- The agent updates the policy by learning inside the world model.
			- World model: feed-forward CNN
				- Input 4 frames
				- Output: predicts next frame (256 softmax)
				- Output: Reward
			- RL:
				- PPO
			- Experiment: 100k interactions;

## Robotics
- Guided policy search (model-based RL) for image-based robotic manipulation https://github.com/cbfinn/gps
- End-to-end training of deep visuomotor policies, L.* , Finn* ’16

## Video Prediction
- J. Oh, X. Guo, H. Lee, R. Lewis, and S.Singh. Action-conditional video prediction using deep networks in atari games. arxiv, 2015.
