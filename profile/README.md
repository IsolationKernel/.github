## A brief history of Isolation-based methods 👋 

Isolation-based methods refer to methods that employ an isolation mechanism to construct isolating partitions in the input space. The first method is called Isolation Forest or iForest [1], a point anomaly detector, reported in IEEE ICDM 2008. The intuition is that anomalies are rare and different from normal points; thus each anomaly is more amenable to isolation than normal points. A point is said to be isolated if it is contained within an isolating partition that isolates it from the rest of the points in a sample. 


Isolation Forest is one of the most effective and efficient anomaly detectors created thus far. Since its introduction, it has been used widely in academia and industries. Its limitations, due to the use of tree structures, have been studied by different researchers. One improvement beyond tree structures is iNNE [2] which employs hyperspheres as the isolation mechanism. Both Isolation Forest and iNNE have also provided a new solution to the emerging new class (zero-shot) problem in data streams [24,25], a classification probblem that is seemingly unrelated to anomaly detection.


The development of isolation-based methods has grown outside the confines of anomaly detection since. In 2010, Isolation Forest is shown to be a special case of mass estimation [3] (i.e., an alternative to density estimation.)  


In 2018, a data dependent kernel called Isolation Kernel [4] or IK is first introduced as an alternative to data independent kernels such as Gaussian and Laplacian kernels. It has a unique characteristic:  two points, as measured by Isolation Kernel derived with a dataset in a sparse region, are more similar than the same two points, as measured by Isolation Kernel derived with a dataset in a dense region. This characteristic is derived from data directly; and IK has no closed form expression and does not require learning. Isolation Kernel has three implementations using different isolation mechanisms up to 2021 [4,5,6]. IK has been shown to be the key in achieving large scale online kernel learning [7], improving the efficacy & efficiency of t-SNE [15], and inspiring a new data dependent kernel as the key in building a persistence diagram which is robust to noise and varied densities in Topological data analysis [20].

[**Breaking news**] Isolation Kernel has just been shown to be the only measure that can find the exact nearest neighbor of a query in high dimensions----addressing a longstanding open problem in the study of curse of dimensionality [26].

In 2020, Isolation Distributional Kernel or IDK is introduced to measure the similarity of two distributions [6], based on the framework of kernel mean embedding [8]. The first application of IDK is a kernel-based point anomaly detector that needs no learning, unlike OCSVM [9]. Through IDK point anomaly detector, Isolation Forest is linked to a kernel-based method for the very first time. IDK has since been applied to 
* Group anomaly detection [10], graph classification via Isolation Graph Kernel [11], multi-instance learning [12], graph anomaly detection [18].
* IDK can be interpreted as a kernel density estimator called Isolation Kernel Density Estimator [13]. 
* A new class of clustering algorithms which employs IDK to grow a cluster by treating each cluster as a distribution. Two such methods are psKC (or point-set Kernel Clustering) [14], and IDKC (Isolation Distributional Kernel Clustering) [19]. They are the only clustering algorithms which are both effective and efficient---a quality which is all but nonexistent in current clustering algorithms. They are also the only kernel-based clustering algorithms which have linear time complexity.
* A new class of online Agglomerative Hierarchical Clustering [16].
* Change interval detection in data streams [23].
* Trajecotry retrieval, anomaly detection and clustering [21].
* A new treatment for timeseries [17,22]. This is a paradigm shift from the time domain and frequency domain approaches that have been around for more than 100 years.
* Spatial Transcriptomics [27].
* Explaining why many anomaly detectors could not justify their detected 'anomaly' to be rare and different from the majority of the instances in a given dataset under investigation [28].


## References
[1] Fei Tony Liu, Kai Ming Ting, Zhi-Hua Zhou (2008) Isolation Forest. Proceedings of IEEE ICDM, 413-422. [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Isolation%20Forest.pdf)

