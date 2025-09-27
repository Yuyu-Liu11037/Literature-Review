## Introduction

Hallucination mitigation in Large Language Models (LLMs) addresses the challenge of models producing fluent but factually incorrect or misleading information. Such errors often stem from limitations in training data coverage, overgeneralization, or the model’s tendency to prioritize coherence over accuracy. To reduce hallucinations, researchers explore strategies such as grounding responses in external knowledge sources, refining training data quality, incorporating human feedback for alignment, and applying post-processing techniques like fact-checking or confidence estimation. These methods work toward improving the reliability and trustworthiness of LLM outputs, making them more suitable for high-stakes and real-world use cases.

## Table of Contents

<table>
<tr><td colspan="2"><a href="#1-surveys-books-tools-tutorials" style="color:#B22222">1. Surveys, Books, Tools, Tutorials</a></td></tr>
<tr><td colspan="2"><a href="#2-methods-and-models" style="color:#B22222">2. Methods and Models</a></td></tr>
<tr>
    <td>&ensp;<a href="#21-llm-inference">2.1 LLM Inference</a></td>
    <td>&ensp;<a href="#22-datasets-and-benchmarks">2.2 Datasets and Benchmarks</a></td>
</tr>
<tr>
    <td>&ensp;<a href="#23-internal-embeddings">2.3 Internal Embeddings</a></td>
    <td>&ensp;<a href="#24-hallucination-detection">2.4 Hallucination Detection</a></td>
</tr>
<tr>
    <td>&ensp;<a href="#25-analysis">2.5 Analysis</a></td>
    <td>&ensp;<a href="#26-knowledge-editing">2.6 Knowledge Editing</a></td>
</tr>

<tr><td colspan="2"><a href="#3-applications" style="color:#B22222">3. Applications</a></td></tr>
<tr>
    <td>&ensp;<a href="#31-agent">3.1 Agent</a></td>
    <td>&ensp;<a href="#32-rag">3.2 RAG</a></td>
</tr>
<tr>
  <td>&ensp;<a href="#33-diffusion-models">3.3 Diffusion Models</a></td>
</tr>
</table>

## [1. Surveys, Books, Tools, Tutorials](#content)

