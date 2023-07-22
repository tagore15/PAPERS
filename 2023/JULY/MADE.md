Masked Autoregressive Flow for Density Estimation
---------------------------------
Autoregressive are best neural density estimators.   
By constructing a stack of autoregressive models, each modelling the random numbers of the next model in the stack, we obtain a type of normalizing flow for density estimation. Its related to Real NVP. 

Joint density p(x) is object of interest in machine lerning. 
Problem of estimating p(x) from set of examples {$$x_n$$} is at the core of probabilistic unsupervised learning and generative modelling.   
Other methods for genrative modeling:-     
* variational autoencoder
* genrative adversarial 

Neural density estimators differs from above that they 
+ provide exact density evaluation.    
+ suitable for application where the focus is on explicitly evaluating densities, rather than generating synthetic data.
+ Density estimators can learn suitable priors for data from large unlabelled datasets, for use in Bayesian inference.     
+ In Simulation-based likelihood free inference, conditional density estimators can learn models for likelihood.
+ can learn effective proposals for importance sampling or sequential monte carlo
+ can be used as flexible inference networks for amortized variational inference as part of variational autoencoder 

- challenge is to construct models that are flexible to represent complex densities, but have tractable density functions and learning algo. 

2 families of neural density estimators:-      
1) Autoregressive models    
Decompose joint density as product of conditionals  and model each conditional in turn.

2) Normalizing flows     
transform a base density (e.g. Gaussian) into target density by an invertible transformation with tractable Jacobian.

Viewing an autoregressive model as normalizing flow increases its flexibility by stacking multiple models of the same type.    

Masked Autoregressive Flow (MAF) uses Masked Autoencoder for Distribution Estimation (MADE) as building block. 
+ enables density evaluations w/o the sequential loop typical of autoregressive models sof fast to evaluate and train on parallel architectures like GPU.    

Autoregressive density estimation
------------------------------
Using chain rule of probability     
$$p(x) = \prod_ip(x_i|x_{1:i-1})$$

model each conditional as parameteric density whose parameters are fn of hidden state $$h_i$$. In recurrent architectures, $h_i} is fn of previous hidden state $h_{i-1}$
