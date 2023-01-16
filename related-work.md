# Related Work.  

## Surveys.  

## RL based pruning.  

## GAN based pruning.   

**Towards Optimal Structured CNN Pruning via Generative Adversarial Learning (CVPR 2020)**.  
[Paper](https://openaccess.thecvf.com/content_CVPR_2019/papers/Lin_Towards_Optimal_Structured_CNN_Pruning_via_Generative_Adversarial_Learning_CVPR_2019_paper.pdf).  
*Abstract*
> "Structured pruning of filters or neurons has received in- creased focus for compressing convolutional neural net- works. Most existing methods rely on multi-stage optimiza- tions in a layer-wise manner for iteratively pruning and re- training which may not be optimal and may be computation intensive. Besides, these methods are designed for pruning a specific structure, such as filter or block structures with- out jointly pruning heterogeneous structures. In this paper, we propose an effective structured pruning approach that jointly prunes filters as well as other structures in an end- to-end manner. To accomplish this, we first introduce a soft mask to scale the output of these structures by defining a new objective function with sparsity regularization to align the output of baseline and network with this mask. We then effectively solve the optimization problem by generative ad- versarial learning (GAL), which learns a sparse soft mask in a label-free and an end-to-end manner. By forcing more scaling factors in the soft mask to zero, the fast iterative shrinkage-thresholding algorithm (FISTA) can be leveraged to fast and reliably remove the corresponding structures. Extensive experiments demonstrate the effectiveness of GAL on different datasets, including MNIST, CIFAR-10 and Im- ageNet ILSVRC 2012. For example, on ImageNet ILSVRC 2012, the pruned ResNet-50 achieves 10.88% Top-5 error and results in a factor of 3.7× speedup. This significantly outperforms state-of-the-art methods."   

<img width="989" alt="image" src="https://user-images.githubusercontent.com/94199007/212780935-32d60598-1233-4dee-91d8-acbd6afafc8c.png">