## [2. Methods and Models](#content)
### [2.1 LLM Inference](#content)
1. [Steer LLM Latents for Hallucination Detection](https://arxiv.org/abs/2503.01917), ICML 2025, \
Seongheon Park, Xuefeng Du, Min-Hsuan Yeh, Haobo Wang, Yixuan Li
1. [In-Context Sharpness as Alerts: An Inner Representation Perspective for Hallucination Mitigation](https://arxiv.org/abs/2403.01548), ICML 2024, \
Shiqi Chen, Miao Xiong, Junteng Liu, Zhengxuan Wu, Teng Xiao, Siyang Gao, Junxian He

### [2.2 Datasets and Benchmarks](#content)
1. [Can Knowledge Editing Really Correct Hallucinations?](https://iclr.cc/virtual/2025/poster/28744), ICLR 2025, \
Baixiang Huang, Canyu Chen, Xiongxiao Xu, Ali Payani, Kai Shu
1. [K-HALU: Multiple Answer Korean Hallucination Benchmark for Large Language Models](https://iclr.cc/virtual/2025/poster/32080), ICLR 2025, \
Jaehyung Seo, Heuiseok Lim
1. [How Language Model Hallucinations Can Snowball](https://arxiv.org/abs/2305.13534), ICML 2024, \
Muru Zhang, Ofir Press, William Merrill, Alisa Liu, Noah A. Smith
1.[ERBench: An Entity-Relationship based Automatically Verifiable Hallucination Benchmark for Large Language Models](https://nips.cc/virtual/2024/poster/97458), NeurIPS 2024, \
Jio Oh, Soyeon Kim, Junseok Seo, Jindong Wang, Ruochen Xu, Xing Xie, Steven Whang

### [2.3 Internal Embeddings](#content)
1. [NoVo: Norm Voting off Hallucinations with Attention Heads in Large Language Models](https://iclr.cc/virtual/2025/poster/27716), ICLR 2025, \
Zhengyi Ho, Siyuan Liang, Sen Zhang, Yibing Zhan, Dacheng Tao


### [2.4 Hallucination Detection](#content)
1. [HaDeMiF: Hallucination Detection and Mitigation in Large Language Models](https://iclr.cc/virtual/2025/poster/29391), ICLR 2025, \
Xiaoling Zhou, Mingjie Zhang, Zhemg Lee, Wei Ye, Shikun Zhang
1. [HaloScope: Harnessing Unlabeled LLM Generations for Hallucination Detection](https://arxiv.org/abs/2409.17504), NeurIPS 2024, \
Xuefeng Du, Chaowei Xiao, Yixuan Li
1. [ANAH-v2: Scaling Analytical Hallucination Annotation of Large Language Models](https://arxiv.org/abs/2407.04693), NeurIPS 2024, \
Yuzhe Gu, Ziwei Ji, Wenwei Zhang, Chengqi Lyu, Dahua Lin, Kai Chen
1. [LLM-Check: Investigating Detection of Hallucinations in Large Language Models](https://nips.cc/virtual/2024/poster/95584), NeurIPS 2024, \
Gaurang Sriramanan, Siddhant Bharti, Vinu Sankar Sadasivan, Shoumik Saha, Priyatham Kattakinda, Soheil Feizi

### [2.5 Analysis](#content)
1. [Do I Know This Entity? Knowledge Awareness and Hallucinations in Language Models](https://iclr.cc/virtual/2025/poster/29377), ICLR 2025, \
Javier Ferrando, Oscar Obeso, Senthooran Rajamanoharan, Neel Nanda
1. [LLMs Know More Than They Show: On the Intrinsic Representation of LLM Hallucinations](https://iclr.cc/virtual/2025/poster/30060), ICLR 2025, \
Hadas Orgad, Michael Toker, Zorik Gekhman, Roi Reichart, Idan Szpektor, Hadas Kotek, Yonatan Belinkov

### [2.6 Knowledge Editing](#content)
1. [AlphaEdit: Null-Space Constrained Knowledge Editing for Language Models](https://arxiv.org/abs/2410.02355), ICLR 2025 (Oral), \
Junfeng Fang, Houcheng Jiang, Kun Wang, Yunshan Ma, Shi Jie, Xiang Wang, Xiangnan He, Tat-seng Chua



## [3. Applications](#content)
### [3.1 Agent](#content)
1. [Reducing Tool Hallucination via Reliability Alignment](https://arxiv.org/abs/2412.04141), ICML 2025, \
Hongshen Xu, Zichen Zhu, Lei Pan, Zihan Wang, Su Zhu, Da Ma, Ruisheng Cao, Lu Chen, Kai Yu

### [3.2 RAG](#content)
1. [ReDeEP: Detecting Hallucination in Retrieval-Augmented Generation via Mechanistic Interpretability](https://iclr.cc/virtual/2025/poster/27644), ICLR 2025, \
Zhongxiang Sun, Xiaoxue Zang, Kai Zheng, Jun Xu, Xiao Zhang, Weijie Yu, Yang Song, Han Li
1. [Coarse-to-Fine Highlighting: Reducing Knowledge Hallucination in Large Language Models](https://arxiv.org/abs/2410.15116), ICML 2024, \
Qitan Lv, Jie Wang, Hanzhu Chen, Bin Li, Yongdong Zhang, Feng Wu

### [3.3 Diffusion Models](#content)
1. [Towards Understanding Text Hallucination of Diffusion Models via Local Generation Bias](https://iclr.cc/virtual/2025/poster/29614), ICLR 2025, \
Rui Lu, Runzhe Wang, Kaifeng Lyu, Xitai Jiang, Gao Huang, Mengdi Wang
1. [Understanding Hallucinations in Diffusion Models through Mode Interpolation](https://arxiv.org/abs/2406.09358), NeurIPS 2024, \
Sumukh K Aithal, Pratyush Maini, Zachary C. Lipton, J. Zico Kolter