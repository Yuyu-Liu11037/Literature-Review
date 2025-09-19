## Introduction

Electronic Health Records (EHR) data have become a critical resource for advancing machine learning in healthcare. EHRs contain rich, longitudinal information about patients, including demographics, diagnoses, medications, lab results, imaging reports, and clinical notes. This wealth of structured and unstructured data enables the development of predictive models for disease risk, treatment outcomes, and personalized care. However, EHR data also present challenges such as high dimensionality, missing values, coding variability, and privacy concerns, requiring specialized methods for preprocessing, modeling, and interpretation.

<table>
  <tr><td colspan="2"><a href="#1-methods-and-models" style="color:#B22222">1. Methods and Models</a></td></tr>
  <tr>
    <td>&ensp;<a href="#11-foundation-model">1.1 Foundation Model</a></td>
    <td>&ensp;<a href="#12-multimodal-model">1.2 Multimodal Model</a></td>
  </tr>
  <tr>
    <td>&ensp;<a href="#13-dataset-and-evaluation">1.3 Dataset and Evaluation</a></td>
  </tr>
</table>


## [1. Methods and Models](#content)
### [1.1 Foundation Model](#content)
1. [Multimodal Medical Code Tokenizer](https://arxiv.org/abs/2502.04397), ICML 2025, \
   Xiaorui Su, Shvat Messica, Yepeng Huang, Ruth Johnson, Lukas Fesser, Shanghua Gao, Faryad Sahneh, Marinka Zitnik
1. [BoxLM: Unifying Structures and Semantics of Medical Concepts for Diagnosis Prediction in Healthcare](https://www.cs.emory.edu/~jyang71/files/boxlm.pdf), ICML 2025, \
   Yanchao Tan, Hang Lv, Yunfei Zhan, Guofang Ma, Bo Xiong, Carl Yang
1. [Zero shot health trajectory prediction using transformer](https://www.nature.com/articles/s41746-024-01235-0), NPJ Digit Med 2024, \
   Pawel Renc, Yugang Jia, Anthony E. Samir, Jaroslaw Was, Quanzheng Li, David W. Bates & Arkadiusz Sitek
1. [Learning Electronic Health Records through Hyperbolic Embedding of Medical Ontologies](https://dl.acm.org/doi/10.1145/3307339.3342148), ACM BNB 2019, \
   Qiuhao Lu, Nisansa de Silva, Sabin Kafle, Jiazhen Cao, Dejing Dou, Thien Huu Nguyen, Prithviraj Sen, Brent Hailpern, Berthold Reinwald, and Yunyao Li



### [1.2 Multimodal Model](#content)
1. [Addressing Asynchronicity in Clinical Multimodal Fusion via Individualized Chest X-ray Generation](https://arxiv.org/abs/2410.17918), NeurIPS 2024, \
   Wenfang Yao, Chen Liu, Kejing Yin, William K. Cheung, Jing Qin

### [1.3 Dataset and Evaluation](#content)
1. [EHRCon: Dataset for Checking Consistency between Unstructured Notes and Structured Tables in Electronic Health Records](https://arxiv.org/abs/2406.16341), NeurIPS track on Datasets 2024, \
   Yeonsu Kwon, Jiho Kim, Gyubok Lee, Seongsu Bae, Daeun Kyung, Wonchul Cha, Tom Pollard, Alistair Johnson, Edward Choi
