Non Linear Independent Component Estimation (NICE)
-------------------------------------
Deep Learning Framework for modeling complex high-dimensonal densities.    
Good Representation is one in which data has a distribution that is easy to model.     
Map it in such a way that it conform to a factorized distributon, i.e. resulting in independent latent variables.     
parameterize transformation so that computing determinant of Jacobian and inverse Jacobian is trivial.    
* Unbiased ancestral Sampling
* Factorized Distribution   

P<sub>H</sub>(h) = &Pi;pH<sub>d</sub>(h<sub>d</sub>)

Components H<sub>d</sub> should be independent. Proposed traning criterion is directly derived from log-likelihood.    
We consider a change of variables h = f(x) which assumes that f is invertible and dimension of h is same as diemention of x, in order to fit distribution p<sub>H</sub>.   
- Inference
- Sampling
- Inpainting

maximum likelihood using change of variables formula:-

NICE - invertible preprocessing tranform of dataset.   
i
ARCHITECTURE
-----------
- Triangular Structure
- Coupling Layer
	* General Coupling layer
	* Additive Coupling layer
	* Combining Coupling layer
- ALLOWING RESCALING
- PRIOR DISTRIBUTION

RELATED METHODS
------------------
Deep Boltzmann machines (DBM)
Markov Chain Monte Carlo (MCMC)
Annealed Improtance Sampling (AIS)
Variational Auto Encoders (VAE)
	Stochastic encoder q(h|X) and imperfect decoder p(x|h), 


