## Introduction

Electronic Health Records (EHR) data have become a critical resource for advancing machine learning in healthcare. EHRs contain rich, longitudinal information about patients, including demographics, diagnoses, medications, lab results, imaging reports, and clinical notes. This wealth of structured and unstructured data enables the development of predictive models for disease risk, treatment outcomes, and personalized care. However, EHR data also present challenges such as high dimensionality, missing values, coding variability, and privacy concerns, requiring specialized methods for preprocessing, modeling, and interpretation.

## Table of Contents

<table>
  <tr><td colspan="2"><a href="#1-methods-and-models" style="color:#B22222">1. Methods and Models</a></td></tr>
  <tr>
    <td>&ensp;<a href="#11-foundation-model">1.1 Foundation Model</a></td>
    <td>&ensp;<a href="#12-multimodal-model">1.2 Multimodal Model</a></td>
  </tr>
  <tr>
    <td>&ensp;<a href="#13-dataset-and-evaluation">1.3 Dataset and Evaluation</a></td>
    <td>&ensp;<a href="#14-structure-aware-models">1.4 Structure-aware Models</a></td>
  </tr>
  <tr>
    <td>&ensp;<a href="#15-sequential-modeling">1.5 Sequential Modeling</a></td>
    <td>&ensp;<a href="#16-graph-based-models">1.6 Graph Based Models</a></td>
  </tr>
  <tr>
    <td>&ensp;<a href="#17-knowledge-graph">1.7 Knowledge Graph</a></td>
    <td>&ensp;<a href="#18-interpretable-models">1.8 Interpretable Models</a></td>
  </tr>
  <tr>
    <td>&ensp;<a href="#19-rnn-based-models">1.9 RNN Based Models</a></td>
    <!-- <td>&ensp;<a href="#18-interpretable-models">1.8 Interpretable Models</a></td> -->
  </tr>
</table>


