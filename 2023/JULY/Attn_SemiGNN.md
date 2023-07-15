Attention Based GNN for semi-supervised learning
--------------------------
GNN alternates b/w a propagation layer that aggregates hidden state of local neighborhood and a fully connected layer. 
We check that linear model is able to achieve a performance comparable to state-of-the-art models. This reduces the number of parameters. This allows a room for designing more innovative prop layers as it reduces number of parameters. so we proposes    
* Remove all intermediate FC layers 
* relay propagation layers with attention    

TO overcome problem of limited labeled data is semi-supervised learning, using additional unlabled data.   
Addition unlabeled data here is available in form of graph.  

(a) greatly reduces model complexity, with only a single scalar parameter at each intermediate layer.    
(b) discovers dynamically and adaptively which nodes are releavant to the target node for classification
(c) Improves state of art methods in terms of accuracy on standard datasets.

Related work
---------
(1) Graph Laplacian based algorithm solving for locally consistent solutions    
L(X, Y<sub>L</sub>) = L<sub>label</sub>(X<sub>L</sub>, Y<sub>L</sub>) + &lambda;L<sub>G</sub>(X)    

(2) Expectation Maximization based algorithms    


Attention-based Graph Neural Network(AGNN)    
H<super>(1)</super> = ReLU(XW<super>(0)</super>) 
H<super>(t+1)</super> = P<super>(t)</super>H<super>(t)</super>   

Main difference of AGNN w.rt. this owrk is AGNN attention is computer over a neighborhood of a node on a graph, whereas in this work attention over set of all entities is used to construct a "soft neighborhood".    

Experiment on Benchmark Citation Networks
-------------------------------------
Benchmark Datasets
-----------------
citation network dataset consists of documents as nodes and citation links as directed edges. Each node has a human annotated topic from a finite set of classes and feature vector. 3 Datasets:-
1) CiteSeer
2) Cora
	Feature vector has binary entries indicating presence/absence of corresponding word from a dictionary.
3) PubMed 
	Feature vector has real-values entris TF-IDF	


