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


<!-- ================= Research Highlights Carousel Start ================= -->

<style>
.research-carousel-wrapper {
  width: 100%;
  margin: 28px auto 42px auto;
  position: relative;
}

.research-carousel {
  position: relative;
  width: 100%;
  height: 430px;
  overflow: hidden;
  border-radius: 18px;
  box-shadow: 0 12px 32px rgba(0, 0, 0, 0.16);
  background: #f5f5f5;
  -webkit-user-select: none;
  user-select: none;
  touch-action: pan-y;
}

.research-carousel-track {
  display: flex;
  height: 100%;
  transform: translate3d(0, 0, 0);
  transition: transform 1050ms cubic-bezier(0.22, 0.61, 0.36, 1);
  will-change: transform;
  backface-visibility: hidden;
}

.research-carousel-slide {
  min-width: 100%;
  height: 100%;
  position: relative;
  overflow: hidden;
  transform: translateZ(0);
  backface-visibility: hidden;
}

.research-carousel-slide img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
  display: block;
  pointer-events: none;
  transform: scale(1.035);
  transition:
    transform 1600ms cubic-bezier(0.22, 0.61, 0.36, 1),
    opacity 900ms ease;
  will-change: transform;
  backface-visibility: hidden;
}

.research-carousel-slide.active img {
  transform: scale(1);
}

.research-carousel-caption {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  padding: 26px 34px;
  color: #fff;
  background: linear-gradient(
    to top,
    rgba(0, 0, 0, 0.72),
    rgba(0, 0, 0, 0.38),
    rgba(0, 0, 0, 0)
  );
  opacity: 0;
  transform: translate3d(0, 18px, 0);
  transition:
    opacity 850ms ease 220ms,
    transform 850ms cubic-bezier(0.22, 0.61, 0.36, 1) 220ms;
  will-change: opacity, transform;
}

.research-carousel-slide.active .research-carousel-caption {
  opacity: 1;
  transform: translate3d(0, 0, 0);
}

.research-carousel-caption h3 {
  margin: 0 0 10px 0;
  font-size: 24px;
  font-weight: 700;
  line-height: 1.3;
  color: #fff;
}

.research-carousel-caption p {
  margin: 0;
  font-size: 16px;
  line-height: 1.65;
  max-width: 850px;
  color: #fff;
  font-weight: 600;
}

.research-carousel-btn {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: 42px;
  height: 42px;
  border: none;
  border-radius: 50%;
  background: rgba(0, 0, 0, 0.42);
  color: #fff;
  font-size: 24px;
  cursor: pointer;
  z-index: 5;
  transition:
    background 250ms ease,
    transform 250ms ease,
    opacity 250ms ease;
}

.research-carousel-btn:hover,
.research-carousel-btn:focus {
  background: rgba(0, 0, 0, 0.68);
  outline: none;
}

.research-carousel-btn.prev {
  left: 16px;
}

.research-carousel-btn.next {
  right: 16px;
}

.research-carousel-dots {
  display: flex;
  justify-content: center;
  gap: 9px;
  margin-top: 14px;
}

.research-carousel-dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  border: none;
  background: #c9c9c9;
  cursor: pointer;
  transition:
    width 280ms ease,
    background 280ms ease,
    transform 280ms ease;
  padding: 0;
}

.research-carousel-dot.active {
  width: 26px;
  border-radius: 999px;
  background: #3b82f6;
}

.research-carousel-dot:hover {
  transform: scale(1.15);
}

.research-carousel-dot:focus {
  outline: 2px solid rgba(59, 130, 246, 0.45);
  outline-offset: 3px;
}

/* 尊重系统“减少动态效果”的设置 */
@media (prefers-reduced-motion: reduce) {
  .research-carousel-track,
  .research-carousel-slide img,
  .research-carousel-caption,
  .research-carousel-dot,
  .research-carousel-btn {
    transition: none;
  }

  .research-carousel-slide img {
    transform: scale(1);
  }
}

/* 移动端适配 */
@media (max-width: 768px) {
  .research-carousel {
    height: 260px;
    border-radius: 12px;
  }

  .research-carousel-caption {
    padding: 18px 20px;
  }

  .research-carousel-caption h3 {
    font-size: 18px;
  }

  .research-carousel-caption p {
    font-size: 13px;
    line-height: 1.45;
  }

  .research-carousel-btn {
    width: 34px;
    height: 34px;
    font-size: 20px;
  }
}
</style>

