# Weakly-Supervsied Learning

## FAIR
- **URU**: Exploring the Limits of Weakly Supervised Pretraining. ECCV 2018
	- Pretrain on a larger dataset (1.5 billion Instagram) + (1.5k, 8.5k, 17k hashtag classes);
	- Preprocessing: image-deduplication, hash-tags clean up (SynNet);
	- Model: ResNext;
	- Infra: Caffe2-1hr, synchronous-SGD; 42 Machine x 8 GPU/m = 336 GPU; 22 days;
	- Conclusion 1: hash-tags v.s. accuracy; (always a gain, fine-grained target needs a fine-grained source);
	- Conclusion 2: larger amount of pretrain -> better target domain accuracy;
	- Conclusion 3: the smaller the label noise (hashtags are noisy) -> better target accuracy;
