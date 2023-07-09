Graph Un-Nets
-----------
Pooling and unsampling operations are not natural on graph data so we propose:-    
* Graph Pooling(gPool)     
Adaptively selects some nodes to form a smaller graph based on their scalar projection values on a trainable projection vector.  

* unpooling(gUnpool)
restores graph ino origianl structure using position info of nodes selected in corresponding gPool layer.

Graph Pooling Layer
---------------
Pooling layers in CNN reduce feature map size and enlarge receptive fields. k-max pooling layers select k largest units out of each feature map. We can't apply pooling operations to graph as no locality info among nodes in graphs.     
In gPool layer, we adaptive select subset of nodes to from a new but smaller graph. We employ a trainable projection vector p. By projecting all nodes features to 1D, we can perform k-max pooling for node selection. Selection is based on 1D footprint of each node, connectivity is consistent across nodes.    



