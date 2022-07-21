# Class Imbalance Effect on Intrusion Detection System
With the growth of internet information, network security is becoming an immense challenge nowadays. To handle this challenge, Intrusion Detection System (IDS) is the most important system which suffers from various types of false alarms and intruders. Machine learning and data mining algorithms have been developed to detect these intruders. This work focuses on the performance of the system to detect intruders efficiently. Several algorithms and techniques are used, but couldn’t perform state-of-the-art results due to the limitations in the dataset which is class imbalance. To get best performance, this imbalance problem has to overcome. We applied oversampling and under-sampling method and finally got acceptable result.

## Dataset Information and Cost Function
The Dataset is collected from MIT Lincoln Laboratory which is supervised by the sponsorships of [Defense Advanced Research Projects Agency (DARPA)](https://link.springer.com/chapter/10.1007/978-3-540-45248-5_13) and [Air force Research Laboratory (AFRL)](https://www.afrl.af.mil/). DARPA dataset is the most popular and [the KDD’99 Cup dataset](https://www.researchgate.net/publication/327812725_KDD_1999_generation_faults_a_review_and_analysis) is the subset of DARPA dataset due to the size of the dataset, which is prepared by Sal Stolfo et al.
| Type | Attacks |
|:------:|:----------|
| Probe | Ipsweep , nmap, portsweep, satan, Mscan, Saint |
| Dos | Back, land, Neptune, pod, smurf, teardrop, Apache2, Mailbomb, Processtable, Upstorm |
| U2R | buffer_overflow, loadmodule, perl, rootkit, Httptunnel, Ps, Woor, Xterm |
| R2L | ftp_write, guess_passwd, imap, multihop, phf, spy, warezclient, warezmaster Named, Sendmail, Snmpgetattack, Snmpgue, Sqlattack, Xlock, Xsnoop |

A cost matrix is used to measure the misclassification of a model. It can cause the model to maximize beneficial accurate classifications. The cost matrix for five class of [KDD’99 Cup dataset](https://www.researchgate.net/publication/327812725_KDD_1999_generation_faults_a_review_and_analysis) is-

| | Normal | Probe | DoS | U2R | R2L |
|:----:|:----:|:----:|:----:|:----:|:----:|
| Normal | 0 | 2 | 2 | 2 | 2 |
| DoS | 2 | 0 | 2 | 2 | 2 |
| U2R | 2 | 2 | 0 | 2 | 2 |
| R2L | 2 | 2 | 2 | 0 | 2 |
| Probe | 2 | 0 | 2 | 2 | 0 |

Full 10% KDD’99 Dataset contains 494021 samples with 22 attack types. The occurrences of each attack in dataset are shown in the following figure-

![attack freq](https://user-images.githubusercontent.com/42664968/180103272-c3469016-cbd7-4ce5-8f78-a899d8299e67.jpg)

![Distribution of each attacks](https://user-images.githubusercontent.com/42664968/180103414-358ec22e-7a8f-4fda-8a1d-5e8d6011eaa0.jpg)


## Empirical Results

To show the effect of this class imbalance problem, we evaluated the performance for original dataset by using DT classifier. Then remove some irrelevant, noisy, skewed, and/or redundant features from the original dataset and make a new dataset with reduced feature named “reduced dataset”. Then, we applied DT algorithm for empirically analysis on reduced dataset [37]. Finally, calculated the validation performance by removing class imbalance problem through under-sampling and oversampling. These performances are depicted in figure-

![Performance Comparison](https://github.com/nazmul729/Data-Mining-Project/blob/12f0e218f85c9b71424af47653264a72035ff430/Performance%20Comparison.jpg)

The misclassification costs are-

![misclassification_Cost](https://github.com/nazmul729/Data-Mining-Project/blob/main/Misclassification%20Cost.jpg)

In this project, I have empirically analyzed the imbalance effect using Decision Table rules based algorithm on IDS. The new preprocessed dataset built-
- by selecting a limited number of features and 
- by removing class imbalance problem through oversampling and under-sampling. 
Then DT algorithm is applied on the network intrusion dataset with labeled samples. This DT classifier is also applied on reduced dataset and original dataset.The DT classifier performs state-of-the-art performance with lower misclassification costs on proposed unbiased datasets.
