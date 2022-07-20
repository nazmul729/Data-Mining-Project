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
<p align="right">
| | Normal | Probe | DoS | U2R | R2L |
|:----:|:----:|:----:|:----:|:----:|:----:|
| Normal | 0 | 2 | 2 | 2 | 2 |
| DoS | 2 | 0 | 2 | 2 | 2 |
| U2R | 2 | 2 | 0 | 2 | 2 |
| R2L | 2 | 2 | 2 | 0 | 2 |
| Probe | 2 | 0 | 2 | 2 | 0 |
</p>
