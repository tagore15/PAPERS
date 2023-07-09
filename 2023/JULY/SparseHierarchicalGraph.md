Towards Sparse Hierarchical Graph Classifiers
--------------------------------
Node embeddings are good for learning node and link classification. We are not sure how to use them for graph classification.    
* We can use a single global pooling step to aggregate node features.
* Hand designed features for hierarchical coarsening   


*Differentiable Graph Coarsening*  - reduce the size of graph in data-dependent manner like image downsampling within CNN.
Current approaches has quadratic complexity.    
Node classification is analogue to image segmentation.   
First end-to-end trainable graph CNN with learnable pooling operator is DiffPool.
Diffpool computes softclustering assignments of nodes from original graph in the pooled graph. Limitation of DiffPool is:-     
* computation of soft clustering assignments

Solution
-----
#### Convolutional Layers
- it is inductive.
MP(X,A) = sigma(inv(Dh).AhX(theta) + X(thetha))

#### Pooling Layers
Unlike DiffPool, computing a clustering of N nodes in [kn], we leverage Graph U-Net architecture which drops nodes from graph. Nodes to drop are decided by projection score against a learnable vector. 

#### Readout Layers
flattening operation keep info about input graph in fixed size representation. we do this by global avg pool in CNN. Further augment by global max pooling for better representations. 
