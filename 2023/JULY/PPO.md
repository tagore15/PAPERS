Proximal Policy Optimization
---------------------
Family of policy gradient methods alternating b/w sampling data through interaction with env and optimizing a surrogate objective function using SGD.     
Standard policy gradient methods perform one gradient update per data sample. These new methods are:-     
* Proximal Policy Optimizatio (PPO)
Have same benefits of TRPO (Trust Region Policy optimization) but are much simpler to implement.      

-ves Q-learning fails on many simple problems and is poorly understood.     
-ves Vanilla policy gradient methods have poor data efficiency and robustness.   
-ves TRPO is complicated and is not compatible with architectures that include noise (such as dropout)    

PPO uses first order optimization while attaining data efficieny and reliable performance of TRPO.    

On Atari, it performs better in terms of sample complexity than A2C and similaly to ACER (but much simpler)     

POLICY OPTIMIZATION
-----------------
Policy gradient methods work by computing an estimator of the policy gradient and plugging it into a stochastic gradient ascent algo. Most common gradient estimator has form      
ghat = E( &nabla;<sub>&theta;log&pi;(a<sub>t</sub>|s<sub>t</sub>)Ahat)

where pi is a stochastic policy and A is estimator of advantage function at timestep t. Here Expectation E indicates empirical average over a finite batch of samples. It alternates b/w sampling and optimization.      
Using auto differentiate software work by constructing an objective fn whose gradient is the policy gradient estimator    
L<sup>PG</sup>(&theta;) = E<sub>t</sub>[log&pi;<sub>&theta;(a<sub>t</sub>|s<sub>t</sub>)A]    

It is appealing to perform multiple steps of optimization on this loss but empirically it leads to destructively large policy updates.     

### Trust Region Methods
Here an objective fn is maximized subject to a constraint on the size of policy update.     
max(theta) E[&pi;theta(a<sub>t</sub> | s<sub>t</sub> A]  subject to E[KL[&pi;<sub>old(.|St), &pi;<sub>&theta;(.|S<sub>t</sub>)]] < &delta;    
this problem can be solved usig congugate gradient algo after making a linear approx to the objective and quadratic approx to constraint.    
Theory justify TRP actually suggests using a penalty instead of constraint i.e. solving unconstrained optimization problem

for some coef &beta;. TRPO uses a hard constraint rather than a penalty because it is hard to choose a single value of &beta; that performs well across different problems, Hence additional modifications are required.    


### Clipped Surrogate Objective    
 