## [1. Methods and Models](#content)
### [1.1 Foundation Model](#content)
1. [Multimodal Medical Code Tokenizer](https://arxiv.org/abs/2502.04397), ICML 2025, \
   Xiaorui Su, Shvat Messica, Yepeng Huang, Ruth Johnson, Lukas Fesser, Shanghua Gao, Faryad Sahneh, Marinka Zitnik
1. [Zero shot health trajectory prediction using transformer](https://www.nature.com/articles/s41746-024-01235-0), NPJ Digit Med 2024, \
   Pawel Renc, Yugang Jia, Anthony E. Samir, Jaroslaw Was, Quanzheng Li, David W. Bates, Arkadiusz Sitek
1. [EHR foundation models improve robustness in the presence of temporal distribution shift](https://www.nature.com/articles/s41598-023-30820-8?error=cookies_not_supported&code=9f53fd13-a174-4176-a1d6-bb271f818ba6#Sec2), Scientific Reports 2023, \
   Lin Lawrence Guo, Ethan Steinberg, Scott Lanyon Fleming, Jose Posada, Joshua Lemmon, Stephen R. Pfohl, Nigam Shah, Jason Fries, Lillian Sung
1. [Hi-BEHRT: Hierarchical Transformer-based model for accurate prediction of clinical events using multimodal longitudinal electronic health records](https://arxiv.org/abs/2106.11360), IEEE J Biomed Health Inform 2023, \
   Yikuan Li, Mohammad Mamouei, Gholamreza Salimi-Khorshidi, Shishir Rao, Abdelaali Hassaine, Dexter Canoy, Thomas Lukasiewicz, Kazem Rahimi
1. [TransformEHR: transformer-based encoder-decoder generative model to enhance prediction of disease outcomes using electronic health records](https://www.nature.com/articles/s41467-023-43715-z), Nature communications 2023, \
   Zhichao Yang, Avijit Mitra, Weisong Liu, Dan Berlowitz & Hong Yu
1. [Med-BERT: pre-trained contextualized embeddings on large-scale structured electronic health records for disease prediction](https://arxiv.org/abs/2005.12833), npj digital medicine 2021, \
   Laila Rasmy, Yang Xiang, Ziqian Xie, Cui Tao, and Degui Zhi
1. [Biobert: a pre-trained biomedical language representation model for biomedical text mining](https://arxiv.org/abs/1901.08746), Bioinformatics 2020, \
   Jinhyuk Lee, Wonjin Yoon, Sungdong Kim, Donghyeon Kim, Sunkyu Kim, Chan Ho So, Jaewoo Kang
1. [BEHRT: Transformer for Electronic Health Records](https://www.nature.com/articles/s41598-020-62922-y), Scientific Reports 2020, \
   Yikuan Li, Shishir Rao, José Roberto Ayala Solares, Abdelaali Hassaine, Rema Ramakrishnan, Dexter Canoy, Yajie Zhu, Kazem Rahimi, Gholamreza Salimi-Khorshidi
1. [Clinicalbert: Modeling clinical notes and predicting hospital readmission](https://arxiv.org/abs/1904.05342), CHIL 2020 Workshop, \
   Kexin Huang, Jaan Altosaar, Rajesh Ranganath



### [1.2 Multimodal Model](#content)
1. [Addressing Asynchronicity in Clinical Multimodal Fusion via Individualized Chest X-ray Generation](https://arxiv.org/abs/2410.17918), NeurIPS 2024, \
   Wenfang Yao, Chen Liu, Kejing Yin, William K. Cheung, Jing Qin

### [1.3 Dataset and Evaluation](#content)
1. [EHRCon: Dataset for Checking Consistency between Unstructured Notes and Structured Tables in Electronic Health Records](https://arxiv.org/abs/2406.16341), NeurIPS track on Datasets 2024, \
   Yeonsu Kwon, Jiho Kim, Gyubok Lee, Seongsu Bae, Daeun Kyung, Wonchul Cha, Tom Pollard, Alistair Johnson, Edward Choi

### [1.4 Structure-aware Models](#content)
1. [ProtoEHR: Hierarchical Prototype Learning for EHR-based Healthcare Predictions](https://arxiv.org/abs/2508.18313), CIKM 2025, \
   Zi Cai, Yu Liu, Zhiyao Luo, Tingting Zhu
1. [Multi-Ontology Integration with Dual-Axis Propagation for Medical Concept Representation](https://arxiv.org/abs/2508.21320), CIKM 2025, \
   Mohsen Nayebi Kerdabadi, Arya Hadizadeh Moghaddam, Dongjie Wang, Zijun Yao
1. [BoxLM: Unifying Structures and Semantics of Medical Concepts for Diagnosis Prediction in Healthcare](https://www.cs.emory.edu/~jyang71/files/boxlm.pdf), ICML 2025, \
   Yanchao Tan, Hang Lv, Yunfei Zhan, Guofang Ma, Bo Xiong, Carl Yang
1. [BoxCare: A Box Embedding Model for Disease Representation and Diagnosis Prediction in Healthcare Data](https://dl.acm.org/doi/10.1145/3589335.3651448), WWW 2024, \
   Hang Lv, Zehai Chen, Yacong Yang, Guofang Ma, Tan Yanchao, Carl Yang
1. [Self-Supervised Graph Learning with Hyperbolic Embedding for Temporal Health Event Prediction](https://arxiv.org/abs/2106.04751), IEEE Trans. Cybern. 2023, \
   Chang Lu, Chandan K. Reddy, Yue Ning
1. [Exploiting hierarchy in medical concept embedding](https://pubmed.ncbi.nlm.nih.gov/33748691/#:~:text=Results%3A%20%20We%20found%20that,training%20embeddings%20improved%20classification), JAMIA Open 2021, \
   Anthony Finch, Alexander Crowell, Mamta Bhatia, Pooja Parameshwarappa, Yung-Chieh Chang, Jose Martinez, Michael Horberg
1. [HiTANet: Hierarchical Time-Aware Attention Networks for Risk Prediction on Electronic Health Records](https://dl.acm.org/doi/10.1145/3394486.3403107), KDD 2020, \
   Junyu Luo, Muchao Ye, Cao Xiao, Fenglong Ma
1. [Learning Electronic Health Records through Hyperbolic Embedding of Medical Ontologies](https://dl.acm.org/doi/10.1145/3307339.3342148), ACM BNB 2019, \
   Qiuhao Lu, Nisansa de Silva, Sabin Kafle, Jiazhen Cao, Dejing Dou, Thien Huu Nguyen, Prithviraj Sen, Brent Hailpern, Berthold Reinwald, and Yunyao Li
1. [GRAM: Graph-based Attention Model for Healthcare Representation Learning](https://arxiv.org/abs/1611.07012), KDD 2017, \
   Edward Choi, Mohammad Taha Bahadori, Le Song, Walter F. Stewart, Jimeng Sun

   
### [1.5 Sequential Modeling](#content)
1. [Predictive modeling with temporal graphical representation on electronic  health records](https://arxiv.org/abs/2405.03943), IJCAI 2024, \
   Jiayuan Chen, Changchang Yin, Yuanlong Wang, Ping Zhang
1. [Vecocare: Visit sequencesclinical notes joint learning for diagnosis prediction in healthcare data](https://www.ijcai.org/proceedings/2023/547), IJCAI 2023, \
   Yongxin Xu, Kai Yang, Chaohe Zhang, Peinie Zou, Zhiyuan Wang, Hongxin Ding, Junfeng Zhao, Yasha Wang, Bing Xie

### [1.6 Graph Based Models](#content)
1. [Predictive modeling with temporal graphical representation on electronic  health records](https://arxiv.org/abs/2405.03943), IJCAI 2024, \
   Jiayuan Chen, Changchang Yin, Yuanlong Wang, Ping Zhang
1. [Graph Transformers on EHRs: Better Representation Improves Downstream Performance](https://openreview.net/pdf?id=pe0Vdv7rsL), ICLR 2024, \
   Raphael Poulain, Rahmatollah Beheshti
1. [Collaborative graph learning with auxiliary text for temporal event prediction in healthcare](https://arxiv.org/abs/2105.07542), IJCAI 2021, \
   Chang Lu, Chandan K. Reddy, Prithwish Chakraborty, Samantha Kleinberg, Yue Ning

### [1.7 Knowledge Graph](#content)
1. [Stage-aware hierarchical attentive relational network for diagnosis prediction](https://ieeexplore.ieee.org/document/10236511), TKDE 2023, \
   Liping Wang, Qiang Liu, Mengqi Zhang, Yaxuan Hu, Shu Wu, Liang Wang
1. [Kame: Knowledge-based attention model for diagnosis prediction in healthcare](https://dl.acm.org/doi/10.1145/3269206.3271701), CIKM 2018, \
   Fenglong Ma, Quanzeng You, Houping Xiao, Radha Chitta, Jing Zhou, Jing Gao

### [1.8 Interpretable Models](#content)
1. [Inprem: An interpretable and trustworthy predictive model for healthcare](https://dl.acm.org/doi/abs/10.1145/3394486.3403087), KDD 2020, \
   Xianli Zhang, Buyue Qian, Shilei Cao, Yang Li, Hang Chen, Yefeng Zheng, Ian Davidson

### [1.9 RNN Based Models](#content)
1. [Doctor ai: Predicting clinical events via recurrent neural networks](https://arxiv.org/abs/1511.05942), MLHC 2016, \
   Edward Choi, Mohammad Taha Bahadori, Andy Schuetz, Walter F. Stewart, Jimeng Sun
