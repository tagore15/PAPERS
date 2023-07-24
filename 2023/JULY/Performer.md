RETHINKING ATTENTION WITH PERFORMER
---------------------------
Transformer architectures which can estimate regular (softmax) full-rank attention Transformers with provable accuracy, but using only linear (not quadratic) space and time complexity.
Also, doesn't rely on any priors such as sparsity or low-rankness.     
To approximate softmax attention-kernels, Performers use  a novel 
**** Fast Attention Via positive Orthogonal Random features approach (FAVOR+)  ****
It can be used to efficeintly model kernelizable attention mechansim beyound softmax. 
Performers are linear architectures fully compatible with regular Transformers and with strong theoretical guarantees: unbiased or nearly-unbiased estimation of attention matrix, uniform convergence and low estimation variance. 


Bidirection dot product attention:-    
---------------------------------
$$ Q, K, V \in \mathbb{R}^{L X d} $$

$$A \in \mathbb{R} ^{L X L}$$

$$Att_{\leftrightarrow}(Q, K, V) = D^{-1}AV,  A = exp(QK^T / \sqrt{d}), D = diag(A\mathbf{1}_L) $$


