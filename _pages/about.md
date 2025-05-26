---
permalink: /
title: ""
excerpt: ""
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}
{% assign url = gsDataBaseUrl | append: "google-scholar-stats/gs_data_shieldsio.json" %}

<span class='anchor' id='about-me'></span>

## ZhiweiXu(许志伟)

`许志伟`博士为*IEEE*、*CCF*、*ACM*、*CAAI*、*CIE*、*CAA*、*IEEE-SMC*、*IEEE-CIS*、*ACM-SIGEVO*会员、*中国人工智能学会青年工作委员会委员*、*中国仿真学会智能优化与调度专委会委员* 。CSDN人工智能领域优质创作者，博客专家。获得2019年硕士研究生国家奖学金与2021年，2022年博士研究生国家奖学金。近期在多任务多目标优化，约束多目标优化和高维多目标优化方面取得了一系列新进展新突破。参与国家自然科学基金两项，主持省自然科学基金青年项目一项，发表专利三项（已授权）。多项研究发表在国际顶级期刊*IEEE Transaction on Evolutionary Computation*， *IEEE Transaction on Cybernetics*，*IEEE Transactions on Intelligent Transportation Systems*，*Information Sciences*，中国科学：信息科学以及Applied Soft Computing上。获2021年与2022年武汉计算机软件工程学会年会暨学术研讨会优秀研究生，2021年CCF武汉优秀博士生学术风采展示论坛一等奖。为国际顶级期刊*IEEE Transaction on Evolutionary Computation*、*IEEE Transactions on Systems Man Cybernetics-Systems*、 *Information Sciences*， *Applied Soft Computing*等审稿人。为*IEEE Congress on Evolutionary Computation (CEC)*，*IEEE Symposium Series On Computational Intelligence （SSCI）*，*International Conference on Bio-inspired Computing: Theories and Applications （BIC-TA）* 等国际会议审稿人。担任The 19th International Conference on Bio-inspired Computing: Theories and Applications (BIC-TA 2024)的Session Chair，2025亚洲人工智能技术大会（ACAIT2025）程序委员会成员(PC) <a href='https://scholar.google.com/citations?user=_Lkioz8AAAAJ&hl'><img src="https://img.shields.io/endpoint?url={{ url | url_encode }}&logo=Google%20Scholar&labelColor=f6f6f6&color=9cf&style=flat&label=引用"></a>

研究兴趣包括：
- 演化计算
- 多目标优化（超多目标、约束、多任务、多模态等）
- DNA计算、编码、自组装
- RNA二级结构预测
- 多目标路径规划

<span class='anchor' id='-Hl'></span>

## Highlight

<span class='anchor' id='-lwzl'></span>
---

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">TITS 2025</div><img src="{{ site.baseurl }}/images/MMOEA-CDP.svg" alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

