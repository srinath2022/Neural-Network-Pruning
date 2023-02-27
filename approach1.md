# Using GAN to learn 'Good Pruning Masks'    

## Part 1 - Create a pipeline to generate mask using standard methods and retain good masks  
Randomise existing pruning techniques a little to generate various masks for the same initialization and pruning ratio.   
Colab - https://colab.research.google.com/drive/18u5n-ykZJrDqf1vYiPILnpwFSFf2gzjO?usp=sharing.  
   
As a starting point, I have selected the **LeNet5** model and **MNIST** datset for the experiments.   
The following pruning techniques were explored.   
1. Global Channel Prunning - based on L1 norm of weights in each channel
2. Global Channel Pruning - selecting channels at random

### Experiments    
First **LeNet5** is trained on **MNIST** datset for few epochs to get the best performing model **(accuracy = 0.989)**.  

#### Global Channel Prunning - based on L1 norm of weights in each channel    
The criteria for pruning a channel is based on (sum of L1 norms of its weights)/(total number of weights).   
Varying the sparsity from 0 to 95%, the best model is pruned based on the above criteria and retrained on the train dataset for few epochs.
Best model accuracy, pruned accuracy and retrained accuracy at every level of sparsity is calculated on the test dataset. The following figure summarizes the observations.   

![Unknown-2](https://user-images.githubusercontent.com/94199007/221704789-25f84193-e0ba-47f6-851e-cfcb4dc8d07d.png)

#### Global Channel Pruning - selecting channels at random    
Channels are selected at random and pruned until the desired sparsity is reached. Similar to above, pruning and retraining is performed for all sparsity levels ranging from 0-95% in steps of 5. The experiment is repeated twice to observe for any variations.

![Unknown](https://user-images.githubusercontent.com/94199007/221708640-3052e366-2775-412f-bd2b-e4d81d225a29.png)
![Unknown-3](https://user-images.githubusercontent.com/94199007/221708735-62eef9f3-19d4-46c2-bfc1-636760f5c814.png)


To check how random pruning is performing, a total of 20 trials of pruning (with 90% sparsity) and retraining is performed. 

![Unknown-4](https://user-images.githubusercontent.com/94199007/221708911-53a5eaaf-a580-4ab6-9447-7edb5fc9b716.png)

#### Observations   
From the graphs, it can be seen that the retrained accuracy is either reaching ~1(best model) or is stuck at the pruned accuracy. It might be possible that during pruning, the criteria might be pruning all the channels of a given layer and hence unable to improve any further.   

To confirm this reasoning, the above experiments are performed again by keeping track of layer wise sparsities at every step/trial. The figures are shown below.   

Global Channel Pruning - selecting channels at random.   

![Unknown-5](https://user-images.githubusercontent.com/94199007/221711567-23a96c72-c32b-4be8-8dd8-ee61d31799f4.png)
![Unknown-6](https://user-images.githubusercontent.com/94199007/221711598-d404c60e-2e5e-4c1d-8c65-41504d9e05fa.png)


Global Channel Pruning - selecting channels at random, 20 trials of pruning (with 90% sparsity).  

![Unknown-7](https://user-images.githubusercontent.com/94199007/221711732-69876cd7-278f-46d2-a375-a008d58d0aea.png)
![Unknown-8](https://user-images.githubusercontent.com/94199007/221711764-1f1f6077-a63c-4dc6-99a4-bcfb48266f80.png)


## Part 2 - Implement a GAN which could take in a given Network as parameter and generate probablistic mapping of channels for pruning     