<div class="research-carousel-wrapper">
  <div class="research-carousel" id="researchCarousel">
    <div class="research-carousel-track">

      <div class="research-carousel-slide"> 
        <img src="images/carousel/Gary_wust.jpg" alt="Welcome Professor Gary G. Yen">
        <div class="research-carousel-caption">
          <h3>Warmly Welcome IEEE Fellow Professor Gary G. Yen to Visit Our Research Group in 2025</h3>
          <p>
            It is a great honor for our research group to welcome Professor Gary G. Yen, IEEE Fellow,
            for academic exchange and scholarly discussion.
          </p>
        </div>
      </div>

      <div class="research-carousel-slide"> 
        <img src="images/carousel/Ishibuchi_wust.jpg" alt="Welcome Professor Hisao Ishibuchi">
        <div class="research-carousel-caption">
          <h3>Warmly Welcome IEEE Fellow Professor Hisao Ishibuchi to Visit Our Research Group in 2025</h3>
          <p>
            It is a great honor for our research group to welcome Professor Hisao Ishibuchi, IEEE Fellow,
            for academic exchange and scholarly discussion.
          </p>
        </div>
      </div>

      <div class="research-carousel-slide"> 
        <img src="images/carousel/BICTA25.jpg" alt="BICTA 2025 Group Photo">
        <div class="research-carousel-caption">
          <h3>Our Research Group Co-organized BICTA 2025</h3>
          <p>
            As a co-organizer of BICTA 2025, our research group actively supported scholarly
            exchange and interdisciplinary collaboration in bio-inspired computing,
            evolutionary computation, and intelligent optimization.
          </p>
        </div>
      </div>

      <div class="research-carousel-slide"> 
        <img src="images/carousel/TY.jpg" alt="Welcome Professor Ye Tian">
        <div class="research-carousel-caption">
          <h3>Warmly Welcome Professor Ye Tian to Visit Our Research Group in 2025</h3>
          <p>
            It is a great honor for our research group to welcome Professor Ye Tian
            for academic exchange and scholarly discussion.
          </p>
        </div>
      </div>

      <div class="research-carousel-slide"> 
        <img src="images/carousel/23_Gary_wust.jpg" alt="Welcome Professor Gary G. Yen in 2023">
        <div class="research-carousel-caption">
          <h3>Warmly Welcome IEEE Fellow Professor Gary G. Yen to Visit Our Research Group in 2023</h3>
          <p>
            It is a great honor for our research group to welcome Professor Gary G. Yen, IEEE Fellow,
            for academic exchange and scholarly discussion.
          </p>
        </div>
      </div>

    </div>

    <button class="research-carousel-btn prev" type="button" aria-label="Previous slide">&#10094;</button>
    <button class="research-carousel-btn next" type="button" aria-label="Next slide">&#10095;</button>
  </div>

  <div class="research-carousel-dots" id="researchCarouselDots"></div>
</div>

