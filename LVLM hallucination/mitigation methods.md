## Table of Contents

<table>
<tr><td colspan="2"><a href="#1-methods-and-models" style="color:#B22222">1. Methods and Models</a></td></tr>
<tr>
  <td>&ensp;<a href="#11-inference">1.1 Inference</a></td>
  <td>&ensp;<a href="#12-modality-align">1.2 Modality Align</a></td>
</tr>
<tr>
  <td>&ensp;<a href="#13-model-architechture">1.3 Model Architecture</a></td>
  <td>&ensp;<a href="#14-post-hoc-remediation">1.4 Post Hoc Remediation</a></td>
</tr>
<tr>
  <td>&ensp;<a href="#15-fine-tuning">1.5 Fine Tuning</a></td>
  <td>&ensp;<a href="#16-training">1.6 Training</a></td>
</tr>
<tr>
  <td>&ensp;<a href="#17-internal-embeddings">1.7 Internal Embeddings</a></td>
  <td>&ensp;<a href="#18-model-weights-editing">1.8 Model Weights Editing</a></td>
</tr>
<tr>
  <td>&ensp;<a href="#19-preference-learning">1.9 Preference Learning</a></td>
  <td>&ensp;<a href="#110-data">1.10 Data</a></td>
</tr>
<tr>
  <td>&ensp;<a href="#111-rag">1.11 RAG</a></td>
  <td>&ensp;<a href="#112-(visual)-contrastive-decoding">1.12 (Visual) Contrastive Decoding</a></td>
</tr>

<tr><td colspan="2"><a href="#2-applications" style="color:#B22222">2. Applications</a></td></tr>
<tr>
  <td>&ensp;<a href="#21-revolutionary-generation-models">2.1 Revolutionay Generative Models</a></td>
  <td>&ensp;<a href="#22-promptable-segmentation">2.2 Promptable Segmentation</a></td>
</tr>
<tr>
  <td>&ensp;<a href="#23-audio-visual-models">2.3 Audio Visual Models</a></td>
  <td>&ensp;<a href="#24-video">2.4 Video</a></td>
</tr>
<tr>
  <td>&ensp;<a href="#25-biology">2.5 Biology</a></td>
  <!-- <td>&ensp;<a href="#26-vision-question-answering">2.6 Vision Question Answering</a></td> -->
</tr>
<tr>
  <td>&ensp;<a href="#27-counterfactual-presupposition-questions">2.7 Counterfactual Presupposition Questions</a></td>
  <!-- <td>&ensp;<a href="#26-vision-question-answering">2.6 Vision Question Answering</a></td> -->
</tr>
</table>


