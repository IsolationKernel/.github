# Nanjing Workshop on

## Advances and Lessons Learned in 70 years of Clustering Research

**Co-Chairs: Kai Ming Ting, Daniel Aloise, Ricardo J.G.B. Campello**

**21-23 May 2027, Nanjing China**

Research in clustering has progressed significantly since 1957, with the introduction of Lloyd’s algorithm [[1]](#ref-1). Over the decades, the field has evolved from k-means clustering and Gaussian mixture models to density-based clustering, spectral clustering, support vector clustering, and, more recently, deep clustering. Despite this methodological evolution, several fundamental questions have persisted.

The definition of clustering as “the grouping of similar objects” [[2]](#ref-2) has served as a starting point for much of the field, including (i) the design of clustering algorithms; (ii) computational complexity analyses showing that many fundamental clustering optimization problems are NP-hard; and (iii) axiomatic analyses, including the Impossibility Theorem for Clustering, which shows that no clustering function can satisfy three natural axioms simultaneously [[3]](#ref-3).

At the same time, despite nearly 70 years of research, the prevailing choice for very large-scale datasets remains, at least until recently, k-means or one of its scalable variants. This is not because it produces the best clustering outcomes, but because it offers a particularly attractive trade-off between simplicity, computational efficiency, and scalability in the face of increasingly large data volumes.

Clustering very high-dimensional datasets also remains an open challenge. Such datasets may contain thousands of potentially noisy or irrelevant features that obscure underlying cluster structure and weaken the mechanisms on which traditional clustering algorithms rely, due to various manifestations of the curse of dimensionality. Deep clustering attempts to address this issue by transforming the original data into a lower-dimensional embedding through complex learned mappings. However, this can reduce interpretability and may ultimately create a different, potentially artificial, clustering problem in the learned representation space.

Given the above background, the workshop aims to discuss the following issues:

- What are the notable advances?
- Is deep clustering the answer?
- What are the key challenges?
- What is the progress towards each of the challenges?
- What are the lessons learned in the 70 years of research?
- Is clustering an NP-hard problem, given the latest result [[4]](#ref-4)?
- Potential future directions

## References

<a id="ref-1"></a>[1] Lloyd. Least square quantization in PCM. Bell Telephone Laboratories Paper, 1957. Published in journal later: Lloyd. Least squares quantization in PCM. IEEE Transactions on Information Theory, 1982.

<a id="ref-2"></a>[2] Hartigan. Clustering Algorithms. 1975.

<a id="ref-3"></a>[3] Kleinberg. An impossibility theorem for clustering. In Advances in Neural Information Processing Systems, 2002

<a id="ref-4"></a>[4] Zhang, Ting, Zhu. Kernel-bounded clustering: Achieving the objective of spectral clustering without eigendecomposition. Artificial Intelligence, 2026

<a id="ref-5"></a>[5] NIPS 2005 Workshop on Theoretical Foundations of Clustering http://people.kyb.tuebingen.mpg.de/ule/clustering_workshop_nips05/workshop_description.html

## Workshop Organizers

- Kai Ming Ting, School of ArtificiaI Intelligence, Nanjing University, China
- Daniel Aloise, Department of Computer Engineering and Software Engineering, Polytechnique Montréal, Canada
- Ricardo J.G.B. Campello, Department of Mathematics and Computer Science, University of Southern Denmark, Denmark
