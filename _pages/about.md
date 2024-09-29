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

I am currently a lecturer at the School of Computer Science and Technology, Wuhan University of Science and Technology, China. I am a member of the **Institute of Electrical and Electronics Engineers (IEEE)**, **China Computer Federation (CCF)**, **Association for Computing Machinery (ACM)**, **Chinese Association for Artificial Intelligence (CAAI)**, **IEEE Systems, Man, and Cybernetics Society (IEEE-SMC)**, **IEEE Computational Intelligence Society (IEEE-CIS)**, and **ACM Special Interest Group on Genetic and Evolutionary Computation (ACM-SIGEVO)**. Recognized as a high-quality content creator and blogging expert in the field of artificial intelligence on CSDN, I have actively contributed to the academic community.

I was awarded the National Scholarship for Master's students in 2019 and the National Scholarship for Doctoral students in 2021 and 2022 by the Ministry of Education of China. Recently, I have achieved significant advancements and breakthroughs in multi-task multi-objective optimization, constrained multi-objective optimization, and high-dimensional multi-objective optimization.

I have participated in two projects funded by the National Natural Science Foundation of China and led a youth project funded by the Provincial Natural Science Foundation. I hold three granted patents. My research findings have been published in top-tier international journals such as **IEEE Transactions on Evolutionary Computation**, **IEEE Transactions on Cybernetics**, **Information Sciences**, **Science China: Information Sciences**, and **Applied Soft Computing**.

I was recognized as an Excellent Graduate Student at the Annual Meeting and Academic Seminar of the Wuhan Computer Software Engineering Society in both 2021 and 2022, and won the First Prize at the 2021 CCF Wuhan Excellent Doctoral Student Academic Showcase Forum. I serve as a reviewer for leading international journals including **IEEE Transactions on Evolutionary Computation**, **IEEE Transactions on Systems, Man, and Cybernetics: Systems**, **Information Sciences**, and **Applied Soft Computing**. Additionally, I am a reviewer for international conferences such as the **IEEE Congress on Evolutionary Computation (CEC)**, **IEEE Symposium Series on Computational Intelligence (SSCI)**, and the **International Conference on Bio-inspired Computing: Theories and Applications (BIC-TA)**. <a href='https://scholar.google.com/citations?user=_Lkioz8AAAAJ&hl'><img src="https://img.shields.io/endpoint?url={{ url | url_encode }}&logo=Google%20Scholar&labelColor=f6f6f6&color=9cf&style=flat&label=引用"></a>

My research interests include:

- Evolutionary Computation
- Multi-objective Optimization (many-objective, constrained, multi-task, large-scale, etc.)
- DNA Computing, Encoding, and Self-Assembly
- RNA Structure Prediction
- Multi-objective Path Planning

<span class='anchor' id='-Hl'></span>

## Highlight

<span class='anchor' id='-lwzl'></span>

---
<div class='paper-box'><div class='paper-box-image'><div><div class="badge">TCYB 2021</div><img src='images/MaOES.svg' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

