# Neural-Network-Pruning
Exploring model compression algorithms and experimenting new ideas for NN pruning.   

[related-work](related-work.md)   

## High Level Approaches   

### 1 : Using GAN to learn distribution of 'Good Pruning Masks'.     
Use existing algorithms like IMP to generate various masks(which achieve a reasonable test accuracy) for channel pruning in a given network. Train a GAN which could learn the distribution of these good enough masks.   
   
[Details and Experiments](approach1.md). 
   
### 2 : Enhancement to AutoML, by using 'Learned Filter Pruning Criteria' instead of mere magnitude based criteria.   

The idea is essentially to combine two papers, [Learning Filter Pruning Criteria for Deep Convolutional Neural Networks Acceleration (CVPR 2020)](https://openaccess.thecvf.com/content_CVPR_2020/papers/He_Learning_Filter_Pruning_Criteria_for_Deep_Convolutional_Neural_Networks_Acceleration_CVPR_2020_paper.pdf) and [AMC: AutoML for Model Compression and Acceleration on Mobile Devices (ECCV 2018)](https://openaccess.thecvf.com/content_ECCV_2018/papers/Yihui_He_AMC_Automated_Model_ECCV_2018_paper.pdf).   

## *Useful Links*.  
1. https://pytorch.org/tutorials/intermediate/pruning_tutorial.html.  
2. https://pytorch.org/tutorials/beginner/blitz/cifar10_tutorial.html.  
