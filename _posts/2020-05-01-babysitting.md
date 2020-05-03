---
title: 'Training Neural Networks'
permalink: /posts/baby-sitting/
tags:
  - cool posts
  - category1
  - category2
---

This is one of the most essential part of training process. This needs one-time set up and has to be done almost always.

1. **One Time Setup**
  - Activation Functions:  
      
      Several options to pick from like sigmoid, tanh, ReLU, Leaky ReLU, Maxout, ELU. ReLU has almost completely replaced other activation functions owing to its advantage of fast convergence and computationally cheap. We can still go with tanh but should not expect much. Sigmoid is a bad idea in most of the cases.

  - Data Preprocessing

    Suppose if all the data is positive or negative. In that case we will always get gradients with repect to weights either postive or negative. This is bad for learning. Therefore, we should normalize the data to make it zero-centered. We can also scale the data to make variance equal to 1. As per my knowledge, I think we can go with other scale values as well but variance of 1 has become popular. We should scale so so that our model generalizes well. Otherwise, weights can get too higher and our model can overfit.

     x = (x-u)/$\sigma$


  - Weight Initialization:
    
      If initial weights are too small, neurons can saturate in deep networks. That is why Xavier initialization is used. 
      
      Xavier Initialization: W = np.random.randn(fan_in, fan_out) / np.sqrt(fan_in)

      But if we are using ReLU, this initialization breaks. We can see that ReLU truncates the signal to only keep positive values, essentialy reducing variance by half. He et al., 2015 came up with this and introduced a factor of 2. 

      He Initialization:  W = np.random.randn(fan_in, fan_out) / np.sqrt(fan_in/2)

  - Regularization

    We normalize data before feeding it to network. Why not give the same advantage to all the layers. Signal experience internal covariate shift after passing through each network. This is where we can normalize it by calculating mini-batch mean and variance at each layer. And then allow network to squash the range if it wants to. This is done using two parameters, gamma and beta. 

  - Gradient Checking

    To make sure that the implementation of backprop in the code is correct, it is advisable to check gradient values numerically.

    Mathematical Definition of Derivative:

     <img src="https://github.com/sportsunrahul/sportsunrahul.github.io/blob/master/images/training/gradient_mathematical.PNG?raw=true" alt="Photo" style="width: 450px;"/> 

    Numeric Approximation:

     <img src="https://github.com/sportsunrahul/sportsunrahul.github.io/blob/master/images/training/gradient_analytical.PNG?raw=true" alt="Photo" style="width: 450px;"/> 


2. **Training Dynamics**
  - Babysitting the learning process
  - Parameter updates
  - Hyperparameter optimization



Aren't headings cool?


Reference: http://cs231n.stanford.edu/slides/2017/cs231n_2017_lecture6.pdf
