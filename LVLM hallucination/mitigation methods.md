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
1. [ClearSight: Visual Signal Enhancement for Object Hallucination Mitigation in Multimodal Large Language Models](https://arxiv.org/abs/2503.13107), CVPR 2025, \
Hao Yin, Guangzong Si, Zilei Wang
1. [Octopus: Alleviating Hallucination via Dynamic Contrastive Decoding](https://arxiv.org/abs/2503.00361), CVPR 2025, \
Wei Suo, Lijun Zhang, Mengyang Sun, Lin Yuanbo Wu, Peng Wang, Yanning Zhang
1. [Mitigating Object Hallucinations in Large Vision-Language Models with Assembly of Global and Local Attention](https://arxiv.org/abs/2406.12718), CVPR 2025, \
Wenbin An, Feng Tian, Sicong Leng, Jiahao Nie, Haonan Lin, QianYing Wang, Ping Chen, Xiaoqin Zhang, Shijian Lu
1. [Devils in Middle Layers of Large Vision-Language Models: Interpreting, Detecting and Mitigating Object Hallucinations via Attention Lens](https://arxiv.org/abs/2411.16724), CVPR 2025, \
Zhangqi Jiang, Junkai Chen, Beier Zhu, Tingjin Luo, Yankun Shen, Xu Yang
1. [ICT: Image-Object Cross-Level Trusted Intervention for Mitigating Object Hallucination in Large Vision-Language Models](https://arxiv.org/abs/2411.15268), CVPR 2025, \
Junzhe Chen, Tianshu Zhang, Shiyu Huang, Yuwei Niu, Linfeng Zhang, Lijie Wen, Xuming Hu
1. [Seeing Far and Clearly: Mitigating Hallucinations in MLLMs with Attention Causal Decoding](https://arxiv.org/abs/2505.16652), CVPR 2025, \
Feilong Tang, Chengzhi Liu, Zhongxing Xu, Ming Hu, Zelin Peng, Zhiwei Yang, Jionglong Su, Minquan Lin, Yifan Peng, Xuelian Cheng, Imran Razzak, Zongyuan Ge
1. [IBD: Alleviating Hallucinations in Large Vision-Language Models via Image-Biased Decoding](https://openaccess.thecvf.com/content/CVPR2025W/TMM-OpenWorld/html/Zhu_IBD_Alleviating_Hallucinations_in_Large_Vision-Language_Models_via_Image-Biased_Decoding_CVPRW_2025_paper.html), CVPR Workshop 2025, \
Lanyun Zhu, Deyi Ji, Tianrun Chen, Peng Xu, Jieping Ye, Jun Liu
1. [Fact: Teaching mllms with faithful, concise and transferable rationales](https://arxiv.org/abs/2404.11129), ACM MM 2024, \
Minghe Gao, Shuang Chen, Liang Pang, Yuan Yao, Jisheng Dang, Wenqiao Zhang, Juncheng Li, Siliang Tang, Yueting Zhuang, Tat-Seng Chua
1. [Cantor: Inspiring multimodal chainof-thought of mllm](https://arxiv.org/abs/2404.16033), ACM MM 2024, \
Timin Gao, Peixian Chen, Mengdan Zhang, Chaoyou Fu, Yunhang Shen, Yan Zhang, Shengchuan Zhang, Xiawu Zheng, Xing Sun, Liujuan Cao, Rongrong Ji
1. [Opera: Alleviating hallucination in multimodal large language models via over-trust penalty and retrospectionallocation](https://arxiv.org/abs/2311.17911), CVPR 2024, \
Qidong Huang, Xiaoyi Dong, Pan Zhang, Bin Wang, Conghui He, Jiaqi Wang, Dahua Lin, Weiming Zhang, Nenghai Yu
1. [Pensieve: Retrospectthen-compare mitigates visual hallucination](https://arxiv.org/abs/2403.14401), arXiv 2024, \
Dingchen Yang, Bowen Cao, Guang Chen, Changjun Jiang
1. [Efuf: Efficient fine-grained unlearning framework for mitigating hallucinations in multimodal large language models](https://arxiv.org/abs/2402.09801), EMNLP 2024, \
Shangyu Xing, Fei Zhao, Zhen Wu, Tuo An, Weihao Chen, Chunhui Li, Jianbing Zhang, Xinyu Dai
1. [HALC: Object Hallucination Reduction via Adaptive Focal-Contrast Decoding](https://arxiv.org/abs/2403.00425), ICML 2024, \
Zhaorun Chen, Zhuokai Zhao, Hongyin Luo, Huaxiu Yao, Bo Li, Jiawei Zhou
1. [CODE: Contrasting Self-generated Description to Combat Hallucination in Large Multi-modal Models](https://arxiv.org/abs/2406.01920), NeurIPS 2024, \
Junho Kim, Hyunjun Kim, Yeonju Kim, Yong Man Ro

### [1.2 Modality Align](#content)
1. [See What You Are Told: Visual Attention Sink in Large Multimodal Models](https://arxiv.org/abs/2503.03321), ICLR 2025, \
Seil Kang, Jinyeong Kim, Junhyeok Kim, Seong Jae Hwang
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
1. [Mitigating Object Hallucination via Concentric Causal Attention](https://arxiv.org/abs/2410.15926), NeurIPS 2024, \
Yun Xing, Yiheng Li, Ivan Laptev, Shijian Lu

### [1.4 Post Hoc Remediation](#content)
1. [Volcano: mitigating multimodal hallucination through self-feedback guided revision](https://arxiv.org/abs/2311.07362), NAACL 2024, \
Seongyun Lee, Sue Hyun Park, Yongrae Jo, Minjoon Seo
1. [Woodpecker: Hallucination correction for multimodal large language models](https://arxiv.org/abs/2310.16045), arXiv 2023, \
Shukang Yin, Chaoyou Fu, Sirui Zhao, Tong Xu, Hao Wang, Dianbo Sui, Yunhang Shen, Ke Li, Xing Sun, Enhong Chen
1. [Analyzing and mitigating object hallucination in large visionlanguage models](https://arxiv.org/abs/2310.00754), arXiv 2023, \
Yiyang Zhou, Chenhang Cui, Jaehong Yoon, Linjun Zhang, Zhun Deng, Chelsea Finn, Mohit Bansal, Huaxiu Yao

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
1. [VASparse: Towards Efficient Visual Hallucination Mitigation via Visual-Aware Token Sparsification](https://arxiv.org/abs/2501.06553), CVPR 2025, \
Xianwei Zhuang, Zhihong Zhu, Yuxin Xie, Liming Liang, Yuexian Zou
1. [See What You Are Told: Visual Attention Sink in Large Multimodal Models](https://arxiv.org/abs/2503.03321), arXiv 2025, \
Seil Kang, Jinyeong Kim, Junhyeok Kim, Seong Jae Hwang
1. [Don't Miss the Forest for the Trees: Attentional Vision Calibration for Large Vision Language Models](https://arxiv.org/abs/2405.17820), ACL Findings 2025, \
Sangmin Woo, Donguk Kim, Jaehyuk Jang, Yubin Choi, Changick Kim

### [1.8 Model Weights Editing](#content)
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
1. [CIEM: Contrastive Instruction Evaluation Method for Better Instruction Tuning](https://arxiv.org/abs/2309.02301), NeurIPS 2023 Workshop, \
   Hongyu Hu, Jiyuan Zhang, Minyi Zhao, Zhenbang Sun
1. [Mllms-augmented visual-language representation learning](), arXiv 2023, \
Y. Liu, K. Wang, W. Shao, P. Luo, Y. Qiao, M. Z. Shou, K. Zhang
1. [Mitigating hallucination in large multi-modal models via robust instruction tuning](), ICLR 2023, \
F. Liu, K. Lin, L. Li, J. Wang, Y. Yacoob, and L. Wang
1. [Hallucidoctor: Mitigating hallucinatory toxicity in visual instruction data](), arXiv 2023, \
Q. Yu, J. Li, L. Wei, L. Pang, W. Ye, B. Qin, S. Tang, Q. Tian, and Y. Zhuang



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
