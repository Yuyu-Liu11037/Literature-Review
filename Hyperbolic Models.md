## Introduction

Recently, hyperbolic spaces have emerged as a promising alternative for processing data with a tree-like structure or power-law distribution, owing to its exponential growth property and tree-likeness prior. Different from the Euclidean space, which expands polynomially, the hyperbolic space grows exponentially which makes it gain natural advantages in abstracting tree-like or scale-free data with hierarchical organizations. In this repository, we categorize papers related to hyperbolic representation learning into different types to facilitate researcher studies and to promote the development of the community.

## Table of Contents
<table>
<tr><td colspan="2"><a href="#1-surveys-books-tools-tutorials" style="color:#B22222">1. Surveys, Books, Tools, Tutorials</a></td></tr>
<tr>
    <td>&ensp;<a href="#11-surveys">1.1 Surveys</a></td>
    <td>&ensp;<a href="#12-books">1.2 Books</a></td>
</tr>
  <tr>
    <td>&ensp;<a href="#13-tools">1.3 Tools</a></td>
    <td>&ensp;<a href="#14-tutorials">1.4 Tutorials</a></td>
</tr>
  
<tr><td colspan="2"><a href="#2-methods-and-models" style="color:#B22222">2. Methods and Models</a></td></tr>
<tr>
    <td>&ensp;<a href="#21-hyperbolic-shallow-model">2.1 Hyperbolic Shallow Model</a></td>
    <td>&ensp;<a href="#22-hyperbolic-neural-network">2.2 Hyperbolic Neural Network</a></td>
</tr> 
  <tr>
    <td>&ensp;<a href="#23-hyperbolic-graph-neural-network">2.3 Hyperbolic Graph Neural Network</a></td>
    <td>&ensp;<a href="#24-hyperbolic-transformer">2.4 Hyperbolic Transformer</a></td>
</tr>
<tr>
    <td>&ensp;<a href="#25-theoretical-foundations">2.5 Theoretical Foundations</a></td>
    <td>&ensp;<a href="#26-analysis">2.6 Analysis</a></td>
</tr>
<tr>
    <td>&ensp;<a href="#27-numerical-problems">2.7 Numerical Problems</a></td>
    <td>&ensp;<a href="#28-explicitly-tree-embedding">2.8 Explicitly Tree Embedding</a></td>
</tr>
<tr>
    <td>&ensp;<a href="#29-mixed-curvature-learning">2.9 Mixed Curvature Learning</a></td>
    <td>&ensp;<a href="#210-semi-riemannian-learning">2.10 Semi-Riemannian Learning</a></td>
</tr>
<tr>
    <td>&ensp;<a href="#211-hyperbolic-generative-models">2.11 Hyperbolic Generative Models</a></td>
    <td>&ensp;<a href="#212-hyperbolic-classifiers">2.12 Hyperbolic Classifiers</a></td>
</tr>
<tr>
    <td>&ensp;<a href="#213-hyperbolic-operations">2.13 Hyperbolic Operations</a></td>
    <td>&ensp;<a href="#214-llm-and-hyperbolic-space">2.14 LLM && Hyperbolic Space</a></td>
</tr>

<tr><td colspan="2"><a href="#3-applications" style="color:#B22222">3. Applications</a></td></tr>
<tr>
    <td>&ensp;<a href="#31-natural-language-processing">3.1 Natural Language Processing</a></td>
    <td>&ensp;<a href="#32-computer-vision">3.2 Computer Vision</a></td>
</tr>
<tr>
    <td>&ensp;<a href="#33-graph-embeddings">3.3 Graph Embeddings</a></td>
    <td>&ensp;<a href="#34-recommender-systems">3.4 Recommender Systems</a></td>
</tr>
<tr>
    <td>&ensp;<a href="#35-knowledge-graphs">3.5 Knowledge Graphs</a></td>
    <td>&ensp;<a href="#36-molecular-learning">3.6 Molecular Learning</a></td>
</tr>
<tr>
    <td>&ensp;<a href="#37-code-representation">3.7 Code Representation</a></td>
    <td>&ensp;<a href="#38-multi-label-learning">3.8 Multi-label Learning</a></td>
</tr>
<tr>
    <td>&ensp;<a href="#39-hyperbolic-metric-learning">3.9 Hyperbolic Metric Learning</a></td>
    <td>&ensp;<a href="#310-data-driven-geometry-learning">3.10 Data-driven Geometry Learning</a></td>
</tr>
<tr>
    <td>&ensp;<a href="#311-few-shot-learning">3.11 Few-Shot Learning</a></td>
    <td>&ensp;<a href="#312-open-vocabulary-learning">3.12 Open-Vocabulary Learning</a></td>
</tr>
<tr>
    <td>&ensp;<a href="#313-safety-and-robustness">3.13 Safety and Robustness</a></td>
    <td>&ensp;<a href="#314-environmental-monitoring">3.14 Environmental Monitoring</a></td>
</tr>
<tr>
    <td>&ensp;<a href="#315-category-discovery">3.15 Category Discovery</a></td>
    <td>&ensp;<a href="#316-multi-criteria-learning">3.16 Multi-Criteria Learning</a></td>