- `Zhiwei Xu(许志伟)` \*, Kai Zhang, Javier Del Ser, Miqing Li, Xin Xu, Juanjuan He, Ni Wu.Multi-Objective Optimization for Multimodal Multi-Objective Multi-Point Shortest Path Problem Considering Unforeseeable Road Eventualities. *IEEE Transactions on Intelligent Transportation Systems* , pp. 1–19, 2025 (JCR: Q1; IF: 7.9)  
- In this paper, multi-objective multi-point shortest path planning problem is modeled as a multimodal multi-objective optimization problem with necessary points constrains. A multimodal multi-objective evolutionary algorithm using constraint dominance principle-based path comparison strategy and path similarity-based multimodal solutions selection strategy is proposed to address this problem.  
[[Link]](https://ieeexplore.ieee.org/document/10959009/) [[Download]](/PDF/MMOEA-CDP.pdf) [[Code]](https://github.com/JaywayXu/MMOEA-CDP)

</div>
</div>


<div class='paper-box'><div class='paper-box-image'><div><div class="badge">TCYB 2021</div>
<img src="{{ site.baseurl }}/images/MaOES.svg" alt="sym" width="100%">
</div></div>
<div class='paper-box-text' markdown="1">

- Kai Zhang, `Zhiwei Xu(许志伟)`, Shengli Xie, and Gary G. Yen\*. Evolution Strategy-Based Many-Objective Evolutionary Algorithm Through Vector Equilibrium. *IEEE Transactions on Cybernetics* , vol. 51, no. 11, pp. 5455–5467, Nov. 2021. (JCR:Q1; IF:11.8)
- In this paper, we propose a novel evolution strategy for solving many-objective optimization problems, named MaOES.
- The proposed algorithm uses mutation and selection for individual self-adaptation. The Precision Controllable Mutation operator is designed for individuals to explore and exploit the decision space efficiently. The Maximum Extension Distance strategy is tailored to guide the individuals to keep uniform distance among particles in the population and to facilitate the extension to approximate the entire Pareto front automatically.  
[[Link]](https://ieeexplore.ieee.org/document/8955947/) [[Download]](/PDF/MaOES.pdf)[[Code]](https://github.com/MaOEA/MaOES)

</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">TEVC 2024</div><img src="{{ site.baseurl }}/images/CMOES.svg" alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

- Kai Zhang, `Zhiwei Xu(许志伟)`, Gary G. Yen\*, Ling Zhang. Two-Stage Multi-Objective Evolution Strategy for Constrained Multi-Objective Optimization. *IEEE Transactions on Evolutionary Computation* , vol. 28, no. 1, pp. 17–31, Feb. 2024 (JCR:Q1; IF:14.3)
- In this paper, a novel parameter-less constraint handling technique is proposed, which divides the whole population into three mutually exclusive subsets dynamically, including FNDS, the subset dominated by FNDS, and the subset not dominated by FNDS. According to the proposed division of labor, it is not necessary to balance the convergence and constrained satisfaction in each subset.
- Secondly, to avoid been trapped into local optima, the proposed algorithm adopts a two-stage strategy to solve CMOPs.
- In the first stage, the proposed algorithm focuses solely on converging toward the unconstrained PF without considering the constrained satisfaction.
- In the second stage, the FNDS constraint handling technique is adopted to guide the population converging towards PF effectively.  
[[Link]](https://ieeexplore.ieee.org/document/9869698) [[Download]](/PDF/CMOES.pdf)[[Code]](https://github.com/MaOEA/CMOES)

</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">INS 2022</div>
<img src="{{ site.baseurl }}/images/CT-EMT-MOES.svg" alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

- `Zhiwei Xu (许志伟)`, Xiaoming Liu, Kai Zhang\*, and Juanjuan He. Cultural transmission based multi-objective evolution strategy for evolutionary multitasking. *Information Sciences* , vol. 582, pp. 215–242, Jan. 2022. (JCR:Q1; IF：8.1)

- In this paper, a novel multi-objective evolution strategy was proposed for solving multitask optimization problems. Inspired by modern cultural evolution theory, elite-guided variation strategy, and horizontal cultural transmission strategy, two evolutionary operators were proposed.
- To make full use of the two transfer strategies, an adaptive information transfer strategy is proposed to adjust the probability of the information transfer adaptively according to the dominant relationship between the offspring and its parent to reasonably allocate the evolutionary resources.  
[[Link]](https://www.sciencedirect.com/science/article/pii/S0020025521009282) [[Download]](/PDF/CT_EMT_MOES.pdf)[[Code]](https://github.com/Asurada2015/CT-EMT-MOES)

</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">INS 2022</div><img src="{{ site.baseurl }}/images/EMT-MOMIEA.svg" alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

- `Zhiwei Xu (许志伟)`, Kai Zhang, Juanjuan He\*, and Xiaoming Liu. A novel membrane-inspired evolutionary framework for multi-objective multi-task optimization problems. *Information Sciences* , vol. 596, pp. 236–263, Jun. 2022. (JCR:Q1; IF：8.1)  

- In this paper, a multi-objective multi-task evolutionary framework based on membrane system (EMT-MOMIEA) is proposed to solve the multi-objective multi-task optimization (MOMTO) problems. 
- Inspired by the binding process of information molecules and receptors during information exchange between cells, the information molecule concentration vector (IMCV) concept is proposed. The IMCV can dynamically adjust the information transfer probability and reduce negative information transfer.  
[[Link]](https://www.sciencedirect.com/science/article/pii/S002002552200216X) [[Download]](/PDF/EMT-MOMIEA.pdf)
</div>
</div>



<div class='paper-box'><div class='paper-box-image'><div><div class="badge">ASOC 2021</div>
<img src="{{ site.baseurl }}/images/MOMFIA.svg" alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

- `Zhiwei Xu (许志伟)` and Kai Zhang\*. Multiobjective multifactorial immune algorithm for multiobjective multitask optimization problems. *Applied Soft Computing* , vol. 107, p. 107399, Aug. 2021. (JCR:Q1; IF：8.7)

- In this paper, a novel multiobjective multifactorial immune algorithm (MOMFIA) is proposed to solve MOMTO and MOMaTO problems. The proposed MOMFIA applied a novel multipopulation framework and a novel information transfer method based on the dimensional information of solutions (DIS). The proposed multi-population framework can evenly distribute individuals to different subpopulations, each of which maintains an independent task module, can evolve independently, but is also equipped to transfer their knowledge when necessary.  
[[Link]](https://www.sciencedirect.com/science/article/pii/S1568494621003227) [[Download]](/PDF/MOMFIA.pdf)
</div>
</div>


<div class='paper-box'><div class='paper-box-image'><div><div class="badge">ASOC 2024</div>
<img src="{{ site.baseurl }}/images/HMOMFMA.svg" alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

- `Zhiwei Xu (许志伟)`\*, Jia feng Xu, Kai Zhang, Xin Xu, Juanjuan He, Ni Wu, Decision Variable Classification based Multi-objective Multifactorial Memetic Algorithm for Multi-objective Multi-task Optimization Problem. *Applied Soft Computing* , vol. 152, p. 111232, Feb. 2024. (JCR:Q1; IF：8.7)

- In this paper, a novel hybrid multi-objective multifactorial memetic algorithm is proposed to solve MOMTO problems. The proposed variable classification method will classify decision variables into convergence-related and diversity-related decision variables. Only the same type of decision variables in the source and target tasks can transfer information to avoid negative transfer. 
- Different evolutionary operators are adopted according to the characteristics of decision variables during individual recombination. 
- In addition, the proposed algorithm hybridizes the immune algorithm as the global evolutionary operator and the evolutionary gradient search algorithm as the local search operator into the multifactorial framework to enhance the searching ability.  
[[Link]](https://www.sciencedirect.com/science/article/pii/S1568494624000061) [[Download]](/PDF/HMOMFMA.pdf)
</div>
</div>
