## Table of Contents
<table>
<tr><td colspan="2"><a href="#1-detection" style="color:#B22222">1. Detection</a></td></tr>

<tr><td colspan="2"><a href="#2-benchmarks" style="color:#B22222">2. Benchmarks</a></td></tr>

<tr><td colspan="2"><a href="#3-applications" style="color:#B22222">3. Applications</a></td></tr>
</table>

## [1. Detection](#content)
1. [GLSim: Detecting Object Hallucinations in LVLMs via Global-Local Similarity](https://arxiv.org/abs/2508.19972), NeurIPS 2025, \
Seongheon Park, Sharon Li
1. [PerturboLLaVA: Reducing Multimodal Hallucinations with Perturbative Visual Training](https://iclr.cc/virtual/2025/poster/28657), ICLR 2025, \
Cong Chen, Mingyu Liu, Chenchen Jing, Yizhou Zhou, Fengyun Rao, Hao Chen, Bo Zhang, Chunhua Shen
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: They introduce HalFscore, a concept-level metric built from GPT-4o–extracted triplets and language graphs to measure accuracy & completeness, and propose PerturboLLaVA, a training scheme that injects adversarially perturbed texts to weaken language priors and force stronger image grounding.
      
      2. Cause: over-rely on pretrained language priors

      3. Detection: HalFscore: extract subject–relation–object triplets with GPT-4o from both model captions and ground-truth dense captions, build concept graphs, then compare to mark hallucinations (extra/incorrect concepts) and omissions, computing precision/recall and their F-score.
    </details>
1. [SECOND: Mitigating Perceptual Hallucination in Vision-Language Models via Selective and Contrastive Decoding](https://arxiv.org/abs/2506.08391), ICML 2025, \
Woohyeon Park, Woojin Kim, Jaeik Kim, Jaeyoung Do
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: A training-free, multi-stage pipeline that (i) builds multi-scale visual tokens via down-/re-scaling and positional-embedding interpolation, (ii) selects high-attention patches stage-by-stage using an entropy-controlled rate, and (iii) applies multi-stage contrastive decoding that contrasts successive “amateur→expert” outputs to sharpen grounding.
      
      2. Cause: indiscriminately fuse multi-scale patches
  
      3. Detection: They (a) define a hallucination probability P_Hal from the model’s token likelihoods and analyze it, and (b) compute an Attention Dice Coefficient by combining vision self-attention and cross-attention against segmentation masks to quantify grounding; empirically, higher alignment ↔ lower P_Hal. Benchmarks then evaluate hallucination via POPE’s yes/no object-presence queries.
    </details>
1. [Detecting and mitigating hallucination in large vision language models via fine-grained ai feedback](https://arxiv.org/abs/2404.14233), AAAI 2025, \
Wenyi Xiao, Ziwei Huang, Leilei Gan, Wanggui He, Haoyuan Li, Zhelun Yu, Fangxun Shu, Hao Jiang, Linchao Zhu
1. [HalLoc: Token-level Localization of Hallucinations for Vision Language Models](https://arxiv.org/abs/2506.10286), CVPR 2025, \
Eunkyu Park, Minyeong Kim, Gunhee Kim
1. [Mitigating Hallucinations in Large Vision-Language Models with Instruction Contrastive Decoding](https://arxiv.org/abs/2403.18715), ACL Findings 2024, \
Xintong Wang, Jingheng Pan, Liang Ding, Chris Biemann
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: Instruction Contrastive Decoding (ICD) appends “disturbance” role prefixes to the instruction to elicit hallucinatory tendencies, computes token distributions under standard vs. disturbed instructions, and selects tokens by penalizing the disturbed distribution—with an adaptive plausibility constraint that truncates to likely tokens.
      
      2. Cause: statistical biases and over-reliance on language priors
  
      3. Detection: They (1) run a hallucination detection analysis on MSCOCO by computing a “hallucination ratio” of objects predicted but absent in the image under baseline/positive/negative disturbance settings; (2) evaluate object-level hallucinations with the POPE binary QA benchmark (reporting Accuracy/Precision/Recall/F1); and (3) use the MME hallucination subset (existence/count/position/color) as QA with task scores. Generative LLaVa-Bench is assessed qualitatively (no automatic metric).
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
1. [Devils in Middle Layers of Large Vision-Language Models: Interpreting, Detecting and Mitigating Object Hallucinations via Attention Lens](https://arxiv.org/abs/2411.16724), CVPR 2025, \
Zhangqi Jiang, Junkai Chen, Beier Zhu, Tingjin Luo, Yankun Shen, Xu Yang
    <details> 
      <summary>Digest</summary>
      
      1. Methodology: The paper analyzes middle-layer attention using an “attention lens” (VAR/SVAR) and a logit lens to reveal two stages—visual information enrichment and semantic refinement—then detects hallucinations via low mid-layer visual attention and head inconsistency, and finally mitigates them at inference by reweighting visual attention using head-averaged scores.
      
      2. Cause: improper visual-information processing in middle layers
  
      3. Detection: using SVAR_{5–18} (summed/averaged visual attention ratios across heads in mid layers)
    </details>
1. [Hallo3D: Multi-Modal Hallucination Detection and Mitigation for Consistent 3D Content Generation](https://proceedings.neurips.cc/paper_files/paper/2024/hash/d75660d6eb0ce31360c768fef85301dd-Abstract-Conference.html), NeurIPS 2024, \
Hongbo Wang, Jie Cao, Jin Liu, Xiaoqiang Zhou, Huaibo Huang, Ran He
1. [Estimating the Hallucination Rate of Generative AI](https://nips.cc/virtual/2024/poster/95553), NeurIPS 2024, \
Andrew Jesson, Nicolas Beltran Velez, Quentin Chu, Sweta Karlekar, Jannik Kossen, Yarin Gal, John Cunningham, David Blei
1. [Detecting and preventing hallucinations in large vision language models](https://arxiv.org/abs/2308.06394), AAAI 2024, \
Anisha Gunjal, Jihan Yin, Erhan Bas
1. [(MMHal-Bench) LLaVA-RLHF: Aligning Large Multimodal Models with Factually Augmented RLHF](https://llava-rlhf.github.io/), arXiv 2023, \
Zhiqing Sun, Sheng Shen, Shengcao Cao, Haotian Liu, Chunyuan Li, Yikang Shen, Chuang Gan, Liang-Yan Gui, Yu-Xiong Wang, Yiming Yang, Kurt Keutzer, Trevor Darrell
1. [HallE-Control: Controlling Object Hallucination in Large Multimodal Models](https://arxiv.org/abs/2310.01779), arXiv 2023, \
   Bohan Zhai, Shijia Yang, Chenfeng Xu, Sheng Shen, Kurt Keutzer, Chunyuan Li, Manling Li

## [2. Benchmark](#content)
1. [HALLUCINOGEN: Benchmarking Hallucination in Implicit Reasoning within Large Vision Language Models](https://aclanthology.org/2025.uncertainlp-main.10/), EMNLP 2025, \
Ashish Seth, Dinesh Manocha, Chirag Agarwal
1. [Diving into Mitigating Hallucinations from a Vision Perspective for Large Vision-Language Models](https://arxiv.org/abs/2509.13836), EMNLP 2025, \
Weihang Wang, Xinhao Li, Ziyue Wang, Yan Pang, Jielei Zhang, Peiyi Li, Qiang Zhang, Longwen Gao
1. [Hallucination at a Glance: Controlled Visual Edits and Fine-Grained Multimodal Learning](https://arxiv.org/abs/2506.07227), NeurIPS 2025, \
Tianyi Bai, Yuxuan Fan, Jiantao Qiu, Fupeng Sun, Jiayi Song, Junlin Han, Zichen Liu, Conghui He, Wentao Zhang, Binhang Yuan
1. [Seeing is Believing? Mitigating OCR Hallucinations in Multimodal Large Language Models](https://arxiv.org/abs/2506.20168), NeurIPS 2025, \
Zhentao He, Can Zhang, Ziheng Wu, Zhenghao Chen, Yufei Zhan, Yifan Li, Zhao Zhang, Xian Wang, Minghui Qiu
1. [More Thinking, Less Seeing? Assessing Amplified Hallucination in Multimodal Reasoning Models](https://arxiv.org/abs/2505.21523), NeurIPS 2025, \
Chengzhi Liu, Zhongxing Xu, Qingyue Wei, Juncheng Wu, James Zou, Xin Eric Wang, Yuyin Zhou, Sheng Liu
1. [Discovering Compositional Hallucinations in LVLMs](https://openreview.net/pdf/96e01a47f57625c1c899b56cf6c1cbe0fd642344.pdf), NeurIPS 2025, \
Sibei Yang, Ge Zheng, Jiajin Tang, Jiaye Qian, Hanzhuo Huang, Cheng Shi
1. [MIRAGE: Assessing Hallucination in Multimodal Reasoning Chains of MLLM](https://arxiv.org/abs/2505.24238), NeurIPS 2025, \
Bowen Dong, Minheng Ni, Zitong Huang, Guanglei Yang, Wangmeng Zuo, Lei Zhang
1. [Visual hallucination detection in large vision-language models via evidential conflict](https://www.sciencedirect.com/science/article/abs/pii/S0888613X25001483), ICAR 2025, \
Tao Huang, Zhekun Liu, Rui Wang, Yang Zhang, Liping Jing
1. [ODE: Open-Set Evaluation of Hallucinations in Multimodal Large Language Models](https://arxiv.org/abs/2409.09318), CVPR 2025, \
Yahan Tu, Rui Hu, Jitao Sang
1. [PhD: A ChatGPT-Prompted Visual Hallucination Evaluation Dataset](https://huggingface.co/datasets/AIMClab-RUC/PhD), CVPR 2025, \
Jiazhen Liu, Yuhan Fu, Ruobing Xie, Runquan Xie, Xingwu Sun, Fengzong Lian, Zhanhui Kang, Xirong Li
1. [3D-GRAND: A Million-Scale Dataset for 3D-LLMs with Better Grounding and Less Hallucination](https://arxiv.org/abs/2406.05132), CVPR 2025, \
Jianing Yang, Xuweiyi Chen, Nikhil Madaan, Madhavan Iyengar, Shengyi Qian, David F. Fouhey, Joyce Chai
1. [(VHBench-10) Diving into Mitigating Hallucinations from a Vision Perspective for Large Vision-Language Models](https://arxiv.org/abs/2509.13836), EMNLP 2025, \
Weihang Wang, Xinhao Li, Ziyue Wang, Yan Pang, Jielei Zhang, Peiyi Li, Qiang Zhang, Longwen Gao
1. [(VHILT) Defining and Quantifying Visual Hallucinations in Vision-Language Models](https://aclanthology.org/2025.trustnlp-main.32/), TrustNLP 2025, \
Vipula Rawte, Aryan Mishra, Amit Sheth, Amitava Das
1. [A Comprehensive Analysis for Visual Object Hallucination in Large Vision-Language Models](https://arxiv.org/abs/2505.01958), arXiv 2025, \
Liqiang Jing, Guiming Hardy Chen, Ehsan Aghazadeh, Xin Eric Wang, Xinya Du
1. [Visual hallucination detection in large vision-language models via evidential conflict](https://www.sciencedirect.com/science/article/abs/pii/S0888613X25001483), IJAR 2025, \
Tao Huang, Zhekun Liu, Rui Wang, Yang Zhang, Liping Jing
1. [Mm-vet: Evaluating large multimodal models for integrated capabilities](https://arxiv.org/abs/2308.02490), ICML 2024, \
   Weihao Yu, Zhengyuan Yang, Linjie Li, Jianfeng Wang, Kevin Lin, Zicheng Liu, Xinchao Wang, Lijuan Wang
1. [Evaluating and Analyzing Relationship Hallucinations in Large Vision-Language Models](https://arxiv.org/abs/2406.16449), ICML 2024, \
Mingrui Wu, Jiayi Ji, Oucheng Huang, Jiale Li, Yuhang Wu, Xiaoshuai Sun, Rongrong Ji
1. [Toward a Stable, Fair, and Comprehensive Evaluation of Object Hallucination in Large Vision-Language Models](https://nips.cc/virtual/2024/poster/93023), NeurIPS 2024, \
Hongliang Wei, Xingtao Wang, Xianqi Zhang, Xiaopeng Fan, Debin Zhao
1. [Multi-Object Hallucination in Vision Language Models](https://nips.cc/virtual/2024/poster/95666), NeurIPS 2024, \
Xuweiyi Chen, Ziqiao Ma, Xuejun Zhang, Sihan Xu, Shengyi Qian, Jianing Yang, David Fouhey, Joyce Chai
1. [Mm-sap: A comprehensive benchmark for assessing self-awareness of multimodal large language models in perception](), arXiv 2024, \
Y. Wang, Y. Liao, H. Liu, H. Liu, Y. Wang, and Y. Wang
1. [(VHTest) Visual hallucinations of multi-modal large language models](), arXiv 2024, \
W. Huang, H. Liu, M. Guo, and N. Z. Gong
1. [(MAD-Bench) How easy is it to fool your multimodal llms? an empirical analysis on deceptive prompts](), arXiv 2024, \
Y. Qian, H. Zhang, Y. Yang, and Z. Gan
1. [The all-seeing project v2: Towards general relation comprehension of the open world](), arXiv 2024, \
W. Wang, Y. Ren, H. Luo, T. Li, C. Yan, Z. Chen, W. Wang, Q. Li, L. Lu, X. Zhu et al.
1. [(LLaVA-Bench) Visual instruction tuning](https://arxiv.org/abs/2304.08485), NeurIPS 2023, \
   Haotian Liu, Chunyuan Li, Qingyang Wu, Yong Jae Lee
1. [(POPE) Evaluating object hallucination in large vision-language models](https://arxiv.org/abs/2305.10355), EMNLP 2023, \
Yifan Li, Yifan Du, Kun Zhou, Jinpeng Wang, Wayne Xin Zhao, Ji-Rong Wen
1. [(NOPE) Negative object presence evaluation (nope) to measure object hallucination in vision-language models](), ALVR 2024, \
Holy Lovenia, Wenliang Dai, Samuel Cahyawijaya, et al.
1. [Genception: Evaluate multimodal llms with unlabeled unimodal data](), arXiv 2024, \
L. Cao, V. Buchner, Z. Senane, and F. Yang
1. [Mementos: A comprehensive benchmark for multimodal large language model reasoning over image sequences](), arXiv 2024, \
X. Wang, Y. Zhou, X. Liu, H. Lu, Y. Xu, F. He, J. Yoon, T. Lu, G. Bertasius, M. Bansal et al.
1. [Unified hallucination detection for multimodal large language models](), arXiv 2024, \
X. Chen, C. Wang, Y. Xue, N. Zhang, X. Yang, Q. Li, Y. Shen, J. Gu, and H. Chen
1. [Ciem: Contrastive instruction evaluation method for better instruction tuning](), NeurIPS workshop 2023, \
Hongyu Hu, Jiyuan Zhang, Minyi Zhao, et al.
1. [(AMBER) An llm-free multi-dimensional benchmark for mllms hallucination evaluation](https://arxiv.org/abs/2311.07397), arXiv 2023, \
Junyang Wang, Yuhang Wang, Guohai Xu, Jing Zhang, Yukai Gu, Haitao Jia, Jiaqi Wang, Haiyang Xu, Ming Yan, Ji Zhang, Jitao Sang
1. [(EMMA) Evaluation and mitigation of agnosia in multimodal large language models](), arXiv 2023, \
J. Lu, J. Rao, K. Chen, X. Guo, Y. Zhang, B. Sun, C. Yang, and J. Yang
1. [Behind the magic, merlim: Multi-modal evaluation benchmark for large image-language models](), arXiv 2023, \
A. Villa, J. C. L. Alcazar, A. Soto, and B. Ghanem
1. [Mme: A comprehensive evaluation benchmark for multimodal large language models](https://arxiv.org/abs/2306.13394), arXiv 2023, \
Chaoyou Fu, Peixian Chen, Yunhang Shen, Yulei Qin, Mengdan Zhang, Xu Lin, Jinrui Yang, Xiawu Zheng, Ke Li, Xing Sun, Yunsheng Wu, Rongrong Ji
1. [Hallusionbench: An advanced diagnostic suite for entangled language hallucination & visual illusion in large vision-language models](), arXiv 2023, \
T. Guan, F. Liu, X. Wu, R. Xian, Z. Li, X. Liu, X. Wang, L. Chen, F. Huang, Y. Yacoob et al
1. [Evaluation and mitigation of agnosia in multimodal large language models](), arXiv 2023, \
Jiaying Lu, Jinmeng Rao, Kezhen Chen, et al.
1. [Halle-switch: Rethinking and controlling object existence hallucinations in large vision language models for detailed caption](), arXiv 2023, \
Bohan Zhai, Shijia Yang, Xiangchen Zhao, et al.
1. [Faithscore: Evaluating hallucinations in large visionlanguage models](), arXiv 2023, \
Liqiang Jing, Ruosen Li, Yunmo Chen, et al.
1. [Mitigating hallucination in large multi-modal models via robust instruction tuning](), arXiv 2023, \
Fuxiao Liu, Kevin Lin, Linjie Li, et al.
1. [Aligning large multimodal models with factually augmented rlhf](), arXiv 2023, \
Zhiqing Sun, Sheng Shen, Shengcao Cao, et al.
1. [Detecting and preventing hallucinations in large vision language models](), arXiv 2023, \
Anisha Gunjal, Jihan Yin, and Erhan Bas
1. [Instructblip: Towards general-purpose visionlanguage models with instruction tuning](), arXiv 2023, \
Wenliang Dai, Junnan Li, Dongxu Li, et al.
1. [Evaluation and analysis of hallucination in large vision-language models](), arXiv 2023, \
Junyang Wang, Yiyang Zhou, Guohai Xu, et al.
1. [A-okvqa: A benchmark for visual question answering using world knowledge](https://arxiv.org/abs/2206.01718), ECCV 2022, \
   Dustin Schwenk, Apoorv Khandelwal, Christopher Clark, Kenneth Marino, Roozbeh Mottaghi
1. [(CHAIR) Object hallucination in image captioning](), EMNLP 2018, \
Anna Rohrbach, Lisa Anne Hendricks, Kaylee Burns, et al.

## [3. Applications](#content)
1. [Aerial Mirage: Unmasking Hallucinations in Large Vision Language Models](https://ieeexplore.ieee.org/abstract/document/10943891), WACV 2025, \
Debolena Basak, Soham Bhatt, Sahith Kanduri, Maunendra Sankar Desarkar