<script>
(function () {
  function initResearchCarousel() {
    const carousel = document.getElementById("researchCarousel");
    if (!carousel) return;

    /*
     * 防止重复初始化。
     * 如果脚本被浏览器缓存恢复、Jekyll 页面重载或其他机制重复执行，
     * 先销毁旧实例，避免多个定时器叠加导致轮播突然变快。
     */
    if (
      carousel.__researchCarouselInstance &&
      typeof carousel.__researchCarouselInstance.destroy === "function"
    ) {
      carousel.__researchCarouselInstance.destroy();
    }

    const wrapper = carousel.closest(".research-carousel-wrapper") || carousel;
    const track = carousel.querySelector(".research-carousel-track");
    const slides = Array.from(carousel.querySelectorAll(".research-carousel-slide"));
    const prevBtn = carousel.querySelector(".research-carousel-btn.prev");
    const nextBtn = carousel.querySelector(".research-carousel-btn.next");
    const dotsContainer = document.getElementById("researchCarouselDots");

    if (!track || slides.length === 0 || !prevBtn || !nextBtn || !dotsContainer) return;

    /*
     * 五秒切换一次。
     * 注意：这是每张图的停留节奏，不是动画时间。
     * 动画时间由 CSS 中的 1050ms 控制。
     */
    const AUTOPLAY_DELAY = 5000;
    const TRANSITION_DURATION = 1050;

    let currentIndex = 0;
    let autoplayTimer = null;
    let isPaused = false;
    let isDestroyed = false;
    let isAnimating = false;

    const prefersReducedMotion =
      window.matchMedia &&
      window.matchMedia("(prefers-reduced-motion: reduce)").matches;

    const canAutoplay = slides.length > 1 && !prefersReducedMotion;
    const removeListeners = [];

    function addListener(element, eventName, handler) {
      element.addEventListener(eventName, handler, false);
      removeListeners.push(function () {
        element.removeEventListener(eventName, handler, false);
      });
    }

    dotsContainer.innerHTML = "";

    slides.forEach(function (_, index) {
      const dot = document.createElement("button");
      dot.className = "research-carousel-dot";
      dot.type = "button";
      dot.setAttribute("aria-label", "Go to slide " + (index + 1));

      addListener(dot, "click", function () {
        goToSlide(index);
        scheduleAutoplay();
      });

      dotsContainer.appendChild(dot);
    });

    const dots = Array.from(dotsContainer.querySelectorAll(".research-carousel-dot"));

    function clearAutoplay() {
      if (autoplayTimer !== null) {
        window.clearTimeout(autoplayTimer);
        autoplayTimer = null;
      }
    }

    function scheduleAutoplay() {
      clearAutoplay();

      if (isDestroyed || !canAutoplay || isPaused || document.hidden) {
        return;
      }

      autoplayTimer = window.setTimeout(function () {
        nextSlide();
        scheduleAutoplay();
      }, AUTOPLAY_DELAY);
    }

    function pauseAutoplay() {
      isPaused = true;
      clearAutoplay();
    }

    function resumeAutoplay() {
      isPaused = false;
      scheduleAutoplay();
    }

    function updateCarousel() {
      track.style.transform = "translate3d(-" + currentIndex * 100 + "%, 0, 0)";

      slides.forEach(function (slide, index) {
        slide.classList.toggle("active", index === currentIndex);
      });

      dots.forEach(function (dot, index) {
        dot.classList.toggle("active", index === currentIndex);
      });
    }

    function goToSlide(index) {
      if (slides.length <= 1) return;

      const nextIndex = (index + slides.length) % slides.length;

      if (nextIndex === currentIndex || isAnimating) {
        return;
      }

      currentIndex = nextIndex;
      isAnimating = true;
      updateCarousel();

      window.setTimeout(function () {
        isAnimating = false;
      }, TRANSITION_DURATION + 80);
    }

    function nextSlide() {
      goToSlide(currentIndex + 1);
    }

    function prevSlide() {
      goToSlide(currentIndex - 1);
    }

    addListener(nextBtn, "click", function () {
      nextSlide();
      scheduleAutoplay();
    });

    addListener(prevBtn, "click", function () {
      prevSlide();
      scheduleAutoplay();
    });

    /*
     * 鼠标悬停暂停，离开后恢复。
     * pointerenter / pointerleave 对 Mac Safari、Chrome、Edge 更稳。
     * mouseenter / mouseleave 作为补充兼容。
     */
    addListener(wrapper, "pointerenter", pauseAutoplay);
    addListener(wrapper, "pointerleave", resumeAutoplay);
    addListener(wrapper, "mouseenter", pauseAutoplay);
    addListener(wrapper, "mouseleave", resumeAutoplay);

    /*
     * 用户使用键盘或按钮聚焦时暂停，提高可访问性。
     */
    addListener(wrapper, "focusin", pauseAutoplay);
    addListener(wrapper, "focusout", resumeAutoplay);

    /*
     * 页面切到后台时暂停，回到前台后恢复。
     * 可以避免浏览器后台节流导致恢复时动画异常。
     */
    addListener(document, "visibilitychange", function () {
      if (document.hidden) {
        clearAutoplay();
      } else {
        scheduleAutoplay();
      }
    });

    /*
     * 支持左右键切换。
     */
    addListener(wrapper, "keydown", function (event) {
      if (event.key === "ArrowLeft") {
        prevSlide();
        scheduleAutoplay();
      }

      if (event.key === "ArrowRight") {
        nextSlide();
        scheduleAutoplay();
      }
    });

    if (!wrapper.hasAttribute("tabindex")) {
      wrapper.setAttribute("tabindex", "0");
    }

    /*
     * 初始化首张图的 active 状态。
     * 这样首张图片会有轻微的视觉进入效果，而不是静态显示。
     */
    updateCarousel();
    scheduleAutoplay();

    carousel.__researchCarouselInstance = {
      destroy: function () {
        isDestroyed = true;
        clearAutoplay();
        removeListeners.forEach(function (remove) {
          remove();
        });
        dotsContainer.innerHTML = "";
      }
    };
  }

  if (document.readyState === "loading") {
    document.addEventListener("DOMContentLoaded", initResearchCarousel, { once: true });
  } else {
    initResearchCarousel();
  }
})();
</script>