- Kai Zhang, `Zhiwei Xu(许志伟)`, Shengli Xie, and Gary G. Yen\*. Evolution Strategy-Based Many-Objective Evolutionary Algorithm Through Vector Equilibrium. *IEEE Transactions on Cybernetics* , vol. 51, no. 11, pp. 5455–5467, Nov. 2021. (JCR:Q1; IF:11.8)
- In this paper, we propose a novel evolution strategy for solving many-objective optimization problems, named MaOES.
- The proposed algorithm uses mutation and selection for individual self-adaptation. The Precision Controllable Mutation operator is designed for individuals to explore and exploit the decision space efficiently. The Maximum Extension Distance strategy is tailored to guide the individuals to keep uniform distance among particles in the population and to facilitate the extension to approximate the entire Pareto front automatically.  
[[Link]](https://ieeexplore.ieee.org/document/8955947/) [[Download]](/PDF/MaOES.pdf)[[Code]](https://github.com/MaOEA/MaOES)

</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">TEVC 2024</div><img src='images/CMOES.svg' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

- Kai Zhang, `Zhiwei Xu(许志伟)`, Gary G. Yen\*, Ling Zhang. Two-Stage Multi-Objective Evolution Strategy for Constrained Multi-Objective Optimization. *IEEE Transactions on Evolutionary Computation* , vol. 28, no. 1, pp. 17–31, Feb. 2024 (JCR:Q1; IF:14.3)
- In this paper, a novel parameter-less constraint handling technique is proposed, which divides the whole population into three mutually exclusive subsets dynamically, including FNDS, the subset dominated by FNDS, and the subset not dominated by FNDS. According to the proposed division of labor, it is not necessary to balance the convergence and constrained satisfaction in each subset.
- Secondly, to avoid been trapped into local optima, the proposed algorithm adopts a two-stage strategy to solve CMOPs.
- In the first stage, the proposed algorithm focuses solely on converging toward the unconstrained PF without considering the constrained satisfaction.
- In the second stage, the FNDS constraint handling technique is adopted to guide the population converging towards PF effectively.  
[[Link]](https://ieeexplore.ieee.org/document/9869698) [[Download]](/PDF/CMOES.pdf)[[Code]](https://github.com/MaOEA/CMOES)

</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">INS 2022</div><img src='images/CT-EMT-MOES.svg' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

- `Zhiwei Xu (许志伟)`, Xiaoming Liu, Kai Zhang\*, and Juanjuan He. Cultural transmission based multi-objective evolution strategy for evolutionary multitasking. *Information Sciences* , vol. 582, pp. 215–242, Jan. 2022. (JCR:Q1; IF：8.1)

- In this paper, a novel multi-objective evolution strategy was proposed for solving multitask optimization problems. Inspired by modern cultural evolution theory, elite-guided variation strategy, and horizontal cultural transmission strategy, two evolutionary operators were proposed.
- To make full use of the two transfer strategies, an adaptive information transfer strategy is proposed to adjust the probability of the information transfer adaptively according to the dominant relationship between the offspring and its parent to reasonably allocate the evolutionary resources.  
[[Link]](https://www.sciencedirect.com/science/article/pii/S0020025521009282) [[Download]](/PDF/CT_EMT_MOES.pdf)[[Code]](https://github.com/Asurada2015/CT-EMT-MOES)

</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">INS 2022</div><img src='images/EMT-MOMIEA.svg' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

- `Zhiwei Xu (许志伟)`, Kai Zhang, Juanjuan He\*, and Xiaoming Liu. A novel membrane-inspired evolutionary framework for multi-objective multi-task optimization problems. *Information Sciences* , vol. 596, pp. 236–263, Jun. 2022. (JCR:Q1; IF：8.1)  

- In this paper, a multi-objective multi-task evolutionary framework based on membrane system (EMT-MOMIEA) is proposed to solve the multi-objective multi-task optimization (MOMTO) problems. 
- Inspired by the binding process of information molecules and receptors during information exchange between cells, the information molecule concentration vector (IMCV) concept is proposed. The IMCV can dynamically adjust the information transfer probability and reduce negative information transfer.  
[[Link]](https://www.sciencedirect.com/science/article/pii/S002002552200216X) [[Download]](/PDF/EMT-MOMIEA.pdf)
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">ASOC 2021</div><img src='images/MOMFIA.svg' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

- `Zhiwei Xu (许志伟)` and Kai Zhang\*. Multiobjective multifactorial immune algorithm for multiobjective multitask optimization problems. *Applied Soft Computing* , vol. 107, p. 107399, Aug. 2021. (JCR:Q1; IF：8.7)

- In this paper, a novel multiobjective multifactorial immune algorithm (MOMFIA) is proposed to solve MOMTO and MOMaTO problems. The proposed MOMFIA applied a novel multipopulation framework and a novel information transfer method based on the dimensional information of solutions (DIS). The proposed multi-population framework can evenly distribute individuals to different subpopulations, each of which maintains an independent task module, can evolve independently, but is also equipped to transfer their knowledge when necessary.  
[[Link]](https://www.sciencedirect.com/science/article/pii/S1568494621003227) [[Download]](/PDF/MOMFIA.pdf)
</div>
</div>

<div class='paper-box'><div class='paper-box-image'><div><div class="badge">ASOC 2024</div><img src='images/HMOMFMA.svg' alt="sym" width="100%"></div></div>
<div class='paper-box-text' markdown="1">

- `Zhiwei Xu (许志伟)`\*, Jia feng Xu, Kai Zhang, Xin Xu, Juanjuan He, Ni Wu, Decision Variable Classification based Multi-objective Multifactorial Memetic Algorithm for Multi-objective Multi-task Optimization Problem. *Applied Soft Computing* , vol. 152, p. 111232, Feb. 2024. (JCR:Q1; IF：8.7)

- In this paper, a novel hybrid multi-objective multifactorial memetic algorithm is proposed to solve MOMTO problems. The proposed variable classification method will classify decision variables into convergence-related and diversity-related decision variables. Only the same type of decision variables in the source and target tasks can transfer information to avoid negative transfer. 
- Different evolutionary operators are adopted according to the characteristics of decision variables during individual recombination. 
- In addition, the proposed algorithm hybridizes the immune algorithm as the global evolutionary operator and the evolutionary gradient search algorithm as the local search operator into the multifactorial framework to enhance the searching ability.  
[[Link]](https://www.sciencedirect.com/science/article/pii/S1568494624000061) [[Download]](/PDF/HMOMFMA.pdf)
</div>
</div>

## Publication

<span class='anchor' id='-Pub'></span>

---

- `Zhiwei Xu (许志伟)`, Xiaoming Liu, Kai Zhang\*, and Juanjuan He. Cultural transmission based multi-objective evolution strategy for evolutionary multitasking. *Information Sciences* , vol. 582, pp. 215–242, Jan. 2022. (JCR:Q1; IF：8.1)  
[[Link]](https://www.sciencedirect.com/science/article/pii/S0020025521009282) [[Download]](/PDF/CT_EMT_MOES.pdf)
- `Zhiwei Xu (许志伟)`, Kai Zhang, Juanjuan He\*, and Xiaoming Liu. A novel membrane-inspired evolutionary framework for multi-objective multi-task optimization problems. *Information Sciences* , vol. 596, pp. 236–263, Jun. 2022. (JCR:Q1; IF：8.1)  
[[Link]](https://www.sciencedirect.com/science/article/pii/S002002552200216X) [[Download]](/PDF/EMT-MOMIEA.pdf)
- `Zhiwei Xu\* (许志伟)`, Jia feng Xu, Kai Zhang, Xin Xu, Juanjuan He, Ni Wu, Decision Variable Classification based Multi-objective Multifactorial Memetic Algorithm for Multi-objective Multi-task Optimization Problem. *Applied Soft Computing* , vol. 152, p. 111232, Feb. 2024. (JCR:Q1; IF：8.7)  
[[Link]](https://www.sciencedirect.com/science/article/pii/S1568494624000061) [[Download]](/PDF/HMOMFMA.pdf)
- `Zhiwei Xu (许志伟)` and Kai Zhang\*. Multiobjective multifactorial immune algorithm for multiobjective multitask optimization problems. *Applied Soft Computing* , vol. 107, p. 107399, Aug. 2021. (JCR:Q1; IF：8.7)  
[[Link]](https://www.sciencedirect.com/science/article/pii/S1568494621003227) [[Download]](/PDF/MOMFIA.pdf)
- Kai Zhang, `Zhiwei Xu(许志伟)`, Shengli Xie, and Gary G. Yen\*. Evolution Strategy-Based Many-Objective Evolutionary Algorithm Through Vector Equilibrium. *IEEE Transactions on Cybernetics* , vol. 51, no. 11, pp. 5455–5467, Nov. 2021. (JCR:Q1; IF:11.8)  
[[Link]](https://ieeexplore.ieee.org/document/8955947/) [[Download]](/PDF/MaOES.pdf)[[Code]](https://github.com/MaOEA/MaOES)
- Kai Zhang, `Zhiwei Xu(许志伟)`, Gary G. Yen\*, Ling Zhang. Two-Stage Multi-Objective Evolution Strategy for Constrained Multi-Objective Optimization. *IEEE Transactions on Evolutionary Computation* , vol. 28, no. 1, pp. 17–31, Feb. 2024 (JCR:Q1; IF:14.3)  
[[Link]](https://ieeexplore.ieee.org/document/9869698) [[Download]](/PDF/CMOES.pdf)[[Code]](https://github.com/MaOEA/CMOES)
- Kai Zhang, Chaonan Shen, Gary G. Yen\*, `Zhiwei Xu(许志伟)` , and Juanjuan He. Two-Stage Double Niched Evolution Strategy for Multimodal Multiobjective Optimization. *IEEE Transactions on Evolutionary Computation* , vol. 25, no. 4, pp. 754–768, Aug. 2021. (JCR:Q1; IF:14.3)  
[[Link]](https://ieeexplore.ieee.org/document/9372341) [[Download]](/PDF/DN-MMOES.pdf)[[Code]](https://github.com/MaOEA/DN-MMOES)
- Kai Zhang, Bin Chen, `Zhiwei Xu(许志伟)`\*. A Multiobjective Evolution Strategy Algorithm for DNA Sequence Design. *Journal of Electronics & Information Technology* , 2020, 42(6): 1365-1373.  
[[Link]](https://jeit.ac.cn/cn/article/doi/10.11999/JEIT190869) [[Download]](/PDF/MOES_DNA.pdf)
- `Zhiwei Xu(许志伟)`, Kai Zhang\*, Xin Xu, and Juanjuan He. A Fireworks Algorithm Based on Transfer Spark for Evolutionary Multitasking. *Frontiers in Neurorobotics* , vol. 13, p. 109, Jan. 2020.  
[[Link]](https://www.frontiersin.org/articles/10.3389/fnbot.2019.00109) [[Download]](/PDF/MTO-FWA.pdf)
- `Zhiwei Xu(许志伟)`, Xiaoming Liu, and Kai Zhang\*. Mechanical Properties Prediction for Hot Rolled Alloy Steel Using Convolutional Neural Network. *IEEE Access* , vol. 7, pp. 47068–47078, 2019.  
[[Link]](https://ieeexplore.ieee.org/document/8682144) [[Download]](/PDF/ACCESS.pdf)
- Haozhi Zhao, `Zhiwei Xu(许志伟)`\*, and K Zhang\*. Reference Point Based Multi-objective Evolutionary Algorithm for DNA Sequence Design. *International Conference on Bio-Inspired Computing: Theories and Applications*, 2019, pp. 178–188.  
[[Link]](http://link.springer.com/10.1007/978-981-15-3415-7_14) [[Download]](/PDF/BICTA_DNA.pdf)
- Hao Xu, `Zhiwei Xu(许志伟)`\*, and Kai Zhang\*. Mechanical Properties Prediction for Hot Roll Steel Using Convolutional Neural Network. *International Conference on Bio-Inspired Computing: Theories and Applications*, 2019, pp. 565–575.  
[[Link]](http://link.springer.com/10.1007/978-981-15-3415-7_47) [[Download]](/PDF/BICTA_CNN.pdf)
- Kai Zhang\*, Fang Liu, Chaonan Shen, and `Zhiwei Xu(许志伟)`. Multi-population Evolutionary Algorithm for Multimodal Multobjective Optimization. *International Conference on Intelligent Autonomous Systems*, 2021, pp. 199–204.  
[[Link]](https://ieeexplore.ieee.org/document/9527712) [[Download]](/PDF/ICoIAS.pdf)
- Fan Li, Kai Zhang\*, Chaonan Shen, `Zhiwei Xu(许志伟)`. Solving Multimodal Multi-Objective Problems with Local Pareto Front using a Population Clustering Mechanism. *International Conference on Machine Learning and Soft Computing*, 2023, pp. 34-39.  
[[Link]](https://dl.acm.org/doi/10.1145/3583788.3583793) [[Download]](/PDF/ICMLSC.pdf)
