## Introduction

Hallucination mitigation in Large Vision-Language Models (LVLMs) focuses on reducing instances where the model generates outputs that are factually incorrect, logically inconsistent, or not grounded in the given input. These hallucinations often arise from overgeneralization, spurious correlations, or limitations in aligning visual and textual representations. Effective mitigation strategies combine improved model architectures, training with high-quality multimodal datasets, alignment techniques such as reinforcement learning with human feedback, and post-hoc methods like retrieval augmentation or uncertainty estimation. Together, these approaches aim to enhance the reliability, trustworthiness, and safety of LVLMs in real-world applications.

## Table of Contents

<table>
<tr><td colspan="2"><a href="#1-methods-and-models" style="color:#B22222">1. Methods and Models</a></td></tr>
<tr>
  <td>&ensp;<a href="#11-lvlm-inference">1.1 LVLM Inference</a></td>
  <td>&ensp;<a href="#12-datasets-and-benchmarks">1.2 Datasets and Benchmarks</a></td>
</tr>
<tr>
  <td>&ensp;<a href="#13-model-architechture">1.3 Model Architecture</a></td>
  <td>&ensp;<a href="#14-hallucination-detection">1.4 Hallucination Detection</a></td>
</tr>
<tr>
  <td>&ensp;<a href="#15-fine-tuning">1.5 Fine Tuning</a></td>
  <td>&ensp;<a href="#16-training">1.6 Training</a></td>
</tr>
<tr>
  <td>&ensp;<a href="#17-internal-embeddings">1.7 Internal Embeddings</a></td>
  <!-- <td>&ensp;<a href="#16-training">1.6 Training</a></td> -->
</tr>

<tr><td colspan="2"><a href="#2-applications" style="color:#B22222">2. Applications</a></td></tr>
<tr>
  <td>&ensp;<a href="#21-revolutionary-generation-models">2.1 Revolutionay Generative Models</a></td>
  <td>&ensp;<a href="#22-revolutionary-generation-models">2.2 Promptable Segmentation</a></td>
</tr>
</table>


