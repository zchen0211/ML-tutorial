# Generative Models

## Recurrent, Progressive
- 3D:
	- **3D-PRNN**:
		- https://github.com/zouchuhang/3D-PRNN
- Greg Mori. Probabilistic Neural Programmed Networks for Scene Generation, NIPS 2018
	- Input: text-based programs
    - Output: rendered images
    - PNP-Net

## Recurrent, Sequential, Order-Aware
- **sketch-RNN**: Ha, D. and Eck, D. A neural representation of sketch drawings.
arXiv preprint arXiv:1704.03477, 2017.
	- https://magenta.tensorflow.org/sketch_rnn
- Xie, N., Hachiya, H., and Sugiyama, M. Artist agent: A reinforcement learning approach to automatic stroke generation in oriental ink painting. ICML 2012
	- Ink Painting.
	- Brush as an agent. Train with REINFORCE.
	- Search space: 6-dim.
	- Immediate reward: smoothness

## DeepMind
- **DRAW**: A Recurrent Neural Network For Image Generation. ICML 2015
	- https://github.com/ericjang/draw
	- https://github.com/chenzhaomin123/draw_pytorch
-  Karol Gregor, Frederic Besse, Danilo Jimenez Rezende, Ivo Danihelka, and Daan Wierstra. Towards conceptual compression. NIPS 2016.
	- Convolutional DRAW.
	- Two RNN: one encoder, one decoder;
	- Compression: best reconstruction given budget
	- VAE loss for regularization
	- Step-by-step refine
- **SPRIAL**: Synthesizing Programs for Images using Reinforced Adversarial Learning
- **NPI**:  Scott Reed and Nando de Freitas. Neural programmer-interpreters. In ICLR, 2016.
- **AIR**: Attend, Infer, Repeat: Fast Scene Understanding with Generative Models. NIPS 2016
	- An RNN to handle multiple-object (variable length)
	- Latent variable z to describe if there is new object or not
	- Monte Carlo sampling
- **Neural scene representation and rendering**, Science 2018
- Sequential Attend, Infer, Repeat: Generative Modelling of Moving Objects, NIPS 2018

## MIT: Compositional, Inverse Graphics
- **GPGP**:  Mansinghka, V. K., Kulkarni, T. D., Perov, Y. N., and Tenenbaum, J. Approximate bayesian image interpretation using generative probabilistic graphics programs. In NIPS, 2013
- **Picture**: Kulkarni, T. D., Kohli, P., Tenenbaum, J. B., and Mansinghka, V. Picture: A probabilistic programming language for scene perception. In CVPR, 2015a.
- **DC-IGN**: Kulkarni, T. D., Whitney, W. F., Kohli, P., and Tenenbaum, J. Deep convolutional inverse graphics network. In NIPS, 2015b.
- **Learning to Infer Graphics Programs from Hand-Drawn Images**, NIPS 2018
	- Noisy input (data augmentation)
	- Combining NGPM [4] and Attend-Infer-Repeat [5]
	- Learn a loss function?
	- DSL [11]
	- Prefer shorter program (with explicit reward)
	- Sketch-tool [1] to refine program
- Emilio Parisotto, Abdel rahman Mohamed, Rishabh Singh, Lihong Li, Dengyong Zhou, and Pushmeet Kohli. Neuro-symbolic program synthesis. In arXiv, 2016.
- Wu, J., Tenenbaum, J. B., and Kohli, P. Neural scene derendering. In CVPR, 2017b.
- Wu, J., Lu, E., Kohli, P., Freeman, B., and Tenenbaum, J. Learning to see physics via visual de-animation. In NIPS, 2017a.
-  3D-Aware Scene Manipulation via Inverse Graphics, NIPS 2018

## Inverse Graphics
- Jampani, V., Nowozin, S., Loper, M., and Gehler, P. V. The informed sampler: A discriminative approach to bayesian inference in generative computer vision models. CVIU, 2015.
- **NMN**: Jacob Andreas, Marcus Rohrbach, Trevor Darrell, and Dan Klein. Deep compositional question answering
with neural module networks. In CVPR, 2016.
- Tuan Anh Le, Atilim Gunes Baydin, and Frank D. Wood. Inference compilation and universal probabilistic
programming. CoRR, abs/1610.09900, 2016.
- Stanford:
	- **NGPM**: Neurally-Guided Procedural Models: Amortized Inference for Procedural Graphics Programs using Neural Networks. NIPS 2016
- **Omniglot**
	- Lake, B. M., Salakhutdinov, R., and Tenenbaum, J. B. Human-level concept learning through probabilistic program induction. Science, 2015.
	- Lake, B. M., Ullman, T. D., Tenenbaum, J. B., and Gershman, S. J. Building machines that learn and think like people. Behavioral and Brain Sciences, 40, 2017.
- Justin Johnson, Agrim Gupta, and Li Fei-Fei. **Image generation from scene graphs.** CVPR 2018
- Nair, V., Susskind, J., and Hinton, G. E. Analysis-by synthesis by learning to invert generative black boxes. In ICANN, 2008.
- **Sketch**:
	- Image-to-Markup Generation with Coarse-to-Fine Attention. ICML 2017
- Tung, H.-Y. F., Harley, A. W., Seto, W., and Fragkiadaki, K. Adversarial inverse graphics networks: Learning 2d-to3d lifting and image-to-image translation from unpaired supervision. In ICCV, 2017.
