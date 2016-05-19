---
layout: about
---
# Compressive Sensing

<!-- with Prof. Barbot and Prof. Sun, collaboration between Wuhan Univ. and ECS-Lab. -->

 Compressive sensing is a new methodology to capture signals at sub-Nyquist rate. To guarantee exact recovery from compressed measurements, one should choose specific matrix, which satisfies the Restricted Isometry Property (RIP), to implement the sensing procedure.

In this work, we propose to construct the sensing matrix with chaotic sequence following a trivial method and prove that with overwhelming probability, the RIP of this kind of matrix is guaranteed. Meanwhile, its experimental comparisons with Gaussian random matrix, Bernoulli random matrix and sparse matrix are carried out and show that the performances among these sensing matrix are almost equal.

## References
-  [1] Yu Lei; Barbot, J.P.; Zheng Gang; Sun Hong; , "Compressive Sensing With Chaotic Sequence," Signal Processing Letters, IEEE, vol.17, no.8, pp.731-734, Aug. 2010.
-  [2] Yu Lei; Barbot, J.P.; Zheng Gang; Sun Hong; , "Toeplitz-structured Chaotic Sensing Matrix for Compressive Sensing," Communication Systems Networks and Digital Signal Processing (CSNDSP), 2010 7th International Symposium on, pp.229-233, 21-23 July 2010.
-  [3] Frunzete, M., Yu, L., Barbot, J., & Vlad, A. (2011, September). Compressive sensing matrix designed by tent map, for secure data transmission. In Signal Processing Algorithms, Architectures, Arrangements, and Applications Conference Proceedings (SPA), 2011 (pp. 1-6). IEEE.

# Sparse Coding with Cluster Structured Prior

In traditional framework of Compressive Sensing (CS), only sparse prior on the property of signals in time or frequency domain is adopted to guarantee the exact inverse recovery. Other than sparse prior, structures on the sparse pattern of the signal have also been used as an additional prior.

In this work, we exploit a hierarchical Bayesian framework (Graphical model) to model both sparsity and structure and infer an algorithm to solve the sparse inverse problems with structure priori. Particularly, by exploiting the latent variables, the sparse signals are considered as a hadamard product of latent variable and the weight variable, where the latent variable indicates whether the element is nonzero. Then, statistical models can be respectively built for the latent and weight variables: sparse inducing model on weight variables and structure promoting model on latent variables.


## Related References