## [1. Methods and Models](#content)
### [1.1 LVLM Inference](#content)
1. [The Hidden Life of Tokens: Reducing Hallucination of Large Vision-Language Models Via Visual Information Steering](https://arxiv.org/abs/2502.03628), ICML 2025, \
Zhuowei Li, Haizhou Shi, Yunhe Gao, Di Liu, Zhenting Wang, Yuxiao Chen, Ting Liu, Long Zhao, Hao Wang, Dimitris N. Metaxas
1. [SECOND: Mitigating Perceptual Hallucination in Vision-Language Models via Selective and Contrastive Decoding](https://arxiv.org/abs/2506.08391), ICML 2025, \
Woohyeon Park, Woojin Kim, Jaeik Kim, Jaeyoung Do
1. [Mitigating Object Hallucination in Large Vision-Language Models via Image-Grounded Guidance](https://arxiv.org/abs/2402.08680), ICML 2025, \
Linxi Zhao, Yihe Deng, Weitong Zhang, Quanquan Gu
1. [Look Twice Before You Answer: Memory-Space Visual Retracing for Hallucination Mitigation in Multimodal Large Language Models](https://arxiv.org/abs/2410.03577), ICML 2025, \
Xin Zou, Yizhou Wang, Yibo Yan, Yuanhuiyi Lyu, Kening Zheng, Sirui Huang, Junkai Chen, Peijie Jiang, Jia Liu, Chang Tang, Xuming Hu
1. [DAMO: Decoding by Accumulating Activations Momentum for Mitigating Hallucinations in Vision-Language Models](https://iclr.cc/virtual/2025/poster/30108), ICLR 2025, \
Kaishen Wang, Hengrui Gu, Meijun Gao, Kaixiong Zhou
1. [Self-Introspective Decoding: Alleviating Hallucinations for Large Vision-Language Models](https://iclr.cc/virtual/2025/poster/28166), ICLR 2025, \
Fushuo Huo, Wenchao Xu, Zhong Zhang, Haozhao Wang, Zhicheng Chen, Peilin Zhao
1. [Do You Keep an Eye on What I Ask? Mitigating Multimodal Hallucination via Attention-Guided Ensemble Decoding](https://iclr.cc/virtual/2025/poster/27655), ICLR 2025, \
Yeongjae Cho, Keonwoo Kim, Taebaek Hwang, Sungzoon Cho
1. [Reducing Hallucinations in Large Vision-Language Models via Latent Space Steering](https://iclr.cc/virtual/2025/poster/30013), ICLR 2025, \
Sheng Liu, Haotian Ye, James Y Zou
1. [MLLM can see? Dynamic Correction Decoding for Hallucination Mitigation](https://iclr.cc/virtual/2025/poster/30978), ICLR 2025, \
Chenxi Wang, Xiang Chen, Ningyu Zhang, Bozhong Tian, Haoming Xu, Shumin Deng, Huajun Chen
1. [Mitigating Modality Prior-Induced Hallucinations in Multimodal Large Language Models via Deciphering Attention Causality](https://iclr.cc/virtual/2025/poster/30629), ICLR 2025, \
Guanyu Zhou, Yibo Yan, Xin Zou, Kun Wang, Aiwei Liu, Xuming Hu
1. [Intervening Anchor Token: Decoding Strategy in Alleviating Hallucinations for MLLMs](https://iclr.cc/virtual/2025/poster/27678), ICLR 2025, \
Barrett Tang, Zile Huang, Chengzhi Liu, Qiang Sun, Harry Yang, Ser-Nam Lim
1. [Understanding and Mitigating Hallucination in Large Vision-Language Models via Modular Attribution and Intervention](https://iclr.cc/virtual/2025/poster/30556), ICLR 2025, \
Tianyun Yang, Ziniu Li, Juan Cao, Chang Xu
1. [Self-Correcting Decoding with Generative Feedback for Mitigating Hallucinations in Large Vision-Language Models](https://iclr.cc/virtual/2025/poster/28052), ICLR 2025, \
Ce Zhang, Zifu Wan, Zhehan Kan, Martin Q. Ma, Simon Stepputtis, Deva Ramanan, Russ Salakhutdinov, Louis-Philippe Morency, Katia Sycara, Yaqi Xie
1. [Visual Description Grounding Reduces Hallucinations and Boosts Reasoning in LVLMs](https://iclr.cc/virtual/2025/poster/31078), ICLR 2025, \
Sreyan Ghosh, Chandra Kiran Evuru, Sonal Kumar, Utkarsh Tyagi, Oriol Nieto, Zeyu Jin, Dinesh Manocha
1. [HALC: Object Hallucination Reduction via Adaptive Focal-Contrast Decoding](https://arxiv.org/abs/2403.00425), ICML 2024, \
Zhaorun Chen, Zhuokai Zhao, Hongyin Luo, Huaxiu Yao, Bo Li, Jiawei Zhou
1. [CODE: Contrasting Self-generated Description to Combat Hallucination in Large Multi-modal Models](https://arxiv.org/abs/2406.01920), NeurIPS 2024, \
Junho Kim, Hyunjun Kim, Yeonju Kim, Yong Man Ro


### [1.2 Datasets and Benchmarks](#content)
1. [Evaluating and Analyzing Relationship Hallucinations in Large Vision-Language Models](https://arxiv.org/abs/2406.16449), ICML 2024, \
Mingrui Wu, Jiayi Ji, Oucheng Huang, Jiale Li, Yuhang Wu, Xiaoshuai Sun, Rongrong Ji
1. [Toward a Stable, Fair, and Comprehensive Evaluation of Object Hallucination in Large Vision-Language Models](https://nips.cc/virtual/2024/poster/93023), NeurIPS 2024, \
Hongliang Wei, Xingtao Wang, Xianqi Zhang, Xiaopeng Fan, Debin Zhao
1. [Multi-Object Hallucination in Vision Language Models](https://nips.cc/virtual/2024/poster/95666), NeurIPS 2024, \
Xuweiyi Chen, Ziqiao Ma, Xuejun Zhang, Sihan Xu, Shengyi Qian, Jianing Yang, David Fouhey, Joyce Chai

### [1.3 Model Architecture](#content)
1. [Mitigating Object Hallucination via Concentric Causal Attention](https://arxiv.org/abs/2410.15926), NeurIPS 2024, \
Yun Xing, Yiheng Li, Ivan Laptev, Shijian Lu

### [1.4 Hallucination Detection](#content)
1. [Hallo3D: Multi-Modal Hallucination Detection and Mitigation for Consistent 3D Content Generation](https://proceedings.neurips.cc/paper_files/paper/2024/hash/d75660d6eb0ce31360c768fef85301dd-Abstract-Conference.html), NeurIPS 2024, \
Hongbo Wang, Jie Cao, Jin Liu, Xiaoqiang Zhou, Huaibo Huang, Ran He
1. [Estimating the Hallucination Rate of Generative AI](https://nips.cc/virtual/2024/poster/95553), NeurIPS 2024, \
Andrew Jesson, Nicolas Beltran Velez, Quentin Chu, Sweta Karlekar, Jannik Kossen, Yarin Gal, John Cunningham, David Blei


### [1.5 Fine Tuning](#content)
1. [Mitigating Object Hallucination in MLLMs via Data-augmented Phrase-level Alignment](https://iclr.cc/virtual/2025/poster/27739), ICLR 2025, \
Pritam Sarkar, Sayna Ebrahimi, Ali Etemad, Ahmad Beirami, Sercan Arik, Tomas Pfister
1. [Alleviating Hallucinations in Large Vision-Language Models through Hallucination-Induced Optimization](https://nips.cc/virtual/2024/poster/95118), NeurIPS 2024, \
Xinyu Lyu, Beitao Chen, Lianli Gao, Hengtao Shen, Jingkuan Song

### [1.6 Training](#content)
1. [PerturboLLaVA: Reducing Multimodal Hallucinations with Perturbative Visual Training](https://iclr.cc/virtual/2025/poster/28657), ICLR 2025, \
Cong Chen, Mingyu Liu, Chenchen Jing, Yizhou Zhou, Fengyun Rao, Hao Chen, Bo Zhang, Chunhua Shen

### [1.7 Internal Embeddings](#content)
1. [Interpreting and Editing Vision-Language Representations to Mitigate Hallucinations](https://iclr.cc/virtual/2025/poster/30724), ICLR 2025, \
Nick Jiang, Anish Kachinthaya, Suzanne Petryk, Yossi Gandelsman


## [2. Applications](#content)
### [2.1 Revolutionay Generative Models](#content)
1. [Looks Too Good To Be True: An Information-Theoretic Analysis of Hallucinations in Generative Restoration Models](https://arxiv.org/abs/2405.16475), NeurIPS 2024, \
Regev Cohen, Idan Kligvasser, Ehud Rivlin, Daniel Freedman

### [2.2 Promptable Segmentation](#content)
1. [Leveraging Hallucinations to Reduce Manual Prompt Dependency in Promptable Segmentation](https://nips.cc/virtual/2024/poster/96318), NeurIPS 2024, \
Jian Hu, Jiayi Lin, Junchi Yan, Shaogang Gong

### [2.3 Audio Visual Models](#content)
1. [AVHBench: A Cross-Modal Hallucination Benchmark for Audio-Visual Large Language Models](https://iclr.cc/virtual/2025/poster/28638), ICLR 2025, \
Kim Sung-Bin, Oh Hyun-Bin, Lee Jung-Mok, Arda Senocak, Joon Son Chung, Tae-Hyun Oh