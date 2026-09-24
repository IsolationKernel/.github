<a id="history"></a>

# A brief history of Isolation-based methods 👋

**Contents**

- [A brief history of Isolation-based methods](#history)
  - [Isolation Kernel (IK)](#isolation-kernel-ik)
  - [Isolation Distributional Kernel (IDK)](#isolation-distributional-kernel-idk)
- [Projects and code](#projects-and-code)
- [References](#references)

Isolation-based methods refer to methods that employ an isolation mechanism to construct isolating partitions in the input space. The first method is called Isolation Forest or iForest [[3]](#ref-3), a point anomaly detector, reported in IEEE ICDM 2008. The intuition is that anomalies are rare and different from normal points; thus each anomaly is more amenable to isolation than normal points. A point is said to be isolated if it is contained within an isolating partition that isolates it from the rest of the points in a sample.


Isolation Forest is one of the most effective and efficient anomaly detectors created thus far. Since its introduction, it has been used widely in academia and industries. Its limitations, due to the use of tree structures, have been studied by different researchers. One improvement beyond tree structures is iNNE [[6]](#ref-6) which employs hyperspheres as the isolation mechanism. Both Isolation Forest and iNNE have also provided a new solution to the emerging new class (zero-shot) problem in data streams [[5]](#ref-5),[[10]](#ref-10), a classification probblem that is seemingly unrelated to anomaly detection.


The development of isolation-based methods has grown outside the confines of anomaly detection since. In 2010, Isolation Forest is shown to be a special case of mass estimation [[4]](#ref-4) (i.e., an alternative to density estimation.)


## Isolation Kernel (IK)

In 2018, a data dependent kernel called Isolation Kernel [[7]](#ref-7) or IK is first introduced as an alternative to data independent kernels such as Gaussian and Laplacian kernels. It has a unique characteristic:  two points, as measured by Isolation Kernel derived with a dataset in a sparse region, are more similar than the same two points, as measured by Isolation Kernel derived with a dataset in a dense region. This characteristic is derived from data directly; and IK has no closed form expression and does not require learning. Isolation Kernel has three implementations using different isolation mechanisms up to 2021 [[7]](#ref-7),[[8]](#ref-8),[[11]](#ref-11). IK has been shown to be the key in
* enabling large scale online kernel learning [[12]](#ref-12),
* achieving effective and efficient embedding for retrieval of LLM embedded vector databases [[35]](#ref-35),
* empowering efficient and effective consistent neighborhood in multi-view anomaly detection [[34]](#ref-34),
* realizing binary hashing without learning for vector databases that are better than learning-to-hash, and its applications to trajectory and graph databases [[31]](#ref-31).
* improving agglomerative hierarchical clustering algorithms [[24]](#ref-24),
* improving the efficacy & efficiency of t-SNE [[15]](#ref-15), and
* inspiring a new data dependent kernel as the key in building a persistence diagram which is robust to noise and varied densities in Topological data analysis [[22]](#ref-22).

> [**Breaking news**] Isolation Kernel is the only measure that can find the exact nearest neighbor of a query in high dimensions----addressing a longstanding open problem in the study of curse of dimensionality [[27]](#ref-27).

## Isolation Distributional Kernel (IDK)

In 2020, Isolation Distributional Kernel or IDK is introduced to measure the similarity of two distributions [[11]](#ref-11), based on the framework of kernel mean embedding [[2]](#ref-2). The first application of IDK is a kernel-based point anomaly detector that needs no learning, unlike OCSVM [[1]](#ref-1). Through IDK point anomaly detector, Isolation Forest is linked to a kernel-based method for the very first time. IDK has since been applied to
* Group anomaly detection [[16]](#ref-16), graph classification via Isolation Graph Kernel [[13]](#ref-13) and multi-instance learning [[9]](#ref-9).
* IDK can be interpreted as a kernel density estimator called Isolation Kernel Density Estimator [[14]](#ref-14).
* IDK-based Clustering is a new class of clustering algorithms which employs IDK to grow a cluster by treating each cluster as a distribution. Three such methods are psKC (or point-set Kernel Clustering) [[19]](#ref-19), IDKC (Isolation Distributional Kernel Clustering) [[21]](#ref-21) and Kernel Bounded Clustering [[32]](#ref-32). They are the only clustering algorithms which are both effective and efficient---a quality which is all but nonexistent in current clustering algorithms. They are also the only kernel-based clustering algorithms which have linear time complexity.
* A new class of online Agglomerative Hierarchical Clustering [[17]](#ref-17).
* Change interval detection in data streams [[26]](#ref-26).
* Trajectory retrieval, anomaly detection [[28]](#ref-28) and clustering [[23]](#ref-23), as well as category-based trajectory retrieval [[36]](#ref-36).
* A new treatment for timeseries [[18]](#ref-18),[[25]](#ref-25). This is a paradigm shift from the time domain and frequency domain approaches that have been around for more than 100 years.
* Clustering Spatial Transcriptomics data [[29]](#ref-29), and online automatic modulation classification [[39]](#ref-39).
* Explaining why many anomaly detectors could not justify their detected 'anomaly' to be rare and different from the majority of the instances in a given dataset under investigation [[30]](#ref-30).
* Streaming anomaly detection [[33]](#ref-33).
* The first distribution-based feature attribution for explaining the predictions of any classifier [[37]](#ref-37).
* Graph anomaly detection [[20]](#ref-20), and case-based interpretability in graph-level anomaly detection [[38]](#ref-38)


> [**Breaking news**] An IDK-based Clustering called Kernel-bounded clustering achieves the objective of spectral clustering (SC) without eigendecomposition---the unquestioned tool in 50 years of SC research [[32]](#ref-32).

> The first book on this topic is: [Isolation-Inspired Machine Learning: To Succeed when Deep Learning Fails](https://link.springer.com/book/9789819231508)

## Projects and code

| Area | Project | Paper | Code |
| --- | --- | --- | --- |
|IK-based methods|IK-OGD|[DMKD2021](PDF/DMKD2021.pdf) [[12]](#ref-12)|[code](https://github.com/IsolationKernel/IK_OGD.git)|
| |IK-TSNE|[JAIR2021](PDF/JAIR2021.pdf) [[15]](#ref-15)                           |[code](https://github.com/IsolationKernel/IK_TSNE.git)|
| |IKDE|[ICDM2021](PDF/ICDM2021_IsolationKernelDensityEstimation.pdf) [[14]](#ref-14)                                                              |[code](https://github.com/IsolationKernel/IKDE.git)|
| |IK_Implementations |[AAAI2019](PDF/AAAI2019.pdf) [[8]](#ref-8),[SIGKDD2018](PDF/SIGKDD2018_SVM.pdf) [[7]](#ref-7)  |[code](https://github.com/IsolationKernel/IK_Implementations.git)|
| |High-dimensional Evaluation| |[code](https://github.com/IsolationKernel/High-dimensional_Evaluation.git)|
|Clustering Methods|psKC|[TKDE2023](PDF/TKDE_Point-Set_Kernel_Clustering.pdf) [[19]](#ref-19)                                                                         |[code](https://github.com/IsolationKernel/psKC.git) |
| |IK-AHC|[PR2023](PDF/PR2023_AHC.pdf) [[24]](#ref-24)                                                                                                                                       |[code](https://github.com/IsolationKernel/IK_AHC.git)|
| |IDKC|[IS2023](PDF/IS2023.pdf) [[21]](#ref-21)                                                                                  | [code](https://github.com/zhuye88/IDKC.git)|
| |Kernel-bounded-clustering-versus-spectral-clustering|[AIJ2025](PDF/KBCAIJ2025.pdf) [[32]](#ref-32)                                  | [code](https://github.com/IsolationKernel/Kernel-bounded-clustering-versus-spectral-clustering)|
| |KBC in Spatial Transcriptomics|[GR](PDF/Genome_Res2025_KBC.pdf) [[29]](#ref-29)                                                                                  | [code](https://github.com/IsolationKernel/Kernel-Bounded-Clustering-for-Spatial-Transcriptomics)|
| Data Streams |StreakHC: Online Hierarchical Clustering|[SIGKDD2022](PDF/SIGKDD2022_SHC.pdf) [[17]](#ref-17)   |[code](https://github.com/IsolationKernel/StreaKHC.git)|
|  |iCID: Change Interval Detection| [JAIR2024](PDF/iCID_JAIR.pdf) [[26]](#ref-26) |[code](https://github.com/IsolationKernel/iCID.git)|
|Graph|IGK for classification |[AAAI2021](PDF/AAAI2021.pdf) [[13]](#ref-13)                                                              |[code](https://github.com/IsolationKernel/IGK.git)|
| |Graph Anomaly Detection|[SIAM2023](PDF/SIAM2023_SubgraphCentralization_ANecessaryStepforGraphAnomalyDetection.pdf) [[20]](#ref-20)               |[code](https://github.com/IsolationKernel/GraphAnomalyDetection.git)|
|Trajectory|Trajectory Anomaly Detection |[JAIR2024](https://github.com/IsolationKernel/Codes/blob/main/PDF/JAIR2024.pdf) [[28]](#ref-28)|[code](https://github.com/IsolationKernel/TrajectoryDataMining.git)|
| |TIDKC: Trajectory Clustering |[ICDM2023](https://github.com/IsolationKernel/Codes/blob/main/PDF/Distribution-Based_Trajectory_Clustering.pdf) [[23]](#ref-23)|[code](https://github.com/IsolationKernel/TIDKC.git)|
|Time Series|Time Series Anomaly detection|[VLDB2022](PDF/VLDB2022.pdf) [[18]](#ref-18)                                                                              |[code](https://github.com/IsolationKernel/TS.git)|
|Topological Data Analysis|Lamda Kernel|[ICML2023](PDF/ICML_TowardsaPersistenceDiagramthatisRobusttoNoiseandVariedDensities.pdf) [[22]](#ref-22) |[code](https://github.com/IsolationKernel/Lambda-kernel.git)|

## References
<a id="ref-1"></a>[1] Bernhard Schölkopf, John C. Platt, John C. Shawe-Taylor, Alex J. Smola, Robert C. Williamson. (2001). Estimating the Support of a High-Dimensional Distribution. Neural Computing 13, 7, 1443–1471. [[pdf]](https://alex.smola.org/papers/2001/SchPlaShaSmoetal01.pdf)

<a id="ref-2"></a>[2] Alex Smola, Arthur Gretton, Le Song, Bernhard Schölkopf. (2007). A Hilbert Space Embedding for Distributions. In Algorithmic Learning Theory, Marcus Hutter, Rocco A. Servedio, and Eiji Takimoto (Eds.). Springer, 13–31. [[pdf]](https://alex.smola.org/papers/2007/SmoGreSonSch07.pdf)

<a id="ref-3"></a>[3] Fei Tony Liu, Kai Ming Ting, Zhi-Hua Zhou (2008) Isolation Forest. Proceedings of IEEE ICDM, 413-422. [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Isolation%20Forest.pdf)

<a id="ref-4"></a>[4] Kai Ming Ting, Guang-Tong Zhou. Fei Tony Liu, Swee Chuan Tan (2010). Mass Estimation and Its Applications. Proceedings of The 16th ACM SIGKDD Conference on Knowledge Discovery and Data Mining. 989-998. [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Mass%20Estimation%20and%20Its%20Applications.pdf)

<a id="ref-5"></a>[5] Xin Mu, Kai Ming Ting, and Zhi-Hua Zhou (2017). Classification under streaming emerging new classes: A solution using completely-random trees. IEEE
Transactions on Knowledge and Data Engineering 29, 8, 1605–1618. [[pdf]](https://cs.nju.edu.cn/zhouzh/zhouzh.files/publication/tkde17sencForest.pdf)

<a id="ref-6"></a>[6] Tharindu R. Bandaragoda, Kai Ming Ting, David Albrecht, Fei Tony Liu, Ye Zhu, Jonathan R. Wells (2018). Isolation-based Anomaly Detection using Nearest Neighbour Ensembles. Computational Intelligence. Doi:10.1111/coin.12156. [[pdf]](https://www.researchgate.net/publication/322359651_Isolation-based_anomaly_detection_using_nearest-neighbor_ensembles_iNNE)

<a id="ref-7"></a>[7] Kai Ming Ting, Yue Zhu, Zhi-Hua Zhou (2018). Isolation Kernel and Its Effect on SVM. Proceedings of The ACM SIGKDD Conference on Knowledge Discovery and Data Mining. 2329-2337. [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Isolation%20Kernel%20and%20its%20effect%20on%20SVM.pdf)

<a id="ref-8"></a>[8] Xiaoyu Qin, Kai Ming Ting, Ye Zhu, Vincent Cheng Siong Lee (2019). Nearest-Neighbour-Induced Isolation Similarity and Its Impact on Density-Based Clustering. Proceedings of The Thirty-Third AAAI Conference on Artificial Intelligence. 4755-4762. [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Nearest-Neighbour-Induced%20Isolation%20Similarity%20and%20Its%20Impact%20on%20Density-Based%20Clustering.pdf)

<a id="ref-9"></a>[9] Bi-Cun Xu, Kai Ming Ting, Zhi-Hua Zhou (2019). Isolation Set-Kernel and Its Application to Multi-Instance Learning. Proceedings of The ACM SIGKDD Conference on Knowledge Discovery and Data Mining. 941-949. [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Isolation%20Set-Kernel%20and%20Its%20Application%20to%20Multi-Instance%20Learning.pdf)

<a id="ref-10"></a>[10] Xin-Qiang Cai, Peng Zhao, Kai-Ming Ting, Xin Mu, and Yuan Jiang (2019). Nearest
neighbor ensembles: An effective method for difficult problems in streaming
classification with emerging new classes. In  Proceedings of The IEEE International Conference on
Data Mining. 970–975. [[pdf]](https://caixq1996.github.io/files/SENNE.pdf)

<a id="ref-11"></a>[11] Kai Ming Ting, Bi-Cun Xu, Washio Takashi, Zhi-Hua Zhou (2020). Isolation Distributional Kernel: A new tool for kernel based anomaly detection. Proceedings of The ACM SIGKDD Conference on Knowledge Discovery and Data Mining. 198-206. [[pdf]](https://doi.org/10.1145/3394486.3403062)

<a id="ref-12"></a>[12] Kai Ming Ting, Jonathan R. Wells, Takashi Washio (2021). Isolation Kernel: The X Factor in Efficient and Effective Large Scale Online Kernel Learning. Data Mining and Knowledge Discovery. [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Isolation%20Kernel-The%20X%20Factor%20in%20Efficient%20and%20Effective%20Large%20Scale%20Online%20Kernel%20Learning.pdf)

<a id="ref-13"></a>[13] Bi-Cun Xu, Kai Ming Ting, Yuan Jiang (2021). Isolation Graph Kernel. Proceedings of The Thirty-Fifth AAAI Conference on Artificial Intelligence. 10487-10495. [[pdf]](https://ojs.aaai.org/index.php/AAAI/article/view/17255)

<a id="ref-14"></a>[14]  Kai Ming Ting, Takashi Washio, Jonathan R. Wells, Hang Zhang (2021). Isolation Kernel Density Estimation. Proceedings of IEEE ICDM. 619-628 [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Isolation_Kernel_Density_Estimation.pdf)

<a id="ref-15"></a>[15] Ye Zhu, Kai Ming Ting (2021). Improving the Effectiveness and Efficiency of Stochastic Neighbour Embedding with Isolation Kernel. Journal of Artificial Intelligence Research 71, 667-695. [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Improving%20the%20Effectiveness%20and%20Efficiency%20of%20Stochastic%20Neighbour%20Embedding%20with%20Isolation%20Kernel.pdf)

<a id="ref-16"></a>[16] Kai Ming Ting, Bi-Cun Xu, Washio Takashi, Zhi-Hua Zhou (2022). Isolation Distributional Kernel: A new tool for kernel based point and group anomaly detections. IEEE Transactions on Knowledge and Data Engineering. ieeexplore.ieee.org/document/9573389. [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Isolation%20Distributional%20Kernel-A%20New%20Tool%20for%20point%20and%20group%20anomaly%20detection.pdf)

<a id="ref-17"></a>[17] Xin Han, Ye Zhu, Kai Ming Ting, De-Chuan Zhan, Gang Li (2022). Streaming Hierarchical Clustering Based on Point-Set Kernel. Proceedings of The ACM SIGKDD Conference on Knowledge Discovery and Data Mining. [[pdf]](https://www.researchsquare.com/article/rs-1711503/v1.pdf)

<a id="ref-18"></a>[18] Kai Ming Ting, Zongyou Liu, Hang Zhang, Ye Zhu (2022). A New Distributional Treatment for Time Series and An Anomaly Detection Investigation. Proceedings of The Very Large Data Bases (VLDB) Conference. [[pdf]](https://www.vldb.org/pvldb/vol15/p2321-liu.pdf)

<a id="ref-19"></a>[19] Kai Ming Ting, Jonathan R. Wells, Ye Zhu (2023). Point-set Kernel Clustering. IEEE Transactions on Knowledge and Data Engineering. Vol.35, 5147-5158 [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Point-Set%20Kernel%20Clustering.pdf)

<a id="ref-20"></a>[20] Zhong Zhuang, Kai Ming Ting, Guansong Pang, Shuaibin Song (2023). Subgraph Centralization: A Necessary Step for Graph Anomaly Detection. Proceedings of The SIAM Conference on Data Mining. [[pdf]](https://arxiv.org/pdf/2301.06794)

<a id="ref-21"></a>[21] Ye Zhu, Kai Ming Ting (2023).  Kernel-based Clustering via Isolation Distributional Kernel. Information Systems.

<a id="ref-22"></a>[22] Hang Zhang, Kaifeng Zhang, Kai Ming Ting,  Ye Zhu (2023). Towards a persistence diagram
that is robust to noise and varied densities. Proceedings of the 40th
International Conference on Machine Learning, pages 41952–41972. [[pdf]](PDF/ICML_TowardsaPersistenceDiagramthatisRobusttoNoiseandVariedDensities.pdf)

<a id="ref-23"></a>[23] Zijing Wang, Ye Zhu, Kai Ming Ting (2023). Distribution-based trajectory clustering.
Proceedings of the International Conference on Data Mining. [[pdf]](https://arxiv.org/pdf/2310.05123)

<a id="ref-24"></a>[24] Xin Han, Ye Zhu, Kai Ming Ting, Gang Li (2023). The impact of isolation kernel on agglomerative hierarchical clustering algorithms. Pattern Recognition 139, 109517. [[pdf]](PDF/PR2023_AHC.pdf)

<a id="ref-25"></a>[25] Kai Ming Ting, Zongyou Liu, Lei Gong, Hand Zhang, Ye Zhu (2024). A new distributional
treatment for time series anomaly detection. The VLDB Journal.

<a id="ref-26"></a>[26] Y. Cao, Y. Zhu, K. M. Ting, F. D. Salim, H. X. Li, L. Yang, G. Li (2024). Detecting
change intervals with isolation distributional kernel. Journal of Artificial
Intelligence Research, 79:273–306. [[pdf]](https://github.com/IsolationKernel/.github/blob/main/profile/PDF/iCID_JAIR.pdf)

<a id="ref-27"></a>[27] Kai Ming Ting, Takashi Washio, Ye Zhu, Yang Xu, Kaifeng Zhang (2024).
Is it possible to find the single nearest neighbor of a query in high dimensions?
Artificial Intelligence,
Volume 336,
104206. [[pdf]](https://doi.org/10.1016/j.artint.2024.104206)

<a id="ref-28"></a>[28] Yufan Wang, Zijing Wang, Kai Ming Ting, Yuanyi Shang (2024).
A Principled Distributional Approach to Trajectory Similarity Measurement and its Application to Anomaly Detection. Journal of Artificial Intelligence Research 79: 865-893 [[pdf]](https://www.jair.org/index.php/jair/article/download/15849/27020/38277)

<a id="ref-29"></a>[29] Hang Zhang, Yi Zhang, Kai Ming Ting, Jie Zhang, Qiuran Zhao (2025). Kernel-Bounded Clustering for spatial transcriptomics enables scalable discovery of complex spatial domains. Genome Research 35(2):355–367. doi: 10.1101/gr.278983.124 [[pdf]](https://genome.cshlp.org/content/35/2/355.full.pdf)

<a id="ref-30"></a>[30] Kai Ming Ting, Zhong Zhuang, Guansong Pang, Zongyou Liu, Tianrun Liang, and Qiuran Zhao. (2025). What are anomalies in a network? ACM Transactions on Knowledge Discovery from Data. https://doi.org/10.1145/3723007

<a id="ref-31"></a>[31] Yang Xu, Kai Ming Ting (2025).
Voronoi Diagram Encoded Hashing. ECML/PKDD: 87-103. [[conference pdf]](https://ecmlpkdd-storage.s3.eu-central-1.amazonaws.com/preprints/2025/research/preprint_ecml_pkdd_2025_research_223.pdf) Extended journal version: Yang Xu, Kai Ming Ting, Xinpeng Li, and Yunpeng Li (2026). VDeH: Voronoi Diagram Encoded Hashing for Effective andEfficient Similarity Search, Applicable to Different Types of Databases. Journal of Artificial Intelligence Research 86, Article 43

<a id="ref-32"></a>[32] Hang Zhang, Kai Ming Ting, Ye Zhu (2026).
Kernel-bounded clustering: Achieving the objective of spectral clustering without eigendecomposition,
Artificial Intelligence,
Volume 350,
https://doi.org/10.1016/j.artint.2025.104440. [[pdf]](PDF/KBCAIJ2025.pdf)

<a id="ref-33"></a>[33] Yang Xu, Yixiao Ma, Kaifeng Zhang, Zuliang Yang, Kai Ming Ting (2026).
IDK-S: Incremental Distributional Kernel for Streaming Anomaly Detection. AAAI: 16075-16082 [[pdf]](https://ojs.aaai.org/index.php/AAAI/article/download/38642/42604)

<a id="ref-34"></a>[34] Yang Xu, Hang Zhang, Yixiao Ma, Ye Zhu, Kai Ming Ting (2026).
SCoNE: Spherical Consistent Neighborhoods Ensemble for Effective and Efficient Multi-View Anomaly Detection. AAAI: 16083-16090 [[pdf]](https://ojs.aaai.org/index.php/AAAI/article/download/38643/42605)

<a id="ref-35"></a>[35] 	Zhibo Zhang, Yang Xu, Kai Ming Ting, Cam-Tu Nguyen(2026).
LLMs Meet Isolation Kernel: Lightweight, Learning-free Binary Embeddings for Fast Retrieval. ACL (Findings): 13601-13623 [[pdf]](https://aclanthology.org/2026.findings-acl.666.pdf)

<a id="ref-36"></a>[36] 	Yang Xu, Zuliang Yang, Kai Ming Ting (2026).
GeoPTH: A Lightweight Approach to Category-Based Trajectory Retrieval via Geometric Prototype Trajectory Hashing. AAAI: 27359-27367 [[pdf]](https://ojs.aaai.org/index.php/AAAI/article/download/39953/43914)

<a id="ref-37"></a>[37] 	Xinpeng Li, Kai Ming Ting (2026).
Distribution-Based Feature Attribution for Explaining the Predictions of Any Classifier. AAAI: 23221-23229 [[pdf]](https://ojs.aaai.org/index.php/AAAI/article/download/39490/43451)

<a id="ref-38"></a>[38] Qiuran Zhao, Kai Ming Ting, Xinpeng Li (2026).
Case-Based Interpretability in Graph-Level Anomaly Detection via Contrast with Normal Prototypes. ICCBR: 152-168

<a id="ref-39"></a>[39] Xinpeng Li, Zile Jiang, Kai Ming Ting, Ye Zhu (2026).
Online Automatic Modulation Classification Based on Distributional Signal Representation. KSEM: 198-210

<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
