CNNs on Graphs with Fast Localized Spectral Filtering
----------------------------------------
generalize CNN from low-dimensional regular grids, to high dimensional irregular domains,.   
Major bottleneck of CNN for graphs are localized graph filters which are efficient to evaluate and learn.    

This works gives:-
1. Spectral Formulation     

2. Strictly Localized Filters    

3. Low Computational Complexity 

4. Efficient Pooling  

5. Experimental Results

Graph Fourier Transform
----------------------
Signal s: v -> $ defined on nodes of graph x belongs R<super>n</super>. x<sub>i</sub> is value of x at i<sup>th</sup> node. 
Graph Laplacian 
Combinatorial definition is (L = D - W) where D is diagnoal degree matrix and W is weighted adjacency matrix. 
Normalized definition is (L = I<sub>n</sub> - D<sup>-1/2</sup> W D<sup>-1/2</sup>) where I<sub>n</sub> is identity matrix. L is real symmetric positive definite matrix. It has a complete set of orthonormal eigenvectors known as graph Fourier modes and their associated ordered real nonnegative eigenvalues. identified by frequency of graph.   

Spectral Filtering of graph signals
---------------------------------
* Polynoial filter
* Kronecker delta function
* Spectral filters


Polynomal Parameterization for localized filters
--------------------------------------

Recursive Formulation for fast filtering
------------------------ 
* Fourier basis
* Chebyshev expansion
* wavelets
* Lanczos algorithm
* Krylov subspace
* Hilbert space

