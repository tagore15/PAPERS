Constrained Update Projection Approach to Safe Policy Optimization
-------------------------------------------------------------

Safe RL, we not only optimize reward but also avoid unsafe areas. CUP is policy optimization method based Constrained Update Projection framework. We apply a new surrogate functions along with performance bound. CUP enjoys the benefits of:-    
1) CUP generalizes the surrogate functions to generalized advantage estimator (GAE)
2) CUP unifies performance bounds, providing a better understanding and interpretability 
3) CUP provides non-convex implementation via only first-order otimizers.     


Policy Gradient and Generalized Advantage Estimators (GAE)
------------------------
Policy Gradient is used to solve policy optimization. It maximizes the expected total reward by estimating gradient 
g = gradient(J(&pi;<sub>&theta;</sub>) = E[&Sigma;&psi;gradient(log&pi;<sub>&theta;(a<sub>t</sub>|s<sub>t</sub>])