</tr>
<tr>
    <td>&ensp;<a href="#317-biology">3.17 Biology</a></td>
    <td></td>
</tr>
</table>

## [1. Surveys, Books, Tools, Tutorials](#content)
### [1.1 Surveys](#content)
1. [Hyperbolic Deep Learning for Foundation Models: A Survey](https://arxiv.org/abs/2507.17787), KDD 2025 \
  *Neil He, Hiren Madhu, Ngoc Bui, Menglin Yang, Rex Ying*


### [1.4 Tutorials](#content)
1. [Hyperbolic Deep Learning for Foundation Models](https://hyperboliclearning.github.io/events/materials/kdd25.pdf) \
   Neil He, Menglin Yang, Rex Ying, Hiren Madhu, Ngoc Bui


## [2. Methods and Models](#content)
### [2.1 Hyperbolic Shallow Model](#content)

1. [Poincaré Embeddings for Learning Hierarchical Representations](https://arxiv.org/abs/1705.08039), NeurIPS 2017 \
Maximilian Nickel, Douwe Kiela

1. [Learning Continuous Hierarchies in the Lorentz Model of Hyperbolic Geometry](https://arxiv.org/abs/1806.03417), ICML 2018 \
Maximilian Nickel, Douwe Kiela

### [2.2 Hyperbolic Neural Network](#content)
1. [Hyperbolic Neural Networks](https://arxiv.org/abs/1805.09112), NeurIPS 2018 \
Octavian-Eugen Ganea, Gary Bécigneul, Thomas Hofmann


### [2.3 Hyperbolic Graph Neural Network](#content)
1. [Hyperbolic Graph Convolutional Neural Networks](https://arxiv.org/abs/1910.12933), NeurIPS 2019 \
Ines Chami\*, Rex Ying\*, Christopher Ré, Jure Leskovec



### [2.4 Hyperbolic Transformer](#content)
1. [Hypformer: Exploring Efficient Transformer Fully in Hyperbolic Space](https://arxiv.org/abs/2407.01290), KDD 2024 \
   Menglin Yang, Harshit Verma, Delvin Ce Zhang, Jiahong Liu, Irwin King, Rex Ying

1. [Fully Hyperbolic Neural Networks](https://arxiv.org/abs/2105.14686), ACL 2022 \
Weize Chen, Xu Han, Yankai Lin, Hexu Zhao, Zhiyuan Liu, Peng Li, Maosong Sun, Jie Zhou


### [2.5 Theoretical Foundations](#content)
### [2.6 Analysis](#content)
### [2.7 Numerical Problems](#content)
### [2.8 Explicitly Tree Embedding](#content)
### [2.9 Mixed Curvature Learning](#content)
1. [HELM: Hyperbolic Large Language Models via Mixture-of-Curvature Experts](https://arxiv.org/abs/2505.24722), 2025 \
   Neil He, Rishabh Anand, Hiren Madhu, Ali Maatouk, Smita Krishnaswamy, Leandros Tassiulas, Menglin Yang, Rex Ying

### [2.10 Semi-Riemannian Learning](#content)
### [2.11 Hyperbolic Generative Models](#content)
### [2.12 Hyperbolic Classifiers](#content)
### [2.13 Hyperbolic Operations](#content)
### [2.14 LLM and Hyperbolic Space](#content)
1. [HELM: Hyperbolic Large Language Models via Mixture-of-Curvature Experts](https://arxiv.org/abs/2505.24722), 2025 \
   Neil He, Rishabh Anand, Hiren Madhu, Ali Maatouk, Smita Krishnaswamy, Leandros Tassiulas, Menglin Yang, Rex Ying


   

## [3. Applications](#content)
### [3.1 Natural Language Processing](#content)
### [3.2 Computer Vision](#content)
### [3.3 Graph Embeddings](#content)
### [3.4 Recommender Systems](#content)
### [3.5 Knowledge Graphs](#content)
### [3.6 Molecular Learning](#content)
### [3.7 Code Representation](#content)
### [3.8 Multi-label Learning](#content)
### [3.9 Hyperbolic Metric Learning](#content)
### [3.10 Data-driven Geometry Learning](#content)
### [3.11 Few-Shot Learning](#content)
### [3.12 Open-Vocabulary Learning](#content)
### [3.13 Safety and Robustness](#content)
### [3.14 Environmental Monitoring](#content)
### [3.15 Category Discovery](#content)
### [3.16 Multi-Criteria Learning](#content)
### [3.17 Biology](#content)
**Genomics**


**EHR**
1. [Learning Electronic Health Records through Hyperbolic Embedding of Medical Ontologies](https://dl.acm.org/doi/10.1145/3307339.3342148), ACM BCB 2019, \
   Lu, Qiuhao and de Silva, Nisansa and Kafle, Sabin and Cao, Jiazhen and Dou, Dejing and Nguyen, Thien Huu and Sen, Prithviraj and Hailpern, Brent and Reinwald, Berthold and Li, Yunyao




