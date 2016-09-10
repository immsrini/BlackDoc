---
layout: post
title: Understanding representation learning
comments: true
---

This post is the second in the series of understanding deep learning. To come up to speed with the current discussion, read the [previous]() post.

## Interpretations of representation learning
Deep learning has established that feature selection and engineering is not always useful. What do we replace future engineering with, in a representation learning framework? The objective is to learn a hierarchy of features which takes the output from the previous level as its input. The input to the next consequent level is the output of the previous level. Traditional algorithms like SVM and regressions are considered as "shallow" representations since these methods directly carry out classification from input data and do not have intermediate layers. This is where this type of representation learning gets its name "deep."

So how do we interpret this framework? There exists two main type of understanding the performance of this architecture viz.:
<ul>
	<li>Probabilistic graphical models</li>
	<li>Neural Network Models</li>
</ul>
<br/>

#### Probabilistic graphical models:

The nodes of a PGM in each layer are considered as latent random variables <span>$$x$$</span> and the hidden random variable <span>$$h$$</span> and their joint probability distribution function <span>$$p(x,h)$$</span>. This model represents the data as collection of random
variables <span>$$X_1, … X_n$$</span> with joint distribution <span>$$P(X_1,…,X_n)$$</span> and *learn* the distribution from data and inference (compute conditional
distributions) <span>$$P(X_i | X_1 = x_1, …, X_m = x_m)$$</span>

#### Neural Network Models

The nodes in this type of model are considered as neurons that perform some nonlinear logical operation like a [sigmoidal function](https://en.wikipedia.org/wiki/Sigmoid_function) or [rectifier linear unit](https://en.wikipedia.org/wiki/Rectifier_(neural_networks)) or [Tanh](https://en.wikipedia.org/wiki/Hyperbolic_function) on the output it receives from the previous layers.

In the next post we shall consider an example and build towards analysing the Restricted Boltzmann Machines (RBM) and Auto-Encoders from PGM and NN perspective.
