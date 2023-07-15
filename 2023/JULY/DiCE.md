Dice: Infinity DIfferentiable Monte Carlo Estimator
---------------------
Score function estimator is used for estimating gradients of stochastic objectives in Stochastic computational Graph (SCG). It prodcues monte carlo estimates of gradients in settings with non-differentiable objectives e.g. in meta-learning and reinforcement learning.    

 
First order gradients by differentiating a surrogate loss (SL) is simple but challenging for higher order derivatives.    
1) Analytical derivation and implementation is laborious    
2) Repeatedly applying SL to construct new objectives for higher order derivatives involves graph manipulations.    

By DIce, provides a single objective that can be differentiated repeatedly, It relies on automatic differentiation for performing requisite graph manipulations.   

TO obtain higher score functions, there are 2 options:-    
1) analytically derive and implement the estimators    
2) repeatedly apply SL approach to construct new objectives   

DiCE uses a operator (MAGICBOX), acts on set of stochastic nodes W<sub>c</sub> that influence each of the original losses in an SCG. 
$\nabla$<sub>&theta;</sub>(W<sub>c</sub>) = MAGICBOX(W<sub>c</sub>)$\nabla$<sub>&theta;</sub> SUM(log(p(w;&theta;)))

MAGICBOX operator is implemented in deep learning lib as:-    
MAGICBOX(W) = exp(tau - op(tau) where tau = sum(log(p(w;&theta;))) where op is an operator that sets gradient of operator to zero.


