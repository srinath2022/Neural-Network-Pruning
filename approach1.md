# Using GAN to learn 'Good Pruning Masks'.  

## Part 1 - Create a pipeline to generate mask using standard methods and retain good masks.
Randomise existing pruning techniques a little to generate various masks for the same initialization and pruning ratio.   
Colab - https://colab.research.google.com/drive/18u5n-ykZJrDqf1vYiPILnpwFSFf2gzjO?usp=sharing.  
   
As a starting point, I have selected the **LeNet5** model and **MNIST** datset for the experiments.   
The following pruning techniques were explored.   
1. Global Channel Prunning - based on L1 norm of weights in each channel (divided by total number of weights.)
2. Global Channel Pruning - selecting channels at random

### Experiments.  
First **LeNet5** is trained on **MNIST** datset for few epochs to get the best performing model **(accuracy = 0.989)**.  

#### Global Channel Prunning - based on L1 norm of weights in each channel (divided by total number of weights.).  
Varying the sparsity from 0 to 95, the best model is pruned based on the above criteria and retrained on the train dataset for few epochs.
Best model accuracy, pruned accuracy and retrained accuracy at every level of sparsity is calculated on the test dataset. The following figure summarizes the observations.   

![Unknown-2](https://user-images.githubusercontent.com/94199007/221704789-25f84193-e0ba-47f6-851e-cfcb4dc8d07d.png)

   
## Part 2 - Implement a GAN which could take in a given Network as parameter and generate probablistic mapping of channels for pruning.   