<!-- ================= Research Highlights Carousel End ================= -->

<span class='anchor' id='about-me'></span>

## ZhiweiXu(许志伟)

`许志伟`博士现任武汉科技大学计算机科学与技术学院、湖北省智能信息处理与实时工业系统重点实验室讲师。2017年于武汉科技大学获信息安全专业学士学位，2022年于武汉科技大学获控制科学与工程专业博士学位。博士阶段师从`张凯教授`。张凯教授现任武汉科技大学研究生院院长、计算机科学与技术学院院长，并担任湖北省智能信息处理与实时工业系统重点实验室主任。2025年3月至9月，本人作为访问学者赴华中科技大学人工智能与自动化学院开展学术访问与合作研究，合作导师为`潘林强教授`。

`许志伟`博士为*IEEE*、*CCF*、*ACM*、*CAAI*、*CIE*、*CAA*、*IEEE-SMC*、*IEEE-CIS*、*ACM-SIGEVO*会员、*中国人工智能学会青年工作委员会委员*、*中国仿真学会智能优化与调度专委会委员*、*中国仿真学会资源规划仿真与决策专委会* 。CSDN人工智能领域优质创作者，博客专家。获得2019年硕士研究生国家奖学金与2021年，2022年博士研究生国家奖学金。近期在约束多目标优化、高维多目标优化以及多目标交通规划方面取得了一系列新进展新突破。参与国家自然科学基金两项，主持省自然科学基金青年项目一项，主持省教育厅青年项目一项。多项研究发表在国际顶级期刊*IEEE Transaction on Evolutionary Computation*， *IEEE Transaction on Cybernetics*，*IEEE Transactions on Intelligent Transportation Systems*，*Information Sciences*，*中国科学：信息科学* 以及 *Applied Soft Computing* 上。获2021年与2022年武汉计算机软件工程学会年会暨学术研讨会优秀研究生，2021年CCF武汉优秀博士生学术风采展示论坛一等奖。

其为计算机和人工智能领域各大顶级期刊的审稿人包括但不限于： **IEEE Transactions on Evolutionary Computation**, **IEEE Transactions on Systems, Man, and Cybernetics: Systems**, **IEEE Transactions on Cybernetics**, **Information Sciences**, **Applied Soft Computing**, **Robotics and Computer-Integrated Manufacturing**, **Neural Computing and Applications**, **Engineering Applications of Artificial Intelligence**, **Expert Systems with Applications**, and **Journal of Membrane Computing**.

其为以下国际会议的审稿人，包括但不限于： **IEEE Congress on Evolutionary Computation (IEEE CEC)**, **IEEE Symposium Series on Computational Intelligence (SSCI)**, **IEEE Conference on Artificial Intelligence (IEEE CAI)** and the **International Conference on Bio-inspired Computing: Theories and Applications (BIC-TA)**.

其担任 **19th International Conference on Bio-inspired Computing: Theories and Applications (BIC-TA 2024)** 以及 **20th International Conference on Bio-inspired Computing: Theories and Applications (BIC-TA 2025)** 的Session chair, 以下国际会议的PC **2025 Asia Conference on Artificial Intelligence Technology (ACAIT2025)** and **The International Conference on Machine Intelligence and Nature-inspired Computing (MIND 2025)**. <a href='https://scholar.google.com/citations?user=_Lkioz8AAAAJ&hl'><img src="https://img.shields.io/endpoint?url={{ url | url_encode }}&logo=Google%20Scholar&labelColor=f6f6f6&color=9cf&style=flat&label=引用"></a>

研究兴趣包括：
- 神经组合优化
- 调度和车辆路径规划
- 演化计算
- 多目标优化（超多目标、约束、多任务、多模态等）
- DNA计算、编码、自组装

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
