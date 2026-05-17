# 1. Introduction
## 1.1 Background:
The rapid expansion of internet-based services has transformed how governments deliver services to citizens. E-government platforms handle sensitive transactions including tax records, identity verification, healthcare data, and financial services. This creates a high-value target environment for malicious actors seeking to disrupt or exploit government infrastructure.
Network anomaly detection refers to the process of identifying patterns in network traffic that deviate significantly from established normal behavior. Unlike signature-based detection, anomaly detection systems do not rely on prior knowledge of specific attack patterns, making them theoretically capable of identifying both known and unknown threats.
Machine learning (ML) has emerged as a promising approach to automate the process of learning normal network behavior and flagging deviations. Algorithms such as clustering, classification trees, and neural networks can process large volumes of network data and build statistical models of normality that are continuously updated as traffic patterns evolve.
Sudan's e-government infrastructure faces particular challenges. Due to international sanctions, access to commercial network monitoring and threat detection solutions is restricted. This forces government agencies to rely on outdated or unpatched network equipment, leaving them vulnerable to increasingly sophisticated network-level attacks.

### 1.2 Problem Formulation:
Traditional network monitoring tools rely on predefined thresholds and static rules to identify suspicious behavior. These tools fail when attackers use slow, low-volume intrusion techniques or when attack patterns do not match known signatures.
As noted in [1], the core challenge in network security monitoring is that normal traffic patterns are highly dynamic and vary across time, user populations, and service types. Any detection system must therefore learn what is normal for a specific network environment before it can reliably identify what is abnormal. In this study we propose a machine learning framework to detect and classify network anomalies in Sudan's e-government infrastructure.
## 2. Problem Significance and Objectives
This research addresses the growing vulnerability of e-government networks in Sudan to cyber intrusions, denial-of-service attacks, and data exfiltration. The study will provide a framework applicable to government network administrators who currently lack effective automated monitoring tools.
Specific objectives are:

Review existing network anomaly detection techniques and benchmark datasets.
Identify the most discriminative network traffic features using statistical feature selection methods.
Design and evaluate ML models capable of detecting anomalous traffic with high accuracy and low false positive rates.
Develop a prototype anomaly detection system suitable for deployment in resource-constrained government network environments.
Assess the performance of the proposed system against known attack categories including DoS, probe, and unauthorized access attempts.

## 3. Related Work
3.1 Statistical Approaches to Anomaly Detection
Lakhina et al. [2] proposed using Principal Component Analysis (PCA) on network traffic flow data to separate normal traffic subspaces from anomalous ones. Their method operates on traffic aggregated at the flow level using SNMP data, allowing detection of large-scale anomalies such as distributed denial-of-service attacks and network scanning activity without requiring packet-level inspection. The approach demonstrated that anomalies manifest as signals in the residual subspace after normal traffic components are projected out.
3.2 Machine Learning Based Detection
Tavallaee et al. [3] conducted a detailed analysis of the KDD Cup 1999 dataset widely used in network intrusion detection research. Their work highlighted significant issues with the dataset including duplicate records that cause ML classifiers to be biased toward frequent attack types. They proposed a pre-processed version of the dataset — the NSL-KDD dataset — which has since become a standard benchmark for evaluating network anomaly detection algorithms. Their evaluation showed that decision tree-based classifiers achieved strong performance but struggled with rare attack categories.
3.3 Deep Learning Approaches
Javaid et al. [4] applied a deep learning architecture based on sparse autoencoders to the problem of network intrusion detection. Their model learned compact feature representations of network traffic in an unsupervised manner and used reconstruction error as an anomaly score. The approach showed improved detection rates for novel attack types compared to traditional shallow classifiers, supporting the use of representation learning for network anomaly detection.

## 4. Challenges and Suggestions
Signature-based limitations: Current network monitoring tools deployed in e-government environments use rule-based detection that requires frequent manual signature updates. Novel attack vectors — particularly those designed to evade known detection rules — are systematically missed. This results in a detection gap that grows as attackers develop more sophisticated evasion techniques.
Class imbalance: In real network traffic, attack instances represent a very small proportion of total traffic. Standard ML classifiers trained on imbalanced datasets tend to achieve high overall accuracy by classifying almost all traffic as normal, achieving very low detection rates for actual attacks [3]. Addressing this imbalance is a critical technical challenge.
Feature selection: Network traffic data contains a large number of potentially relevant features. Not all features contribute equally to anomaly detection, and irrelevant features can degrade classifier performance and increase computational cost. Statistical feature selection methods such as information gain and correlation-based filtering can identify the most discriminative features for a given network environment [5].
The proposed model for the machine learning approach is:

