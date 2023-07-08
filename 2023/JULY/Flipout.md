Stochastic Neural Networks weights are used in:-
* Regularization
* Bayesian Neural Networks
* Exploration in RL
* Evolution Strategies

2 methods of perturbation:-
* activations
	+ves:- easty to sample independently for different training examples. Allows the training algo to see more perturbations so variance decays as 1/N (Mini Batch Size). 
	
* weights
	+ves:-can be viewed as posterior uncertainty about parameters
	-ves:-expensive to commute as Stochastic Weights have a drawback that network has more weights than units. Typically done with single sample per mini-batch.

In order to reduce variance, gradients within a minibatch need not be independent, but uncorrelated.  This paper describes flipout, a method for decorrelating the gradients. 


LOCAL REPARAMETERIZATION TRICK
------------------
It's possible to reformulate weight perturbations as activation perturbations, allowing them to be efficiently computed fully independently for different examples.   
X - input minibatch
W - weight matrix
B = XW is matrix of activations

LRT samples the activations B rather than weights W. LRT is given by
Q(theta)(W[i][j])= N(mu, sigma) ==> Q(theta)(b[m][j] |x) = N(gamma, delta)
where gamma = sum(x[m][i] * mu[i][j]) and delta[m][j] = sum(x[m][i]^2. sigma[i][j]^2  
b[m][j] -- perturbed activation



FLIPOUT
---------
We make 2 observations:-
(1) perturbations of different weights are independent
(2) perturbation distribution is symmetric around zero

Under these assumptions, perturbation distribution is invariant to elementwise multiplication by a random sign matrix. (matrix with +-1 entries).    
Observation-1
q(thetha) <- perturbation distribution
delta(weight) ~ Dellta weight . E(random sign matrix)
deleta(weight) = delta(weight) . rn snT
rn, sn are random vectors with +-1 entries.    
Advantage of flipout over explicit perturbation is that computation can be done by matmul. 

 
