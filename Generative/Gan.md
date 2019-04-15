# General Adversarial Net

## GAN
- Google Brain, Magenta:
	- **GAN**: Ian Goodfellow, Jean Pouget-Abadie, Mehdi Mirza, Bing Xu, David Warde-Farley, Sherjil Ozair, Aaron Courville, and Yoshua Bengio. Generative adversarial nets. In NIPS, 2014.
	- William Fedus, Mihaela Rosca, Balaji Lakshminarayanan, Andrew M. Dai, Shakir Mohamed, and Ian Goodfellow. Many paths to equilibrium: GANs do not need to decrease a divergence at every step. In ICLR, 2018.
	- Augustus Odena, Christopher Olah, and Jonathon Shlens. Conditional image synthesis with auxiliary classifier GANs. In ICML, 2017.
	- Augustus Odena, Jacob Buckman, Catherine Olsson, Tom B. Brown, Christopher Olah, Colin Raffel, and Ian Goodfellow. Is generator conditioning causally related to GAN performance? ICML 2018.
	- **SA-GAN**: Han Zhang, Ian Goodfellow, Dimitris Metaxas, and Augustus Odena. Self-attention generative adversarial networks. In arXiv preprint arXiv:1805.08318, 2018.
		- https://github.com/heykeetae/Self-Attention-GAN
		- Spectral-Norm + BN + ReLU
