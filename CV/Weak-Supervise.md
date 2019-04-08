# Weakly-Supervsied Learning

## FAIR
- **Tutorial**: M. A. Ranzato and A. Graves. Deep unsupervised learning. NIPS Tutorial, 2018
- **URU**: Exploring the Limits of Weakly Supervised Pretraining. ECCV 2018
	- Pretrain on a larger dataset (1.5 billion Instagram) + (1.5k, 8.5k, 17k hashtag classes);
	- Preprocessing: image-deduplication, hash-tags clean up (SynNet);
	- Model: ResNext;
	- Infra: Caffe2-1hr, synchronous-SGD; 42 Machine x 8 GPU/m = 336 GPU; 22 days;
	- Conclusion 1: hash-tags v.s. accuracy; (always a gain, fine-grained target needs a fine-grained source);
	- Conclusion 2: larger amount of pretrain -> better target domain accuracy;
	- Conclusion 3: the smaller the label noise (hashtags are noisy) -> better target accuracy;
- Armand Joulin, Laurens van der Maaten, Allan Jabri, Nicolas Vasilache. Learning Visual Features from Large Weakly Supervised Data. ECCV 2016
- Weak detetection (Zhenheng):
	- Image has only image level labeling (no bbox or segments);
	- Hundreds of candidate proposals (can't penalize bbox reg-loss or classification loss);
	- Max-pooling/top-k then direct classification;
	- Half mAP 
- Lessons from Scaling Self-Supervised Learning of Visual Representations. ICCV 2019 submission.
	- Task 1: **Jigsaw** (permutation)
	- Task 2: **Colorization**
	- Pretrain, then only train top linear layer;
- Deep Clustering for Unsupervised Learning of Visual Features. ECCV 2018

## Tasks
- Context prediction:
	- Unsupervised Visual Representation Learning by Context Prediction. ICCV 2015
- Jigsaw:
	- Unsupervised Learning of Visual Representations by Solving Jigsaw Puzzles. ECCV 2016

## Videos
- Self-Supervised Video Representation Learning With Odd-One-Out Networks
- Shuffle and Learn: Unsupervised Learning using Temporal Order Verification
