Graph Neural Network with Convolutional ARMA filters
----------------------
GNN do conv op on graph based on polynomial spectral filters. Here we use auto-regressive moving average filter providing robust freq. response compared to polynomial ones.   
GNNs lies b/w DL and methods for structured data. GNN combines node features with local neighborhoods to directly map into categorical labels or real values. or can be used to generate graph embeddings for graph classification/regression.


GNNs implement graph filters as low order polynomials to avoid expensive spectral decomposition and projection in freq domain. Polynomial filters have finite impulse response and perform weighted moving average filtering of graph signals on local node neighborhoods. It allows fast distributed implementations such as Chebyshev polynomials and Lanczos iteration.     
-ves: Polynomial filters have limited modeling capabilities due to smoothness and can't model sharp changes in freq. response.    



ARMA layers implements a non-linear and trainable graph filter generalizing conv layers based on poly filters. ARMA captures global structures with fewer para. ARMA are not localized in node space and requires to compute matrix inversion, which is intractable so we use ARMA layer as recursive formulation leading to fast/distributed implementation exploiting sparse operations on tensors. Resulting filters are not learned in fourier space induced by given laplacian, but are localized in node space and not dependant on graph structure.    


Graph Spectral Filtering
-------------------
Graph filter is an operator modifying components of X on eigenvectors basis of L, according to freq. response h acting on each eigenvalue lambda. L = I(m) - D<sup>-1/2</sup>AD<sup>-1/2</sup> is symmetrically normalized laplacian with spectral docomposition L = sum(lambda<sub>m</sub>u<sub>m</sub>u<sub>m</sub><sup>T</sup>.     

h<sub>POLY</sub>(lambda) = sum(w<sub>k</sub>lambda<sup>k</sup>)     
performs a weighted moving average of graph signal. This overcome limitation of spectral docomposition as they avoid eigendecompositon and their parameters are independent of Laplacian spectrum. Polynomial filters are localized in node space since ouput in filtered signal is linear combination of nodes with K-hop neighborhoods.    
Order of polynomial K is small and independent of M in graph.

Chebyshev polynomial are using in signal processing as they attenuate unwanted oscillations around cut-off freq which are eigenvalues of Laplacian.  T<sub>x</sub>(x) =2xT<sub>k-1</sub>(x) - T<sub>k-2</sub>(x).     

ARMA filter can approximate well any desired filter response h(&Lambda)  

