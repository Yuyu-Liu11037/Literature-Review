## Table of Contents
<table>
<tr><td colspan="2"><a href="#1-data" style="color:#B22222">1. Data</a></td></tr>

<tr><td colspan="2"><a href="#2-visual-encoder" style="color:#B22222">2. Visual Encoder</a></td></tr>

<tr><td colspan="2"><a href="#3-modality-aligning" style="color:#B22222">3. Modality Aligning</a></td></tr>
<tr>
  <td>&ensp;<a href="#31-attention-sink">3.1 Attention Sink</a></td>
  <!-- <td>&ensp;<a href="#12-modality-align">1.2 Modality Align</a></td> -->
</tr>

<tr><td colspan="2"><a href="#4-from-llm" style="color:#B22222">4. From LLM</a></td></tr>

<tr><td colspan="2"><a href="#5-uncategorized" style="color:#B22222">5. Uncategorized</a></td></tr>

<tr><td colspan="2"><a href="#6-language-priors" style="color:#B22222">5. Language Priors</a></td></tr>
</table>

## [1. Data](#content)
1. [Do You Keep an Eye on What I Ask? Mitigating Multimodal Hallucination via Attention-Guided Ensemble Decoding](https://iclr.cc/virtual/2025/poster/27655), ICLR 2025, \
Yeongjae Cho, Keonwoo Kim, Taebaek Hwang, Sungzoon Cho
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: splits an input image into sub-images, uses attention-guided weights to ensemble their logits with the original image’s logits, applies an adaptive plausibility constraint to keep plausible tokens, and provides a faster two-pass variant (FastED).
      
      2. Cause: data (images contain unnecessary/irrelevant objects (misdirecting attention) and when object resolution is low)
    </details>
1. [Ciem: Contrastive instruction evaluation method for better instruction tuning](), NeurIPS workshop 2023, \
Hongyu Hu, Jiyuan Zhang, Minyi Zhao, et al.
1. [Mitigating hallucination in large multi-modal models via robust instruction tuning](), arXiv 2023, \
Fuxiao Liu, Kevin Lin, Linjie Li, et al.
1. [Rlhf-v: Towards trustworthy mllms via behavior alignment from fine-grained correctional human feedback](), arXiv 2023, \
Tianyu Yu, Yuan Yao, Haoye Zhang, et al.

## [2. Visual Encoder](#content)
1. [(VHBench-10) Diving into Mitigating Hallucinations from a Vision Perspective for Large Vision-Language Models](https://arxiv.org/abs/2509.13836), EMNLP 2025, \
Weihang Wang, Xinhao Li, Ziyue Wang, Yan Pang, Jielei Zhang, Peiyi Li, Qiang Zhang, Longwen Gao
1. [Halle-switch: Rethinking and controlling object existence hallucinations in large vision language models for detailed caption](), arXiv 2023, \
Bohan Zhai, Shijia Yang, Xiangchen Zhao
1. [Monkey: Image resolution and text label are important things for large multi-modal models](), arXiv 2023, \
Zhang Li, Biao Yang, Qiang Liu, et al.
1. [Vcoder: Versatile vision encoders for multimodal large language models](), arXiv 2023, \
Jitesh Jain, Jianwei Yang, and Humphrey Shi.
1. [Fine-grained image captioning with clip reward](), NAACL Findings 2022, \
Jaemin Cho, Seunghyun Yoon, Ajinkya Kale, et al.

## [3. Modality Aligning](#content)
1. [Aligning large multimodal models with factually augmented rlhf](), arXiv 2023, \
Zhiqing Sun, Sheng Shen, Shengcao Cao, et al.
1. [Beyond hallucinations: Enhancing lvlms through hallucination-aware direct preference optimization](), arXiv 2023, \
Zhiyuan Zhao, Bin Wang, Linke Ouyang, et al.
1. [Hallucination augmented contrastive learning for multimodal large language model](), arXiv 2023, \
Chaoya Jiang, Haiyang Xu, Mengfan Dong, et al.
1. [Woodpecker: Hallucination correction for multimodal large language models](), arXiv 2023, \
Shukang Yin, Chaoyou Fu, Sirui Zhao, et al.
1. [Internvl: Scaling up vision foundation models and aligning for generic visual-linguistic tasks](), arXiv 2023, \
Zhe Chen, Jiannan Wu, Wenhai Wang, et al.

### [3.1 Attention Sink](#content)
1. [See What You Are Told: Visual Attention Sink in Large Multimodal Models](https://arxiv.org/abs/2503.03321), ICLR 2025, \
Seil Kang, Jinyeong Kim, Junhyeok Kim, Seong Jae Hwang
1. [What drives attention sinks? A study of massive activations and rotational positional encoding in large vision–language models](https://www.sciencedirect.com/science/article/abs/pii/S0306457325003723), IPM 2025, \
Xiaofeng Zhang, Yuanchao Zhu, Chaochen Gu, Jiawei Cao, Hao Cheng, Kaijie Wu

## [4. From LLM](#content)
1. [A Survey on Hallucination in Large Language Models: Principles, Taxonomy, Challenges, and Open Questions](https://dl.acm.org/doi/full/10.1145/3703155), ACM TIS 2025, \
Lei Huang, Weijiang Yu, Weitao Ma, Weihong Zhong, Zhangyin Feng, Haotian Wang, Qianglong Chen, Weihua Peng, Xiaocheng Feng, Bing Qin, Ting Liu
1. [Vigc: Visual instruction generation and correction](), arXiv 2023, \
Bin Wang, Fan Wu, Xiao Han, et al.
1. [Neural path hunter: Reducing hallucination in dialogue systems via path grounding](), EMNLP 2021, \
Nouha Dziri, Andrea Madotto, Osmar R Zaiane, et al.
1. [The curious case of neural text degeneration](), ICLR 2020, \
Ari Holtzman, Jan Buys, Li Du, et al.

## [5. Uncategorized](#content)
1. [A Comprehensive Analysis for Visual Object Hallucination in Large Vision-Language Models](https://arxiv.org/abs/2505.01958), arXiv 2025, \
Liqiang Jing, Guiming Hardy Chen, Ehsan Aghazadeh, Xin Eric Wang, Xinya Du

## [6. Language Priors](#content)
1. [Overcoming Language Priors with Counterfactual Inference for Visual Question Answering](https://aclanthology.org/2023.ccl-1.52/), CNCCL 2023, \
   Ren Zhibo, Wang Huizhen, Zhu Muhua, Wang Yichao, Xiao Tong, Zhu Jingbo