Step 1: Collect and pre-process raw network traffic into flow-level feature vectors
Step 2: Apply unsupervised clustering to identify natural traffic groupings and assign normality scores
Step 3: Apply feature selection to retain only the most discriminative traffic features
Step 4: Train supervised classifiers on labeled traffic samples using the selected features
Step 5: Combine unsupervised normality scores with supervised classification confidence to produce a final anomaly score
Step 6: Flag high-scoring traffic samples for analyst review and incorporate analyst feedback to retrain models iteratively

## 5. Research Methodology
The objective of this study is to develop a machine learning framework that detects network anomalies in e-government infrastructure with higher accuracy and lower false positive rates than existing rule-based systems. The following phases constitute the research methodology:

Review and analyze prior work on network anomaly detection, benchmark datasets, and ML algorithms used in this domain.
Collect representative network traffic data from e-government network environments or suitable public datasets such as NSL-KDD and CICIDS2017.
Apply information gain and correlation-based methods to identify and retain the most relevant traffic features.
Design and implement an ensemble detection model combining unsupervised anomaly scoring with supervised classification.
Evaluate the proposed model against baseline classifiers using standard metrics including detection rate, false positive rate, precision, recall, and F1-score.
Develop a lightweight prototype system suitable for deployment in resource-constrained network environments.

6. Research Planning
Objectives 1 and 2 will be carried out first, as reviewing existing work and collecting suitable datasets are prerequisites for all subsequent phases. Objectives 3 and 4 build directly on the outputs of the review and data collection phases and are expected to be achievable within the first year of the program.
Objective 5 involves system design and implementation, which is the most technically ambitious phase. It is estimated to require the greater part of the second year. The following estimations are based on several factors:

The duration of the master's program (24 months)
The complexity of designing and validating a novel ensemble detection approach
The availability of representative network traffic data from Sudanese e-government networks

These remain estimates subject to a tolerance margin, giving a maximum research timeline of 25 months.

## 7. Conclusion and Expected Outcomes
Sudan's e-government infrastructure has experienced growing exposure to network-based attacks in recent years. Due to international sanctions, government agencies cannot procure commercial network security monitoring products, leaving critical services exposed to anomalous traffic, denial-of-service attacks, and data exfiltration attempts. This research proposes to address this gap by developing a machine learning-based network anomaly detection system that can be deployed without reliance on commercial security vendors.
Outcomes:

Implement a machine learning-based anomaly detection framework adapted to Sudan's e-government network environment.
Improve detection rates for both known and novel network attack categories while minimizing false positive alerts.
Develop a lightweight open-source prototype system that government network administrators can deploy and maintain without access to commercial security tools.


## 8. References
[1] Chandola, V., Banerjee, A., and Kumar, V. Anomaly Detection: A Survey. ACM Computing Surveys, 41(3):1–58, July 2009.
[2] Lakhina, A., Crovella, M., and Diot, C. Diagnosing Network-Wide Traffic Anomalies. In Proceedings of ACM SIGCOMM, 2004.
[3] Tavallaee, M., Bagheri, E., Lu, W., and Ghorbani, A. A Detailed Analysis of the KDD CUP 99 Data Set. In Proceedings of the IEEE Symposium on Computational Intelligence for Security and Defense Applications, 2009.
[4] Javaid, A., Niyaz, Q., Sun, W., and Alam, M. A Deep Learning Approach for Network Intrusion Detection System. In Proceedings of the 9th EAI International Conference on Bio-inspired Information and Communications Technologies, 2016.
[5] Hall, M. A. Correlation-based Feature Selection for Machine Learning. PhD Thesis, University of Waikato, 1999.
[6] Wikipedia. Stuxnet. https://en.wikipedia.org/wiki/Stuxnet, July 2015.
[7] Kaspersky. What is network scanning attack. http://www.kaspersky.com/networkscan