[2] Tharindu R. Bandaragoda, Kai Ming Ting, David Albrecht, Fei Tony Liu, Ye Zhu, Jonathan R. Wells (2018). Isolation-based Anomaly Detection using Nearest Neighbour Ensembles. Computational Intelligence. Doi:10.1111/coin.12156. [[pdf]](https://www.researchgate.net/publication/322359651_Isolation-based_anomaly_detection_using_nearest-neighbor_ensembles_iNNE)

[3] Kai Ming Ting, Guang-Tong Zhou. Fei Tony Liu, Swee Chuan Tan (2010). Mass Estimation and Its Applications. Proceedings of The 16th ACM SIGKDD Conference on Knowledge Discovery and Data Mining. 989-998. [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Mass%20Estimation%20and%20Its%20Applications.pdf)

[4] Kai Ming Ting, Yue Zhu, Zhi-Hua Zhou (2018). Isolation Kernel and Its Effect on SVM. Proceedings of The ACM SIGKDD Conference on Knowledge Discovery and Data Mining. 2329-2337. [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Isolation%20Kernel%20and%20its%20effect%20on%20SVM.pdf)

[5] Xiaoyu Qin, Kai Ming Ting, Ye Zhu, Vincent Cheng Siong Lee (2019). Nearest-Neighbour-Induced Isolation Similarity and Its Impact on Density-Based Clustering. Proceedings of The Thirty-Third AAAI Conference on Artificial Intelligence. 4755-4762. [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Nearest-Neighbour-Induced%20Isolation%20Similarity%20and%20Its%20Impact%20on%20Density-Based%20Clustering.pdf)

[6] Kai Ming Ting, Bi-Cun Xu, Washio Takashi, Zhi-Hua Zhou (2020). Isolation Distributional Kernel: A new tool for kernel based anomaly detection. Proceedings of The ACM SIGKDD Conference on Knowledge Discovery and Data Mining. 198-206. [[pdf]](https://doi.org/10.1145/3394486.3403062)

[7] Kai Ming Ting, Jonathan R. Wells, Takashi Washio (2021). Isolation Kernel: The X Factor in Efficient and Effective Large Scale Online Kernel Learning. Data Mining and Knowledge Discovery. [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Isolation%20Kernel-The%20X%20Factor%20in%20Efficient%20and%20Effective%20Large%20Scale%20Online%20Kernel%20Learning.pdf)

[8] Alex Smola, Arthur Gretton, Le Song, Bernhard Schölkopf. 2007. A Hilbert Space Embedding for Distributions. In Algorithmic Learning Theory, Marcus Hutter, Rocco A. Servedio, and Eiji Takimoto (Eds.). Springer, 13–31.

[9] Bernhard Schölkopf, John C. Platt, John C. Shawe-Taylor, Alex J. Smola, Robert C. Williamson. 2001. Estimating the Support of a High-Dimensional Distribution. Neural Computing 13, 7 (2001), 1443–1471.

[10] Kai Ming Ting, Bi-Cun Xu, Washio Takashi, Zhi-Hua Zhou (2022). Isolation Distributional Kernel: A new tool for kernel based point and group anomaly detections. IEEE Transactions on Knowledge and Data Engineering. ieeexplore.ieee.org/document/9573389. [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Isolation%20Distributional%20Kernel-A%20New%20Tool%20for%20point%20and%20group%20anomaly%20detection.pdf)

[11] Bi-Cun Xu, Kai Ming Ting, Yuan Jiang (2021). Isolation Graph Kernel. Proceedings of The Thirty-Fifth AAAI Conference on Artificial Intelligence. 10487-10495. [[pdf]](https://ojs.aaai.org/index.php/AAAI/article/view/17255)

[12] Bi-Cun Xu, Kai Ming Ting, Zhi-Hua Zhou (2019). Isolation Set-Kernel and Its Application to Multi-Instance Learning. Proceedings of The ACM SIGKDD Conference on Knowledge Discovery and Data Mining. 941-949. [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Isolation%20Set-Kernel%20and%20Its%20Application%20to%20Multi-Instance%20Learning.pdf)

[13]  Kai Ming Ting, Takashi Washio, Jonathan R. Wells, Hang Zhang (2021). Isolation Kernel Density Estimation. Proceedings of IEEE ICDM. 619-628 [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Isolation_Kernel_Density_Estimation.pdf)

[14] Kai Ming Ting, Jonathan R. Wells, Ye Zhu (2023) Point-set Kernel Clustering. IEEE Transactions on Knowledge and Data Engineering. Vol.35, 5147-5158 [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Point-Set%20Kernel%20Clustering.pdf)

[15] Ye Zhu, Kai Ming Ting (2021) Improving the Effectiveness and Efficiency of Stochastic Neighbour Embedding with Isolation Kernel. Journal of Artificial Intelligence Research 71, 667-695. [[pdf]](https://github.com/IsolationKernel/Codes/blob/main/PDF/Improving%20the%20Effectiveness%20and%20Efficiency%20of%20Stochastic%20Neighbour%20Embedding%20with%20Isolation%20Kernel.pdf)

[16] Xin Han, Ye Zhu, Kai Ming Ting, De-Chuan Zhan, Gang Li (2022) Streaming Hierarchical Clustering Based on Point-Set Kernel. Proceedings of The ACM SIGKDD Conference on Knowledge Discovery and Data Mining. [[pdf]](https://www.researchsquare.com/article/rs-1711503/v1.pdf)

[17] Kai Ming Ting, Zongyou Liu, Hang Zhang, Ye Zhu (2022) A New Distributional Treatment for Time Series and An Anomaly Detection Investigation. Proceedings of The Very Large Data Bases (VLDB) Conference. [[pdf]](https://www.vldb.org/pvldb/vol15/p2321-liu.pdf)

[18] Zhong Zhuang, Kai Ming Ting, Guansong Pang, Shuaibin Song (2023). Subgraph Centralization: A Necessary Step for Graph Anomaly Detection. Proceedings of The SIAM Conference on Data Mining. 

[19] Ye Zhu, Kai Ming Ting (2023).  Kernel-based Clustering via Isolation Distributional Kernel. Information Systems.

[20] Hang Zhang, Kaifeng Zhang, Kai Ming Ting,  Ye Zhu (2023). Towards a persistence diagram
that is robust to noise and varied densities. Proceedings of the 40th
International Conference on Machine Learning, pages 41952–41972.

[21] Zijing Wang, Ye Zhu, Kai Ming Ting (2023). Distribution-based trajectory clustering.
Proceedings of the International Conference on Data Mining.

[22] Kai Ming Ting, Zongyou Liu, Lei Gong, Hand Zhang, Ye Zhu (2024). A new distributional
treatment for time series anomaly detection. The VLDB Journal.

[23] Y. Cao, Y. Zhu, K. M. Ting, F. D. Salim, H. X. Li, L. Yang, G. Li (2024). Detecting
change intervals with isolation distributional kernel. Journal of Artificial
Intelligence Research, 79:273–306. [[pdf]](https://github.com/IsolationKernel/.github/blob/main/profile/PDF/iCID_JAIR.pdf)

[24] Xin Mu, Kai Ming Ting, and Zhi-Hua Zhou. 2017. Classification under streaming emerging new classes: A solution using completely-random trees. IEEE
Transactions on Knowledge and Data Engineering 29, 8 (2017), 1605–1618.

[25] Xin-Qiang Cai, Peng Zhao, Kai-Ming Ting, Xin Mu, and Yuan Jiang. 2019. Nearest
neighbor ensembles: An effective method for difficult problems in streaming
classification with emerging new classes. In  Proceedings of The IEEE International Conference on
Data Mining. 970–975.

[26] Kai Ming Ting, Takashi Washio, Ye Zhu, Yang Xu, Kaifeng Zhang,
Is it possible to find the single nearest neighbor of a query in high dimensions?
Artificial Intelligence,
Volume 336,
2024,
104206. [[pdf]](https://doi.org/10.1016/j.artint.2024.104206)

[27] Hang Zhang, Yi Zhang, Kai Ming Ting, Jie Zhang, Qiuran Zhao, Kernel-Bounded Clustering for spatial transcriptomics enables scalable discovery of complex spatial domains. Genome Research 2025 35(2):355–367. doi: 10.1101/gr.278983.124

[28] Kai Ming Ting, Zhong Zhuang, Guansong Pang, Zongyou Liu, Tianrun Liang, and Qiuran Zhao. 2025. What are anomalies in a network? ACM Transactions on Knowledge Discovery from Data. https://doi.org/10.1145/3723007
<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
-->
| | | | |
|-|-|-|-|
|Topological Data Analysis|Lamda Kernel|[ICML2023](PDF/ICML_TowardsaPersistenceDiagramthatisRobusttoNoiseandVariedDensities.pdf) |[code](https://github.com/IsolationKernel/Lambda-kernel.git)|
|IK-based methods|IK-OGD|[DMKD2021](PDF/DMKD2021.pdf)|[code](https://github.com/IsolationKernel/IK_OGD.git)|
| |IK-TSNE|[JAIR2021](PDF/JAIR2021.pdf)                           |[code](https://github.com/IsolationKernel/IK_TSNE.git)|
| |IKDE|[ICDM2021](PDF/ICDM2021_IsolationKernelDensityEstimation.pdf)                                                              |[code](https://github.com/IsolationKernel/IKDE.git)|
| |IK_Implementations |[AAAI2019](PDF/AAAI2019.pdf),[SIGKDD2018](PDF/SIGKDD2018_SVM.pdf)  |[code](https://github.com/IsolationKernel/IK_Implementations.git)|
| |High-dimensional Evaluation| |[code](https://github.com/IsolationKernel/High-dimensional_Evaluation.git)|
|Clustering Methods|psKC|[TKDE2023](PDF/TKDE_Point-Set_Kernel_Clustering.pdf)                                                                         |[code](https://github.com/IsolationKernel/psKC.git) |
| |IK-AHC|[PR2023](PDF/PR2023_AHC.pdf)                                                                                                                                       |[code](https://github.com/IsolationKernel/IK_AHC.git)|
| |IDKC|[IS2023](PDF/IS2023.pdf)                                                                                  | [code](https://github.com/zhuye88/IDKC.git)|
| |KBC in Spatial Transcriptomics|(Genome Research)                                                                                  | [code](https://github.com/IsolationKernel/Kernel-Bounded-Clustering-for-Spatial-Transcriptomics)|
| Data Streams |StreakHC: Online Hierarchical Clustering|[SIGKDD2022](PDF/SIGKDD2022_SHC.pdf)   |[code](https://github.com/IsolationKernel/StreaKHC.git)|
|  |iCID: Change Interval Detection| [JAIR2024](PDF/iCID_JAIR.pdf) |[code](https://github.com/IsolationKernel/iCID.git)|
|Graph|IGK for classification |[AAAI2021](PDF/AAAI2021.pdf)                                                              |[code](https://github.com/IsolationKernel/IGK.git)|
| |Graph Anomaly Detection|[SIAM2023](PDF/SIAM2023_SubgraphCentralization_ANecessaryStepforGraphAnomalyDetection.pdf)               |[code](https://github.com/IsolationKernel/GraphAnomalyDetection.git)|
|Trajectory|Trajectory Anomaly Detection |[JAIR2024](https://github.com/IsolationKernel/Codes/blob/main/PDF/JAIR2024.pdf)|[code](https://github.com/IsolationKernel/TrajectoryDataMining.git)|
| |TIDKC: Trajectory Clustering |[ICDM2023](https://github.com/IsolationKernel/Codes/blob/main/PDF/Distribution-Based_Trajectory_Clustering.pdf)|[code](https://github.com/IsolationKernel/TIDKC.git)|
|Time Series|Time Series Anomaly detection|[VLDB2022](PDF/VLDB2022.pdf)                                                                              |[code](https://github.com/IsolationKernel/TS.git)|
