## Introduction

Hallucination mitigation in Large Language Models (LLMs) addresses the challenge of models producing fluent but factually incorrect or misleading information. Such errors often stem from limitations in training data coverage, overgeneralization, or the model’s tendency to prioritize coherence over accuracy. To reduce hallucinations, researchers explore strategies such as grounding responses in external knowledge sources, refining training data quality, incorporating human feedback for alignment, and applying post-processing techniques like fact-checking or confidence estimation. These methods work toward improving the reliability and trustworthiness of LLM outputs, making them more suitable for high-stakes and real-world use cases.

## Table of Contents

<table>
<tr><td colspan="2"><a href="#1-surveys-books-tools-tutorials" style="color:#B22222">1. Surveys, Books, Tools, Tutorials</a></td></tr>
<tr><td colspan="2"><a href="#2-methods-and-models" style="color:#B22222">2. Methods and Models</a></td></tr>
<tr>
    <td>&ensp;<a href="#21-inference-approaches">2.1 Inference Approaches</a></td>
    <td>&ensp;<a href="#22-datasets-and-benchmarks">2.2 Datasets and Benchmarks</a></td>
  </tr>
<tr><td colspan="2"><a href="#3-applications" style="color:#B22222">3. Applications</a></td></tr>
<tr>
    <td>&ensp;<a href="#31-agent">3.1 Agent</a></td>
    <td>&ensp;<a href="#32-rag">3.2 RAG</a></td>
</tr>
</table>

## [1. Surveys, Books, Tools, Tutorials](#content)

## [2. Methods and Models](#content)
### [2.1 Inference Approaches](#content)
1. [Steer LLM Latents for Hallucination Detection](https://arxiv.org/abs/2503.01917), ICML 2025, \
Seongheon Park, Xuefeng Du, Min-Hsuan Yeh, Haobo Wang, Yixuan Li
1. [In-Context Sharpness as Alerts: An Inner Representation Perspective for Hallucination Mitigation](https://arxiv.org/abs/2403.01548), ICML 2024, \
Shiqi Chen, Miao Xiong, Junteng Liu, Zhengxuan Wu, Teng Xiao, Siyang Gao, Junxian He

### [2.2 Datasets and Benchmarks](#content)
1. [How Language Model Hallucinations Can Snowball](https://arxiv.org/abs/2305.13534), ICML 2024, \
Muru Zhang, Ofir Press, William Merrill, Alisa Liu, Noah A. Smith



## [3. Applications](#content)
### [3.1 Agent](#content)
1. [Reducing Tool Hallucination via Reliability Alignment](https://arxiv.org/abs/2412.04141), ICML 2025, \
Hongshen Xu, Zichen Zhu, Lei Pan, Zihan Wang, Su Zhu, Da Ma, Ruisheng Cao, Lu Chen, Kai Yu

### [3.2 RAG](#content)
1. [Coarse-to-Fine Highlighting: Reducing Knowledge Hallucination in Large Language Models](https://arxiv.org/abs/2410.15116), ICML 2024, \
Qitan Lv, Jie Wang, Hanzhu Chen, Bin Li, Yongdong Zhang, Feng Wu