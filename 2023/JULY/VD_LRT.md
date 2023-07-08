Variational Dropout and the Local Reparameterization Trick
------------------------------
It has been shown that regular (binary) dropout has a Gaussian approximation called Gaussian dropout with virtually identical regularization performance but much faster convergence. Gaussian dropout optimizes a lower bound on the marginal likelihood of the data.   
Bayesian posteriror inference is theoretically attractive for controlling overfitting. exact inference is computationally intractable, but we can approximate by:-    
* MCMC (Markov Chain Monte Carlo)   
* variation inference - have been limited by high variance in the gradients.   

Dataset (D), set of N i.i.d observation (x, y)     
Goal - p(y|x, w)    
Prior - p(w)   
p(w//D) = p(w).p(D/w)/p(D)    

In variational inference, use as optimization problem to optimize q(phi)(w) as approx to p(w/D).     
L(phi) = -Dkl(q(phi)(w) || p(w)) + Ld(phi) where Ld(phi) = sum(x,y)E[logp(y|x, w)] = expected loglikelihood


Stochastic Gradient Variational Bayes (SGVB)
----------------------
we paraemterize random parameters w ~ qphi(w) as w = f(ephsilon, phi) where f(.) is differentiable fn. and epsilon ~p(epsilon) is noise.
   
Ld(phi) = LdSGVB(phi) = N/M sumlog(p(yi/xi, w=f(epsilon, phi))


Variance of SGVB estimator
-----------------
In practice, stochastic gradient ascent depends on variance of gradient.    


Local Reparameteterization Trick
-----------------------









