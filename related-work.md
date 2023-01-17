# Related Work.  

## Surveys.  

## RL based pruning.  

**AMC: AutoML for Model Compression and Acceleration on Mobile Devices (ECCV 2018)**.  
[Paper](https://openaccess.thecvf.com/content_ECCV_2018/papers/Yihui_He_AMC_Automated_Model_ECCV_2018_paper.pdf)
*Abstract*   
>"Model compression is an effective technique to efficiently deploy neural network models on mobile devices which have limited computation resources and tight power budgets. Conventional model compression techniques rely on hand-crafted features and require domain experts to explore the large design space trading off among model size, speed, and accuracy, which is usually sub-optimal and time-consuming. In this paper, we propose AutoML for Model Compression (AMC) which leverages reinforcement learning to efficiently sample the design space and can improve the model compression quality. We achieved state-of- the-art model compression results in a fully automated way without any human efforts. Under 4× FLOPs reduction, we achieved 2.7% better accuracy than the hand-crafted model compression method for VGG-16 on ImageNet. We applied this automated, push-the-button compression pipeline to MobileNet-V1 and achieved a speedup of 1.53× on the GPU (Titan Xp) and 1.95× on an Android phone (Google Pixel 1), with negligible loss of accuracy."   

<img width="754" alt="image" src="https://user-images.githubusercontent.com/94199007/212791413-46ec99af-37a8-43e0-b057-ee86271d3bdb.png">  

**Channel Pruning via Lookahead Search Guided Reinforcement Learning (WACV 2022)**.  
[Paper](https://openaccess.thecvf.com/content/WACV2022/papers/Wang_Channel_Pruning_via_Lookahead_Search_Guided_Reinforcement_Learning_WACV_2022_paper.pdf).  
*Abstract*
>"Channel pruning has become an effective yet still chal- lenging approach to achieve compact neural networks. It aims to prune the optimal set of filters whose removal re- sults in minimal performance degradation of the slimmed network. Due to the prohibitively vast search space of fil- ter combinations, existing approaches usually use various criteria to estimate the filter importance while sacrificing some precision. Here we present a new approach to opti- mizing the filter selection in channel pruning with looka- head search guided reinforcement learning (RL). A neural network that takes as input filter-related features is trained with RL to prune the optimal sequence of filters and max- imize the performance of the remaining network. In addi- tion, we employ Monte Carlo tree search (MCTS) to pro- vide a lookahead search for filter selection, which increases the sample efficiency for the RL training. Experiments on MNIST, CIFAR-10, and ILSVRC-2012 validate the effec- tiveness of our approach compared to both traditional and automated existing channel pruning approaches."   

<img width="802" alt="image" src="https://user-images.githubusercontent.com/94199007/212781625-98fae8dd-b243-4a89-847b-95127f0913d6.png">

## GAN based pruning.   

**Towards Optimal Structured CNN Pruning via Generative Adversarial Learning (CVPR 2020)**.  
[Paper](https://openaccess.thecvf.com/content_CVPR_2019/papers/Lin_Towards_Optimal_Structured_CNN_Pruning_via_Generative_Adversarial_Learning_CVPR_2019_paper.pdf).  
*Abstract*
> "Structured pruning of filters or neurons has received in- creased focus for compressing convolutional neural net- works. Most existing methods rely on multi-stage optimiza- tions in a layer-wise manner for iteratively pruning and re- training which may not be optimal and may be computation intensive. Besides, these methods are designed for pruning a specific structure, such as filter or block structures with- out jointly pruning heterogeneous structures. In this paper, we propose an effective structured pruning approach that jointly prunes filters as well as other structures in an end- to-end manner. To accomplish this, we first introduce a soft mask to scale the output of these structures by defining a new objective function with sparsity regularization to align the output of baseline and network with this mask. We then effectively solve the optimization problem by generative ad- versarial learning (GAL), which learns a sparse soft mask in a label-free and an end-to-end manner. By forcing more scaling factors in the soft mask to zero, the fast iterative shrinkage-thresholding algorithm (FISTA) can be leveraged to fast and reliably remove the corresponding structures. Extensive experiments demonstrate the effectiveness of GAL on different datasets, including MNIST, CIFAR-10 and Im- ageNet ILSVRC 2012. For example, on ImageNet ILSVRC 2012, the pruned ResNet-50 achieves 10.88% Top-5 error and results in a factor of 3.7× speedup. This significantly outperforms state-of-the-art methods."   

<img width="989" alt="image" src="https://user-images.githubusercontent.com/94199007/212780935-32d60598-1233-4dee-91d8-acbd6afafc8c.png">

## Filter pruning using criteria or learning. 
