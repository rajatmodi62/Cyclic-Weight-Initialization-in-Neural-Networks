
# Background
FastAI lecture 1 [Pets Classification] had shown that there is a decrease in the
classification performance of Resnet18/34 when the entire network is trained without freezing.
An alternate way has been to tune the last layer only.

# Our Approach

We propose the following algorithm to overcome this issue:
```
Start
- Load the network with pretrained weights 
- For each epoch
  - For each batch 
    Compute the gradients of the loss function
    Weights at any layer= Pretrained weights + current*weights- alpha*gradients 
    end
   end
```
Rather than making the changes to the gradient descent equation at each iteration, we also experiment with the weight averaging at each epoch. 

# Results 
Training a subset of ImageNet dataset (11 classes) reaches a peak accuracy of 98.3% as compared to 97.2% obtained by freezing the pretrained layers. 

The dataset & pretrained weights of our Resnet models can be found [here](https://drive.google.com/open?id=1gaIZDIp1mwjpdwyCltBE4eHjNVLQQcn_)