- FAIR:
	- Emily Denton, Soumith Chintala, Arthur Szlam, and Rob Fergus. Deep generative image models using a laplacian pyramid of adversarial networks. NIPS 2015.
	- **DC-GAN**: Alec Radford, Luke Metz, and Soumith Chintala. Unsupervised representation learning with deep convolutional generative adversarial networks. In ICLR, 2016.
	- **W-GAN**: Gulrajani, I., Ahmed, F., Arjovsky, M., Dumoulin, V., and Courville, A. C. Improved training of Wasserstein gans. NIPS 2017.
		- Very good explanation: https://vincentherrmann.github.io/blog/wasserstein/
		- Alex Irpan's blog: https://www.alexirpan.com/2017/02/22/wasserstein-gan.html
		- W-GAN is Earth-Mover-Distance
		- Kantorovich-Rubinstein duality
		- sup[E_pr(f(x))-E_pg(f(x))]/K, where f() is K-Lipschitz (f's gradient < K)
- OpenAI:
	- Tim Salimans, Ian Goodfellow, Wojciech Zaremba, Vicki Cheung, Alec Radford, and Xi Chen. Improved techniques for training gans. NIPS 2016
		- **Perception Score** as evaluation
	- Xi Chen, Yan Duan, Rein Houthooft, John Schulman, Ilya Sutskever, and Pieter Abbeel. Infogan: Interpretable representation learning by information maximizing generative adversarial nets. NIPS 2016
	- Tim Salimans, Han Zhang, Alec Radford, and Dimitris Metaxas. Improving GANs using optimal transport. In ICLR, 2018.
- DeepMind:
	- **BigGAN**: Andrew Brock, Jeff Donahue, Karen Simonyan. **Large Scale GAN Training for High Fidelity Natural Image Synthesis**, ICLR 2019
		- https://github.com/ajbrock/BigGAN-PyTorch.git
		- SA-GAN network structure (Zhang 2018)
		- G: class-conditional BatchNorm (Dumoulin 2017, de Vries 2017)
		- D: projection (Miyato 2018)
		- 2D + 1G: per iteration
		- Moving average (Karras 2018)
		- Orthogonal Initialization (Saxe 2014)
		- **Truncated Norm** to sample z from: big trick
		- IS: precision; FID: recall
	- Andrew Brock, Theodore Lim, J.M. Ritchie, and Nick Weston. Neural photo editing with introspective adversarial networks. ICLR 2017.
	- Marc G. Bellemare, Ivo Danihelka, Will Dabney, Shakir Mohamed, Balaji Lakshminarayanan, Stephan Hoyer, and Remi Munos. The Cramer distance as a solution to biased Wasserstein gradients. In arXiv preprint arXiv:1705.10743, 2017.
- **Condition-GAN**: Mirza, M. and Osindero, S. Conditional generative adversarial nets. arXiv preprint arXiv:1411.1784, 2014.
- **Progressive**: Tero Karras, Timo Aila, Samuli Laine, and Jaakko Lehtinen. Progressive growing of GANs for improved quality, stability, and variation. ICLR 2018.
- **SeqGAN**: Yu, L., Zhang, W., Wang, J., and Yu, Y. SeqGAN: Sequence generative adversarial nets with policy gradient. In AAAI, 2017.
- Takeru Miyato and Masanori Koyama. cGANs with projection discriminator. In ICLR, 2018.
- **SN-GAN**: Spectral Normalization for Generative Adversarial Networks, ICLR 2018
- **BAIR**:
	- **Cycle-GAN**: Zhu, J.-Y., Park, T., Isola, P., and Efros, A. A. Unpaired image-to-image translation using cycle-consistent adversarial networks. CVPR 2017
		- https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix
		- G: X -> Y; discriminator: D_Y;
		- F: Y -> X; discriminator: D_X;
		- Adversarial loss: E[logD_Y(y)] + E[log(1-D_Y(G(x)))]
		- Similar loss for D_X
		- Consistency loss: ||F(G(x))-x|| + ||G(F(y))-y|| with L1 norm
	- **pix2pix**: Isola, P., Zhu, J.-Y., Zhou, T., and Efros, A. A. Image-to-image translation with conditional adversarial networks. CVPR, 2017.
- Feature Learning:
	- Donahue, J., Krahenbuhl, P., and Darrell, T. Adversarial feature learning.
- Inference:
	- Dumoulin, V., Belghazi, I., Poole, B., Lamb, A., Arjovsky, M., Mastropietro, O., and Courville, A. Adversarially learned inference.
- Domain adaptation:
	- Ganin, Y. and Lempitsky, V. Unsupervised domain adaptation by backpropagation. ICML 2015

## Evaluation
- Lucas Theis, Aaron van den Oord, and Matthias Bethge. A note on the evaluation of generative models. In arXiv preprint arXiv:1511.01844, 2015.
- **Perception Score (IS)**: Tim Salimans, Ian Goodfellow, Wojciech Zaremba, Vicki Cheung, Alec Radford, and Xi Chen. Improved
techniques for training gans. NIPS 2016
-  **Frechet Inception Distance (FID)**: Martin Heusel, Hubert Ramsauer, Thomas Unterthiner, Bernhard Nessler, Gunter Klambauer, and Sepp Hochreiter. GANs trained by a two time-scale update rule converge to a local nash equilibrium. NIPS 2017

## Variational
- Sebastian Nowozin, Botond Cseke, and Ryota Tomioka. **f-GAN**: Training generative neural samplers using variational divergence minimization. NIPS 2016

## Analysis
- Lars Mescheder, Andreas Geiger, and Sebastian Nowozin. Which training methods for GANs do actually converge? In ICML, 2018.

## RL, Imitation Learning
- Merel, J., Tassa, Y., Srinivasan, S., Lemmon, J., Wang, Z., Wayne, G., and Heess, N. Learning human behaviors from motion capture by adversarial imitation. arXiv preprint arXiv:1707.02201, 2017.

## Misc
- Eslami, S. A., Heess, N., Weber, T., Tassa, Y., Szepesvari, D., Kavukcuoglu, K., and Hinton, G. E. Attend, infer, repeat: Fast scene understanding with generative models. In NIPS, 2016.
- Loper, M. M. and Black, M. J. Opendr: An approximate differentiable renderer. In ECCV, 2014.
- Louppe, G. and Cranmer, K. Adversarial variational optimization
of non-differentiable simulators. arXiv preprint arXiv:1707.07113, 2017.

## Codes
- StarGAN: https://github.com/yunjey/StarGAN
- Deepak: Unsupervised Feature Learning by Image Inpainting using GANs, CVPR 2016, https://github.com/pathak22/context-encoder