## [1. Methods and Models](#content)
### [1.1 Inference](#content)
i.e. Inference-time Decoding
1. [Mitigating Object Hallucinations in Large Vision-Language Models with Assembly of Global and Local Attention](https://arxiv.org/abs/2406.12718), CVPR 2025, \
Wenbin An, Feng Tian, Sicong Leng, Jiahao Nie, Haonan Lin, QianYing Wang, Ping Chen, Xiaoqin Zhang, Shijian Lu
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: Instruction Contrastive Decoding (ICD) appends “disturbance” role prefixes to the instruction to elicit hallucinatory tendencies, computes token distributions under standard vs. disturbed instructions, and selects tokens by penalizing the disturbed distribution—with an adaptive plausibility constraint that truncates to likely tokens.
      
      2. Cause: statistical biases and over-reliance on language priors
  
      3. Detection: They (1) run a hallucination detection analysis on MSCOCO by computing a “hallucination ratio” of objects predicted but absent in the image under baseline/positive/negative disturbance settings; (2) evaluate object-level hallucinations with the POPE binary QA benchmark (reporting Accuracy/Precision/Recall/F1); and (3) use the MME hallucination subset (existence/count/position/color) as QA with task scores. Generative LLaVa-Bench is assessed qualitatively (no automatic metric).
    </details>
1. [INTER: Mitigating Hallucination in Large Vision-Language Models by Interaction Guidance Sampling](https://arxiv.org/abs/2507.05056), ICCV 2025, \
Xin Dong, Shichao Dong, Jin Wang, Jing Huang, Li Zhou, Zenghui Sun, Lihua Jing, Jingsong Lan, Xiaoyong Zhu, Bo Zheng
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: INTER adds an Interactive Guided Locator that flags likely “keyword” steps using the variance of Harsanyi-dividend interaction contributions, and an Interaction Probability Modifier that injects an interaction prior into the logits only at those steps—biasing sampling toward tokens supported by image-text interactions, with no extra training.
      
      2. Cause: modality imbalance
    </details>
1. [Cantor: Inspiring multimodal chainof-thought of mllm](https://arxiv.org/abs/2404.16033), ACM MM 2024, \
Timin Gao, Peixian Chen, Mengdan Zhang, Chaoyou Fu, Yunhang Shen, Yan Zhang, Shengchuan Zhang, Xiawu Zheng, Xing Sun, Liujuan Cao, Rongrong Ji
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: Cantor, a perception-decision CoT framework that injects visual context into the decision-generation stage and then dispatches sub-tasks to four expert roles (TextIntel Extractor, ObjectQuant Locator, VisionIQ Analyst, ChartSense Expert) implemented by a single MLLM, whose outputs are finally synthesized to produce the answer.
      
      2. Cause: 
    </details>

### [1.2 Modality Align](#content)
1. [See What You Are Told: Visual Attention Sink in Large Multimodal Models](https://arxiv.org/abs/2503.03321), ICLR 2025, \
Seil Kang, Jinyeong Kim, Junhyeok Kim, Seong Jae Hwang
1. [Mitigating hallucination for large vision language model by inter-modality correlation calibration decoding](https://arxiv.org/abs/2501.01926), arXiv 2025, \
Jiaming Li, Jiacheng Zhang, Zequn Jie, Lin Ma, Guanbin Li
1. [Cure or Poison? Embedding Instructions Visually Alters Hallucination in Vision-Language Models](https://arxiv.org/abs/2508.01678), arXiv 2025, \
Zhaochen Wang, Yiwei Wang, Yujun Cai
1. [(MOF) Eyes wide shut? exploring the visual shortcomings of multimodal llms](https://arxiv.org/abs/2401.06209), arXiv 2024, \
Shengbang Tong, Zhuang Liu, Yuexiang Zhai, Yi Ma, Yann LeCun, Saining Xie
1. [Enhancing multimodal large language models with vision detection models: An empirical study](https://arxiv.org/abs/2401.17981v2), arXiv 2024, \
Qirui Jiao, Daoyuan Chen, Yilun Huang, Yaliang Li, Ying Shen
1. [Dualfocus: Integrating macro and micro perspectives in multi-modal large language models](https://arxiv.org/abs/2402.14767), arXiv 2024, \
Yuhang Cao, Pan Zhang, Xiaoyi Dong, Dahua Lin, Jiaqi Wang
1. [(VTPrompt) Joint visual and text prompting for improved object-centric perception with multimodal large language models](https://arxiv.org/abs/2404.04514), arXiv 2024, \
Songtao Jiang, Yan Zhang, Chenyi Zhou, Yeying Jin, Yang Feng, Jian Wu, Zuozhu Liu
1. [(COMM) From clip to dino: Visual encoders shout in multi-modal large language models](https://arxiv.org/abs/2310.08825), arXiv 2023, \
Dongsheng Jiang, Yuchen Liu, Songlin Liu, Jin'e Zhao, Hao Zhang, Zhen Gao, Xiaopeng Zhang, Jin Li, Hongkai Xiong

### [1.3 Model Architecture](#content)
1. [MCA-LLaVA: Manhattan Causal Attention for Reducing Hallucination in Large Vision-Language Models](https://arxiv.org/abs/2507.09184), ACM MM 2025, \
Qiyan Zhao, Xiaofeng Zhang, Yiheng Li, Yun Xing, Xiaosong Yuan, Feilong Tang, Sinan Fan, Xuhang Chen, Xuyao Zhang, Dahan Wang
1. [Mitigating Object Hallucination via Concentric Causal Attention](https://arxiv.org/abs/2410.15926), NeurIPS 2024, \
Yun Xing, Yiheng Li, Ivan Laptev, Shijian Lu

### [1.4 Post Hoc Remediation](#content)
1. [Mitigating Object Hallucination in Large Vision-Language Models via Image-Grounded Guidance](https://arxiv.org/abs/2402.08680), ICML 2025, \
Linxi Zhao, Yihe Deng, Weitong Zhang, Quanquan Gu
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: MARINE is a training-free, API-free decoding framework that aggregates object-level signals from open-source image-grounded models (e.g., DETR, RAM++) into a textual guidance prompt and linearly mixes guided vs. unguided logits with a strength parameter γ during generation.
      
      2. Cause: (1) insufficient visual context from the vision encoder, (2) distortion/loss during vision→text projection, and (3) inherent LLM hallucinations
    </details>
1. [Look Twice Before You Answer: Memory-Space Visual Retracing for Hallucination Mitigation in Multimodal Large Language Models](https://arxiv.org/abs/2410.03577), ICML 2025, \
Xin Zou, Yizhou Wang, Yibo Yan, Yuanhuiyi Lyu, Kening Zheng, Sirui Huang, Junkai Chen, Peijie Jiang, Jia Liu, Chang Tang, Xuming Hu
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: MemVR “looks twice” by dynamically detecting high token-level uncertainty and re-injecting visual tokens into a middle FFN layer as key–value “memory,” shifting hidden states without extra training or multi-round decoding.
      
      2. Cause: Modality imbalance
    </details>
1. [DAMO: Decoding by Accumulating Activations Momentum for Mitigating Hallucinations in Vision-Language Models](https://iclr.cc/virtual/2025/poster/30108), ICLR 2025, \
Kaishen Wang, Hengrui Gu, Meijun Gao, Kaixiong Zhou
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: DAMO, a training-free decoding scheme that accumulates “activation momentum” across layers and, when a divergence in layer-wise prediction trends is detected, adaptively refines later-layer activations with a higher momentum weight to preserve earlier visual semantics.
      
      2. Cause: localized surges in later layers —- models “overthink”
    </details>
1. [Mitigating Modality Prior-Induced Hallucinations in Multimodal Large Language Models via Deciphering Attention Causality](https://iclr.cc/virtual/2025/poster/30629), ICLR 2025, \
Guanyu Zhou, Yibo Yan, Xin Zou, Kun Wang, Aiwei Liu, Xuming Hu
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: CAUSALMM, a structural-causal-model–based decoding framework that treats visual and language priors as confounders and applies back-door adjustment with counterfactual interventions on both visual and language attention to realign outputs with the actual multimodal inputs.
      
      2. Cause: Bias from modality priors
    </details>
1. [Intervening Anchor Token: Decoding Strategy in Alleviating Hallucinations for MLLMs](https://iclr.cc/virtual/2025/poster/27678), ICLR 2025, \
Barrett Tang, Zile Huang, Chengzhi Liu, Qiang Sun, Harry Yang, Ser-Nam Lim
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: TAME—a plug-and-play inference-time reparameterization of the QK matrix, which dynamically shrinks/puffs the eigenspectrum variance to curb over-propagation of anchor tokens—requiring no extra decoding passes or training.
      
      2. Cause: anchor tokens over-propagate
    </details>
1. [Understanding and Mitigating Hallucination in Large Vision-Language Models via Modular Attribution and Intervention](https://iclr.cc/virtual/2025/poster/30556), ICLR 2025, \
Tianyun Yang, Ziniu Li, Juan Cao, Chang Xu
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: Use causal mediation via zero-ablation to quantify each module/head’s effect, identify “hallucination heads” (mostly mid/deep MHA heads), analyze their text-over-image attention bias and inheritance from the base LLM, then mitigate with a decoding-time adaptive deactivation (AD-HH) and a targeted fine-tuning (TF-HH) that reduce text-token reliance.
      
      2. Cause: specific multi-head attention heads that over-attend to prior text (vs. image)
    </details>
1. [Seeing Far and Clearly: Mitigating Hallucinations in MLLMs with Attention Causal Decoding](https://arxiv.org/abs/2505.16652), CVPR 2025, \
Feilong Tang, Chengzhi Liu, Zhongxing Xu, Ming Hu, Zelin Peng, Zhiwei Yang, Jionglong Su, Minquan Lin, Yifan Peng, Xuelian Cheng, Imran Razzak, Zongyuan Ge
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: FarSight, a plug-and-play decoding strategy that alters the causal mask with (i) upper-triangular attention registers to absorb outlier-token attention and (ii) a progressively diminishing masking rate to encode absolute positional awareness, improving vision↔text token propagation without extra training.
      
      2. Cause: attention collapse and positional information decay
    </details>
1. [Analyzing and Mitigating Object Hallucination in Large Vision-Language Models](https://arxiv.org/abs/2310.00754), ICLR 2024, \
Yiyang Zhou, Chenhang Cui, Jaehong Yoon, Linjun Zhang, Zhun Deng, Chelsea Finn, Mohit Bansal, Huaxiu Yao
1. [Volcano: mitigating multimodal hallucination through self-feedback guided revision](https://arxiv.org/abs/2311.07362), NAACL 2024, \
Seongyun Lee, Sue Hyun Park, Yongrae Jo, Minjoon Seo
1. [Woodpecker: Hallucination correction for multimodal large language models](https://arxiv.org/abs/2310.16045), arXiv 2023, \
Shukang Yin, Chaoyou Fu, Sirui Zhao, Tong Xu, Hao Wang, Dianbo Sui, Yunhang Shen, Ke Li, Xing Sun, Enhong Chen
1. [Analyzing and mitigating object hallucination in large visionlanguage models](https://arxiv.org/abs/2310.00754), arXiv 2023, \
Yiyang Zhou, Chenhang Cui, Jaehong Yoon, Linjun Zhang, Zhun Deng, Chelsea Finn, Mohit Bansal, Huaxiu Yao

### [1.5 Fine Tuning](#content)
1. [Mitigating Object Hallucination in MLLMs via Data-augmented Phrase-level Alignment](https://iclr.cc/virtual/2025/poster/27739), ICLR 2025, \
Pritam Sarkar, Sayna Ebrahimi, Ali Etemad, Ahmad Beirami, Sercan Arik, Tomas Pfister
1. [Mitigating Object Hallucinations in Large Vision-Language Models via Attention Calibration](https://arxiv.org/abs/2502.01969), arXiv 2025, \
Younan Zhu, Linwei Tao, Minjing Dong, Chang Xu
1. [Efuf: Efficient fine-grained unlearning framework for mitigating hallucinations in multimodal large language models](https://arxiv.org/abs/2402.09801), EMNLP 2024, \
Shangyu Xing, Fei Zhao, Zhen Wu, Tuo An, Weihao Chen, Chunhui Li, Jianbing Zhang, Xinyu Dai
Timin Gao, Peixian Chen, Mengdan Zhang, Chaoyou Fu, Yunhang Shen, Yan Zhang, Shengchuan Zhang, Xiawu Zheng, Xing Sun, Liujuan Cao, Rongrong Ji
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: EFUF curates positive/negative sub-sentences using CLIP-based object–image relevance (no paired human labels), then fine-tunes with three losses—positive, negative via gradient ascent, and a sentence loss—to “unlearn” hallucinated objects while preserving fluency.
      
      2. Cause: modality alignment
    </details>
1. [Alleviating Hallucinations in Large Vision-Language Models through Hallucination-Induced Optimization](https://nips.cc/virtual/2024/poster/95118), NeurIPS 2024, \
Xinyu Lyu, Beitao Chen, Lianli Gao, Hengtao Shen, Jingkuan Song

### [1.6 Training](#content)
1. [PerturboLLaVA: Reducing Multimodal Hallucinations with Perturbative Visual Training](https://iclr.cc/virtual/2025/poster/28657), ICLR 2025, \
Cong Chen, Mingyu Liu, Chenchen Jing, Yizhou Zhou, Fengyun Rao, Hao Chen, Bo Zhang, Chunhua Shen
1. [Generate, but Verify: Reducing Hallucination in Vision-Language Models with Retrospective Resampling](https://arxiv.org/abs/2504.13169), arXiv 2025, \
Tsung-Han Wu, Heekyung Lee, Jiaxin Ge, Joseph E. Gonzalez, Trevor Darrell, David M. Chan

### [1.7 Internal Embeddings](#content)
1. [The Hidden Life of Tokens: Reducing Hallucination of Large Vision-Language Models Via Visual Information Steering](https://arxiv.org/abs/2502.03628), ICML 2025, \
Zhuowei Li, Haizhou Shi, Yunhe Gao, Di Liu, Zhenting Wang, Yuxiao Chen, Ting Liu, Long Zhao, Hao Wang, Dimitris N. Metaxas
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: The authors propose VISTA, a training-free, inference-time method that (i) injects a Visual Steering Vector (VSV) into activations to reinforce image evidence and (ii) performs Self-Logits Augmentation (SLA) by ensembling late-layer (pre-final) logits to bias decoding toward semantically grounded tokens, improving factual grounding across decoding strategies.
      
      2. Cause: gradual visual information loss as language priors accumulate in the residual stream
    </details>
1. [Reducing Hallucinations in Large Vision-Language Models via Latent Space Steering](https://iclr.cc/virtual/2025/poster/30013), ICLR 2025, \
Sheng Liu, Haotian Ye, James Y Zou
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: Visual & Textual Intervention (VTI)—a training-free, test-time latent-space steering method that pre-computes stable “directions” from (i) averaged embeddings of lightly masked images and (ii) pairs of non-hallucinated vs. hallucinated captions, then adds these vectors to all layers during decoding to curb hallucinations.
      
      2. Cause: Modality imbalance
    </details>
1. [Interpreting and Editing Vision-Language Representations to Mitigate Hallucinations](https://iclr.cc/virtual/2025/poster/30724), ICLR 2025, \
Nick Jiang, Anish Kachinthaya, Suzanne Petryk, Yossi Gandelsman
1. [VASparse: Towards Efficient Visual Hallucination Mitigation via Visual-Aware Token Sparsification](https://arxiv.org/abs/2501.06553), CVPR 2025, \
Xianwei Zhuang, Zhihong Zhu, Yuxin Xie, Liming Liang, Yuexian Zou
1. [See What You Are Told: Visual Attention Sink in Large Multimodal Models](https://arxiv.org/abs/2503.03321), arXiv 2025, \
Seil Kang, Jinyeong Kim, Junhyeok Kim, Seong Jae Hwang
1. [Don't Miss the Forest for the Trees: Attentional Vision Calibration for Large Vision Language Models](https://arxiv.org/abs/2405.17820), ACL Findings 2025, \
Sangmin Woo, Donguk Kim, Jaehyuk Jang, Yubin Choi, Changick Kim
1. [Mitigating hallucinations in large vision-language models by adaptively constraining information flow](https://arxiv.org/abs/2502.20750), AAAI 2025, \
Jiaqi Bai, Hongcheng Guo, Zhongyuan Peng, Jian Yang, Zhoujun Li, Mohan Li, Zhihong Tian
1. [ICT: Image-Object Cross-Level Trusted Intervention for Mitigating Object Hallucination in Large Vision-Language Models](https://arxiv.org/abs/2411.15268), CVPR 2025, \
Junzhe Chen, Tianshu Zhang, Shiyu Huang, Yuwei Niu, Linfeng Zhang, Lijie Wen, Xuming Hu
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: ICT applies training-free, forward-pass interventions that add precomputed activation-shift vectors to selected attention heads—at both image-level and object-level—identified via headwise binary classifiers, to boost reliance on visual evidence without erasing helpful language priors.
      
      2. Cause: over-reliance on language priors
    </details>

### [1.8 Model Weights Editing](#content)
1. [When Images Speak Louder: Mitigating Language Bias-induced Hallucinations in VLMs through Cross-Modal Guidance](https://arxiv.org/abs/2510.10466), arXiv 2025, \
Jinjin Cao, Zhiyang Chen, Zijun Wang, Liyuan Ma, Weijian Luo, Guojun Qi
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: They propose Cross-Modal Guidance (CMG), a training-free decoding scheme that builds an “amateur” model by masking cross-modal and inter-visual attention in selected layers, then reweights the original logits using a PMI-style ratio between the original and masked output distributions, with dynamic attention masking and dynamic layer selection (via cosine-similarity) to choose where to mask.
      
      2. Cause: language bias (image-token attention decays through depth while text/system tokens dominate)
    </details>
1. [Nullu: Mitigating Object Hallucinations in Large Vision-Language Models via HalluSpace Projection](https://arxiv.org/abs/2412.13817), CVPR 2025, \
Le Yang, Ziwei Zheng, Boxu Chen, Zhengyu Zhao, Chenhao Lin, Chao Shen

### [1.9 Preference Learning](#content)
1. [Stop Learning it all to Mitigate Visual Hallucination, Focus on the Hallucination Target](https://arxiv.org/abs/2506.11417), CVPR 2025, \
Dokyoon Yoon, Youngsook Song, Woomyong Park
1. [Mitigating Hallucinations in Large Vision-Language Models via DPO: On-Policy Data Hold the Key](https://chatgpt.com/c/68d76812-3148-8326-b324-0f8bae04582f), CVPR 2025, \
Zhihe Yang, Xufang Luo, Dongqi Han, Yunjian Xu, Dongsheng Li
1. [(Fact-RLHF) Aligning large multimodal models with factually augmented rlhf](https://arxiv.org/abs/2309.14525), NAACL 2024, \
Zhiqing Sun, Sheng Shen, Shengcao Cao, Haotian Liu, Chunyuan Li, Yikang Shen, Chuang Gan, Liang-Yan Gui, Yu-Xiong Wang, Yiming Yang, Kurt Keutzer, Trevor Darrell
1. [Detecting and preventing hallucinations in large vision language models](https://arxiv.org/abs/2308.06394), AAAI 2024, \
Anisha Gunjal, Jihan Yin, Erhan Bas
1. [Beyond hallucinations: Enhancing lvlms through hallucination-aware direct preference optimization](https://arxiv.org/abs/2311.16839), arXiv 2023, \
Zhiyuan Zhao, Bin Wang, Linke Ouyang, Xiaoyi Dong, Jiaqi Wang, Conghui He
1. [Training language models to follow instructions with human feedback](https://arxiv.org/abs/2203.02155), NeurIPS 2022, \
Long Ouyang, Jeff Wu, Xu Jiang, Diogo Almeida, Carroll L. Wainwright, Pamela Mishkin, Chong Zhang, Sandhini Agarwal, Katarina Slama, Alex Ray, John Schulman, Jacob Hilton, Fraser Kelton, Luke Miller, Maddie Simens, Amanda Askell, Peter Welinder, Paul Christiano, Jan Leike, Ryan Lowe
1. [Training a helpful and harmless assistant with reinforcement learning from human feedback](https://arxiv.org/abs/2204.05862), arXiv 2022, \
Yuntao Bai, Andy Jones, Kamal Ndousse, Amanda Askell, Anna Chen, Nova DasSarma, Dawn Drain, Stanislav Fort, Deep Ganguli, Tom Henighan, Nicholas Joseph, Saurav Kadavath, Jackson Kernion, Tom Conerly, Sheer El-Showk, Nelson Elhage, Zac Hatfield-Dodds, Danny Hernandez, Tristan Hume, Scott Johnston, Shauna Kravec, Liane Lovitt, Neel Nanda, Catherine Olsson, Dario Amodei, Tom Brown, Jack Clark, Sam McCandlish, Chris Olah, Ben Mann, Jared Kaplan
1. [Learning to summarize with human feedback](https://arxiv.org/abs/2009.01325), NeurIPS 2020, \
Nisan Stiennon, Long Ouyang, Jeff Wu, Daniel M. Ziegler, Ryan Lowe, Chelsea Voss, Alec Radford, Dario Amodei, Paul Christiano

### [1.10 Data](#content)
1. [Fact: Teaching mllms with faithful, concise and transferable rationales](https://arxiv.org/abs/2404.11129), ACM MM 2024, \
Minghe Gao, Shuang Chen, Liang Pang, Yuan Yao, Jisheng Dang, Wenqiao Zhang, Juncheng Li, Siliang Tang, Yueting Zhuang, Tat-Seng Chua
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: Generate executable visual programs for image–question pairs and keep only those that yield the correct answer (faithfulness); convert execution traces into natural-language CoTs via AST-based pruning, symbolic merging, and logical bridging (conciseness); filter CoTs by their utility on end-to-end models (transferability); then distill labels+CoTs jointly into MLLMs.
      
      2. Cause: spurious correlations and include irrelevant in-context information
    </details>
1. [CIEM: Contrastive Instruction Evaluation Method for Better Instruction Tuning](https://arxiv.org/abs/2309.02301), NeurIPS 2023 Workshop, \
   Hongyu Hu, Jiyuan Zhang, Minyi Zhao, Zhenbang Sun
1. [Mllms-augmented visual-language representation learning](), arXiv 2023, \
Y. Liu, K. Wang, W. Shao, P. Luo, Y. Qiao, M. Z. Shou, K. Zhang
1. [Mitigating hallucination in large multi-modal models via robust instruction tuning](), ICLR 2023, \
F. Liu, K. Lin, L. Li, J. Wang, Y. Yacoob, and L. Wang
1. [Hallucidoctor: Mitigating hallucinatory toxicity in visual instruction data](), arXiv 2023, \
Q. Yu, J. Li, L. Wei, L. Pang, W. Ye, B. Qin, S. Tang, Q. Tian, and Y. Zhuang

### [1.11 RAG](#content)
1. [(ARA) Alleviating Hallucination in Large Vision-Language Models with Active Retrieval Augmentation](https://dl.acm.org/doi/full/10.1145/3742434), ACM TMC 2025, \
Xiaoye Qu, Qiyuan Chen, Wei Wei, Jiashuo Sun, Daizong Liu, Jianfeng Dong

### [1.12 (Visual) Contrastive Decoding](#content)
1. [Mitigating Hallucinations in Large Vision-Language Models with Instruction Contrastive Decoding](https://arxiv.org/abs/2403.18715), ACL Findings 2024, \
Xintong Wang, Jingheng Pan, Liang Ding, Chris Biemann
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: Instruction Contrastive Decoding (ICD) appends “disturbance” role prefixes to the instruction to elicit hallucinatory tendencies, computes token distributions under standard vs. disturbed instructions, and selects tokens by penalizing the disturbed distribution—with an adaptive plausibility constraint that truncates to likely tokens.
      
      2. Cause: statistical biases and over-reliance on language priors
    </details>
1. [Self-Augmented Visual Contrastive Decoding](https://arxiv.org/abs/2510.13315), arXiv 2025, \
Eun Woo Im, Muhammad Kashif Ali, Vivek Gupta
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: The method (SAVCD) first uses a self-augmentation selection prompt to have the model pick a text-query–relevant visual augmentation, then applies visual contrastive decoding with a new Sparsity Adaptive Truncation that sets a confidence-aware threshold from the full logit entropy to prune implausible next-token candidates.
      
      2. Cause: auto-regressive training objective / modality misalignment / contextual failures
    </details>
1. [Watermarking for Factuality: Guiding Vision-Language Models Toward Truth via Tri-layer Contrastive Decoding](https://arxiv.org/abs/2510.14304), EMNLP 2025 Findings, \
Kyungryul Back, Seongbeom Park, Milim Kim, Mincheol Kwon, SangHyeok Lee, Hyunyoung Lee, Junhee Cho, Seunghyun Park, Jinkyu Kim
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: A training-free tri-layer contrastive decoding: pick a mature (top) layer and an amateur layer, use a watermark question to find a visually grounded pivot layer, then contrast their logits to generate the final answer.
      
      2. Cause: modality imbalance
    </details>
1. [SECOND: Mitigating Perceptual Hallucination in Vision-Language Models via Selective and Contrastive Decoding](https://arxiv.org/abs/2506.08391), ICML 2025, \
Woohyeon Park, Woojin Kim, Jaeik Kim, Jaeyoung Do
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: A training-free, multi-stage pipeline that (i) builds multi-scale visual tokens via down-/re-scaling and positional-embedding interpolation, (ii) selects high-attention patches stage-by-stage using an entropy-controlled rate, and (iii) applies multi-stage contrastive decoding that contrasts successive “amateur→expert” outputs to sharpen grounding.
      
      2. Cause: indiscriminately fuse multi-scale patches
  
      3. Detection: They (a) define a hallucination probability P_Hal from the model’s token likelihoods and analyze it, and (b) compute an Attention Dice Coefficient by combining vision self-attention and cross-attention against segmentation masks to quantify grounding; empirically, higher alignment ↔ lower P_Hal. Benchmarks then evaluate hallucination via POPE’s yes/no object-presence queries.
    </details>
1. [Self-Introspective Decoding: Alleviating Hallucinations for Large Vision-Language Models](https://iclr.cc/virtual/2025/poster/28166), ICLR 2025, \
Fushuo Huo, Wenchao Xu, Zhong Zhang, Haozhao Wang, Zhicheng Chen, Peilin Zhao
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: Self-Introspective Decoding (SID), which uses a Context & Text-aware Token Selection (CT2S) scheme to keep the least important vision tokens after early decoder layers to amplify vision–text association hallucinations and then subtracts them from the original logits to yield more faithful next-token predictions.
      
      2. Cause: not clearly mentioned. this work is an improvement of CD methods.
    </details>
1. [Do You Keep an Eye on What I Ask? Mitigating Multimodal Hallucination via Attention-Guided Ensemble Decoding](https://iclr.cc/virtual/2025/poster/27655), ICLR 2025, \
Yeongjae Cho, Keonwoo Kim, Taebaek Hwang, Sungzoon Cho
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: splits an input image into sub-images, uses attention-guided weights to ensemble their logits with the original image’s logits, applies an adaptive plausibility constraint to keep plausible tokens, and provides a faster two-pass variant (FastED).
      
      2. Cause: data (images contain unnecessary/irrelevant objects (misdirecting attention) and when object resolution is low)
    </details>
1. [MLLM can see? Dynamic Correction Decoding for Hallucination Mitigation](https://iclr.cc/virtual/2025/poster/30978), ICLR 2025, \
Chenxi Wang, Xiang Chen, Ningyu Zhang, Bozhong Tian, Haoming Xu, Shumin Deng, Huajun Chen
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: DeCo, a training-free, model-agnostic decoding tweak that dynamically picks a “preceding (anchor) layer” where ground-truth tokens are stronger and softly adds its logits to the final layer (scaled by a modulation coefficient) to correct the next-token distribution.
      
      2. Cause: Visual evidence is recognized in earlier layers but gets suppressed by language priors in deeper layers

      3. Detection: via probing: they train a probe at each transformer layer to answer is-there-an-object (isexist(obj)) and show accuracy peaks in preceding layers; they also perform early-exit analyses to observe activation of ground-truth tokens across layers.
    </details>
1. [Self-Correcting Decoding with Generative Feedback for Mitigating Hallucinations in Large Vision-Language Models](https://iclr.cc/virtual/2025/poster/28052), ICLR 2025, \
Ce Zhang, Zifu Wan, Zhehan Kan, Martin Q. Ma, Simon Stepputtis, Deva Ramanan, Russ Salakhutdinov, Louis-Philippe Morency, Katia Sycara, Yaqi Xie
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: Generate an auxiliary image from the LVLM’s initial response with a text-to-image model, compare next-token distributions conditioned on the original vs. generated image via JS divergence, and apply self-correcting decoding that switches between complementary and contrastive logits fusion (thresholded by that divergence) to fix hallucinations—training-free.
      
      2. Cause: Modality alignment (Primarily over-reliance on language priors from biased training data, and also visual shortcomings (e.g., recognition/counting errors) that aren’t explained by language bias alone.)

      3. Detection: Response-level: lower CLIP similarity between the original image and the image generated from the model’s caption correlates with higher CHAIR hallucination rates; Token-level: larger JS divergence between next-token distributions conditioned on the original vs. generated image aligns with hallucinatory tokens; this same signal gates the decoding (detect-then-correct).
    </details>
1. [Visual Description Grounding Reduces Hallucinations and Boosts Reasoning in LVLMs](https://iclr.cc/virtual/2025/poster/31078), ICLR 2025, \
Sreyan Ghosh, Chandra Kiran Evuru, Sonal Kumar, Utkarsh Tyagi, Oriol Nieto, Zeyu Jin, Dinesh Manocha
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: (address hallucinations in more complex, reasoning-intensive scenarios) Visual Description Grounded Decoding (VDGD)—first self-generate a detailed image description, prepend it to the prompt, then rescore next-token candidates by their KL-divergence to the description so tokens with lower divergence are preferred during decoding.
      
      2. Cause: over-rely on language priors
    </details>
1. [ClearSight: Visual Signal Enhancement for Object Hallucination Mitigation in Multimodal Large Language Models](https://arxiv.org/abs/2503.13107), CVPR 2025, \
Hao Yin, Guangzong Si, Zilei Wang
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: Visual Amplification Fusion (VAF)—that boosts attention to visual tokens and lightly suppresses system-prompt attention specifically in the middle fusion layers (using masked attention score edits and restricting changes to “visual perception” heads) to reduce over-reliance on language priors.
      
      2. Cause: Not an overactive language signal per se, but insufficient attention to visual information during mid-layer modality fusion, which skews predictions toward language priors.

      3. Comment: proposes limitations of CD
    </details>
1. [IBD: Alleviating Hallucinations in Large Vision-Language Models via Image-Biased Decoding](https://openaccess.thecvf.com/content/CVPR2025W/TMM-OpenWorld/html/Zhu_IBD_Alleviating_Hallucinations_in_Large_Vision-Language_Models_via_Image-Biased_Decoding_CVPRW_2025_paper.html), CVPR Workshop 2025, \
Lanyun Zhu, Deyi Ji, Tianrun Chen, Peng Xu, Jieping Ye, Jun Liu
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: Build an image-biased variant of the LVLM by boosting attention to image tokens, then contrast its logits with the original model (contrastive decoding) and dynamically weight this signal using JSD-based indicators plus an adaptive candidate filter and a lightweight prompt-tuned adapter.
      
      2. Cause: over-reliance on language priors
    </details>
1. [Mitigating Hallucination of Large Vision-Language Models via Dynamic Logits Calibration](https://arxiv.org/abs/2506.21509), arXiv 2025, \
Jiahe Chen, Jiaying He, Qian Shao, Qiyuan Chen, Jiahe Ying, Hongxia Xu, Jintai Chen, Jianwei Zheng, Jian Wu
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: During generation, they use CLIP to score image–text alignment for each top-k candidate token, compare it to a running visual-consistency baseline, compute a Relative Visual Advantage, and multiplicatively calibrate logits to favor visually grounded tokens—no extra forward passes.
      
      2. Cause: over-reliance on language priors (Progressive semantic drift—an increasing reliance on linguistic priors over visual evidence as decoding proceeds)

      4. Question: is it related to attention sink?
    </details>
1. [Don't Miss the Forest for the Trees: Attentional Vision Calibration for Large Vision Language Models](https://arxiv.org/abs/2405.17820), ACL Findings 2025, \
Sangmin Woo, Donguk Kim, Jaehyuk Jang, Yubin Choi, Changick Kim
1. [Octopus: Alleviating Hallucination via Dynamic Contrastive Decoding](https://arxiv.org/abs/2503.00361), CVPR 2025, \
Wei Suo, Lijun Zhang, Mengyang Sun, Lin Yuanbo Wu, Peng Wang, Yanning Zhang
1. [Alleviating hallucinations of large language models through induced hallucinations](https://arxiv.org/abs/2312.15710), NAACL 2025, \
   Yue Zhang, Leyang Cui, Wei Bi, Shuming Shi
1. [Pensieve: Retrospect-then-compare mitigates visual hallucination](https://arxiv.org/abs/2403.14401), arXiv 2024, \
Dingchen Yang, Bowen Cao, Guang Chen, Changjun Jiang
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: Pensieve is a training-free “retrospect-then-compare” decoder that retrieves semantically similar reference images, subtracts their per-token confidence (logits) from the test image’s logits—plus a diffused (text-only) view and adaptively scales these terms to suppress visually/textually deceptive candidates during generation.
      
      2. Cause: The visual branch often gives similar confidence to both accurate and wrong token candidates (i.e., it’s uncertain and “equally advocates” them), and similar images tend to induce analogous hallucinations
    </details>
1. [HALC: Object Hallucination Reduction via Adaptive Focal-Contrast Decoding](https://arxiv.org/abs/2403.00425), ICML 2024, \
Zhaorun Chen, Zhuokai Zhao, Hongyin Luo, Huaxiu Yao, Bo Li, Jiawei Zhou
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: HALC identifies object-related tokens (via POS tags), retrieves token-wise visual contexts using zero-shot detectors (Grounding DINO/OWLv2), samples/contrasts multiple fields-of-view with JSD to reweight logits, and then selects continuations using a visual matching–based beam search (BLIP/CLIP), all as a plug-and-play decoding module.
      
      2. Cause: rely increasingly on prior text
    </details>
1. [CODE: Contrasting Self-generated Description to Combat Hallucination in Large Multi-modal Models](https://arxiv.org/abs/2406.01920), NeurIPS 2024, \
Junho Kim, Hyunjun Kim, Yeonju Kim, Yong Man Ro
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: CODE contrasts next-token logits computed from the real visual input with logits computed from the model’s own comprehensive description of that image, then applies a dynamic restriction (αₜ) and an adaptive information constraint (βₜ, V_head) to amplify consistent tokens and suppress visually inconsistent ones—without any extra training.
      
      2. Cause: modality alignment
    </details>
1. [Trusting Your Evidence: Hallucinate Less with Context-aware Decoding](https://arxiv.org/abs/2305.14739), NAACL 2024, \
   Weijia Shi, Xiaochuang Han, Mike Lewis, Yulia Tsvetkov, Luke Zettlemoyer, Scott Wen-tau Yih
1. [Opera: Alleviating hallucination in multi-modal large language models via over-trust penalty and retrospection-allocation](https://arxiv.org/abs/2311.17911), CVPR 2024, \
Qidong Huang, Xiaoyi Dong, Pan Zhang, Bin Wang, Conghui He, Jiaqi Wang, Dahua Lin, Weiming Zhang, Nenghai Yu
1. [Multi-modal hallucination control by visual information grounding](https://arxiv.org/abs/2403.14003), CVPR 2024, \
   Alessandro Favero, Luca Zancato, Matthew Trager, Siddharth Choudhary, Pramuditha Perera, Alessandro Achille, Ashwin Swaminathan, Stefano Soatto
1. [Mitigating object hallucinations in large vision-language models through visual contrastive decoding](https://arxiv.org/abs/2311.16922), CVPR 2024, \
   Sicong Leng, Hang Zhang, Guanzheng Chen, Xin Li, Shijian Lu, Chunyan Miao, Lidong Bing
1. [Hallucination Augmented Contrastive Learning for Multimodal Large Language Model](https://arxiv.org/abs/2312.06968), CVPR 2024, \
   Chaoya Jiang, Haiyang Xu, Mengfan Dong, Jiaxing Chen, Wei Ye, Ming Yan, Qinghao Ye, Ji Zhang, Fei Huang, Shikun Zhang
1. [Inference-time intervention: Eliciting truthful answers from a language model](https://arxiv.org/abs/2306.03341), NeurIPS 2023, \
   Kenneth Li, Oam Patel, Fernanda Viégas, Hanspeter Pfister, Martin Wattenberg
1. [Dola: Decoding by contrasting layers improves factuality in large language models](https://arxiv.org/abs/2309.03883), arXiv 2023, \
   Yung-Sung Chuang, Yujia Xie, Hongyin Luo, Yoon Kim, James Glass, Pengcheng He
1. [Contrastive decoding: Open-ended text generation as optimization](https://arxiv.org/abs/2210.15097), ACL 2023, \
   Xiang Lisa Li, Ari Holtzman, Daniel Fried, Percy Liang, Jason Eisner, Tatsunori Hashimoto, Luke Zettlemoyer, Mike Lewis

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

### [2.4 Video](#content)
1. [VidHalluc: Evaluating Temporal Hallucinations in Multimodal Large Language Models for Video Understanding](https://arxiv.org/abs/2412.03735), CVPR 2025, \
Chaoyu Li, Eun Woo Im, Pooyan Fazli
1. [MASH-VLM: Mitigating Action-Scene Hallucination in Video-LLMs through Disentangled Spatial-Temporal Representations](https://arxiv.org/abs/2503.15871), CVPR 2025, \
Kyungho Bae, Jinhyung Kim, Sihaeng Lee, Soonyoung Lee, Gunhee Lee, Jinwoo Choi

### [2.5 Biology](#content)
**CXR**
1. [FactCheXcker: Mitigating Measurement Hallucinations in Chest X-ray Report Generation Models](https://arxiv.org/abs/2411.18672), CVPR 2025, \
Alice Heiman, Xiaoman Zhang, Emma Chen, Sung Eun Kim, Pranav Rajpurkar

### [2.7 Counterfactual Presupposition Questions](#content)
1. [Antidote: A Unified Framework for Mitigating LVLM Hallucinations in Counterfactual Presupposition and Object Perception](https://arxiv.org/abs/2504.20468), CVPR 2025, \
Yuanchen Wu, Lu Zhang, Hang Yao, Junlong Du, Ke Yan, Shouhong Ding, Yunsheng Wu, Xiaoqiang Li

### [2.8 Reasoning Models](#content)
1. [Mitigating Hallucination in Multimodal Reasoning via Functional Attention Control](https://arxiv.org/abs/2510.10285), arXiv 2025, \
Haolang Lu, Bolun Chu, WeiYe Fu, Guoshun Nan, Junning Liu, Minghui Pan, Qiankun Li, Yi Yu, Hua Wang, Kun Wang
