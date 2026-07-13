---
layout: default
title: "My Page"
permalink: /ResearchWorkAlbum
---

<style>
  /* ================= Photo Wall Layout Start ================= */

  .photo-wall {
    display: grid;
    grid-template-columns: repeat(6, minmax(0, 1fr));
    gap: 14px;
    padding: 20px 0;
    width: 100%;
  }

  .photo-item {
    display: flex;
    flex-direction: column;
    background: #fff;
    border-radius: 10px;
    overflow: hidden;
    box-shadow: 0 4px 14px rgba(0, 0, 0, 0.08);
    transition: transform 0.25s ease, box-shadow 0.25s ease;
  }

  .photo-item:hover {
    transform: translateY(-4px);
    box-shadow: 0 8px 22px rgba(0, 0, 0, 0.14);
  }

  .photo-item img {
    width: 100%;
    aspect-ratio: 4 / 3;
    height: auto;
    object-fit: cover;
    display: block;
    border-radius: 0;
    cursor: zoom-in;
    transition: transform 0.35s ease;
  }

  .photo-item:hover img {
    transform: scale(1.06);
  }

  .photo-item p {
    margin: 0;
    padding: 8px 9px 10px;
    font-size: 12px;
    line-height: 1.55;
    color: #333;
    text-align: justify;
    background: #fff;

    display: -webkit-box;
    -webkit-line-clamp: 4;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }

  .photo-item:hover p {
    -webkit-line-clamp: unset;
    overflow: visible;
  }

  /* 超宽屏：如果页面容器足够宽，则每行 8 张 */
  @media (min-width: 1600px) {
    .photo-wall {
      grid-template-columns: repeat(8, minmax(0, 1fr));
      gap: 12px;
    }

    .photo-item p {
      font-size: 11.5px;
      line-height: 1.5;
    }
  }

  /* 普通笔记本或较窄页面：每行 4 张 */
  @media (max-width: 1200px) {
    .photo-wall {
      grid-template-columns: repeat(4, minmax(0, 1fr));
      gap: 14px;
    }
  }

  /* 平板：每行 3 张 */
  @media (max-width: 900px) {
    .photo-wall {
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 12px;
    }

    .photo-item p {
      font-size: 11.5px;
      line-height: 1.5;
    }
  }

  /* 手机横屏或窄屏：每行 2 张 */
  @media (max-width: 600px) {
    .photo-wall {
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 10px;
      padding: 12px 0;
    }

    .photo-item p {
      padding: 7px 8px 9px;
      font-size: 11px;
      line-height: 1.45;
      -webkit-line-clamp: 3;
    }
  }

  /* 极窄屏：每行 1 张 */
  @media (max-width: 380px) {
    .photo-wall {
      grid-template-columns: 1fr;
    }
  }

  /* ================= Photo Wall Layout End ================= */


  /* ================= Fullscreen Lightbox Start ================= */

  .photo-lightbox {
    position: fixed;
    inset: 0;
    z-index: 99999;
    display: none;
    align-items: center;
    justify-content: center;
    padding: 32px;
    background: rgba(0, 0, 0, 0.88);
    backdrop-filter: blur(4px);
    -webkit-backdrop-filter: blur(4px);
  }

  .photo-lightbox.active {
    display: flex;
  }

  .photo-lightbox-content {
    position: relative;
    max-width: 96vw;
    max-height: 92vh;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .photo-lightbox-image-wrap {
    position: relative;
    min-width: min(420px, 80vw);
    min-height: min(280px, 52vh);
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .photo-lightbox img {
    max-width: 96vw;
    max-height: 82vh;
    object-fit: contain;
    border-radius: 10px;
    box-shadow: 0 16px 48px rgba(0, 0, 0, 0.55);
    animation: lightboxZoomIn 0.28s ease;
    cursor: default;
    background: rgba(255, 255, 255, 0.04);
  }

  .photo-lightbox-caption {
    max-width: 92vw;
    margin-top: 14px;
    padding: 0 12px;
    color: #f5f5f5;
    font-size: 15px;
    line-height: 1.65;
    text-align: center;
  }

  .photo-lightbox-loader {
    position: absolute;
    inset: 0;
    z-index: 2;
    display: none;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 12px;
    color: rgba(255, 255, 255, 0.88);
    font-size: 14px;
    letter-spacing: 0.5px;
    pointer-events: none;
  }

  .photo-lightbox.is-loading .photo-lightbox-loader {
    display: flex;
  }

  .photo-lightbox-spinner {
    width: 34px;
    height: 34px;
    border: 3px solid rgba(255, 255, 255, 0.28);
    border-top-color: rgba(255, 255, 255, 0.92);
    border-radius: 50%;
    animation: photoLightboxSpin 0.9s linear infinite;
  }

  .photo-lightbox-close {
    position: fixed;
    top: 22px;
    right: 28px;
    width: 42px;
    height: 42px;
    border: none;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.16);
    color: #fff;
    font-size: 30px;
    line-height: 42px;
    cursor: pointer;
    z-index: 100000;
    transition: background 0.2s ease, transform 0.2s ease, opacity 0.2s ease;
  }

  .photo-lightbox-close:hover,
  .photo-lightbox-close:focus {
    background: rgba(255, 255, 255, 0.28);
    transform: scale(1.06);
    outline: none;
  }

  .photo-lightbox-nav {
    position: fixed;
    top: 50%;
    transform: translateY(-50%);
    width: 46px;
    height: 46px;
    border: none;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.16);
    color: #fff;
    font-size: 30px;
    cursor: pointer;
    z-index: 100000;
    transition: background 0.2s ease, transform 0.2s ease, opacity 0.2s ease;
  }

  .photo-lightbox-nav:hover,
  .photo-lightbox-nav:focus {
    background: rgba(255, 255, 255, 0.28);
    transform: translateY(-50%) scale(1.06);
    outline: none;
  }

  .photo-lightbox-nav:disabled {
    opacity: 0.35;
    cursor: not-allowed;
  }

  .photo-lightbox-prev {
    left: 28px;
  }

  .photo-lightbox-next {
    right: 28px;
  }

  .photo-lightbox-error {
    color: #ffd7d7;
  }

  @keyframes lightboxZoomIn {
    from {
      opacity: 0;
      transform: scale(0.96);
    }

    to {
      opacity: 1;
      transform: scale(1);
    }
  }

  @keyframes photoLightboxSpin {
    from {
      transform: rotate(0deg);
    }

    to {
      transform: rotate(360deg);
    }
  }

  body.photo-lightbox-open {
    overflow: hidden;
  }

  @media (max-width: 768px) {
    .photo-lightbox {
      padding: 18px;
    }

    .photo-lightbox-image-wrap {
      min-width: min(300px, 82vw);
      min-height: min(220px, 45vh);
    }

    .photo-lightbox img {
      max-width: 94vw;
      max-height: 76vh;
    }

    .photo-lightbox-caption {
      font-size: 13px;
      line-height: 1.55;
    }

    .photo-lightbox-close {
      top: 14px;
      right: 14px;
      width: 38px;
      height: 38px;
      font-size: 26px;
      line-height: 38px;
    }

    .photo-lightbox-nav {
      width: 38px;
      height: 38px;
      font-size: 24px;
    }

    .photo-lightbox-prev {
      left: 12px;
    }

    .photo-lightbox-next {
      right: 12px;
    }
  }

  @media (prefers-reduced-motion: reduce) {
    .photo-item,
    .photo-item img,
    .photo-lightbox img,
    .photo-lightbox-close,
    .photo-lightbox-nav,
    .photo-lightbox-spinner {
      transition: none;
      animation: none;
    }
  }

  /* ================= Fullscreen Lightbox End ================= */
</style>

## 科研相册

<div class="photo-wall">
  <div class="photo-item">
    <img src="images/album/26XT.jpg" alt="2026年湘潭大学暑期学校" loading="lazy" decoding="async">
    <p>课题组陈丕林、黄奕然同学参加[2026年湘潭大学智能优化研究生暑期学校]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/CWMC2026.jpg" alt="CWMC2026" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加[2026中国膜计算论坛-中国重庆-重庆城市科技学院]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ISOS2026.jpg" alt="ISOS2026" loading="lazy" decoding="async">
    <p>课题组许志伟老师、余倩倩老师参加[2026中国仿真学会智能优化与调度会议-中国广州-广东工业大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/26LC.jpg" alt="26LC" loading="lazy" decoding="async">
    <p>课题组许志伟老师、余倩倩老师参加中国仿真学会资源规划仿真与决策专委会暨第一届学术年会。图为武汉科技大学管理学院彭琨琨老师、武汉科技大学机械工程学院张子凯老师、李梓响老师、武汉科技大学计算机科学与技术学院许志伟老师、余倩倩老师合影留念</p>
  </div>
  <div class="photo-item">
    <img src="images/album/26LC_YQQ.jpg" alt="26LC_YQQ" loading="lazy" decoding="async">
    <p>课题组余倩倩老师获聘中国仿真学会资源规划仿真与决策专业委员会委员</p>
  </div>
  <div class="photo-item">
    <img src="images/album/26LC_XZW.jpg" alt="26LC_XZW" loading="lazy" decoding="async">
    <p>课题组许志伟老师获聘中国仿真学会资源规划仿真与决策专业委员会委员</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2026DJ.jpg" alt="2026DJ" loading="lazy" decoding="async">
    <p>课题组许志伟老师、余倩倩老师参加中国仿真学会智能优化与调度专委会党建活动</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2026DQQ.jpg" alt="2026DQQ" loading="lazy" decoding="async">
    <p>江西财经大学段琦琦老师访问本课题组并做学术报告</p>
  </div>
  <div class="photo-item">
    <img src="images/album/GAIIS2026.jpg" alt="GAIIS2026" loading="lazy" decoding="async">
    <p>课题组许志伟老师担任GAIIS 2026国际会议程序主席，并在大会作报告</p>
  </div>
  <div class="photo-item">
    <img src="images/album/TY2025.jpg" alt="TY2025" loading="lazy" decoding="async">
    <p>国家级青年人才田野教授应邀访问本课题组并做专题报告</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ACAIT2025YCT.jpg" alt="ACAIT2025YCT" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加[2025年亚洲人工智能技术大会ACAIT2025-中国鄂尔多斯-中国人工智能学会青工委],课题组许志伟老师（右）和郑州大学岳彩通教授合影留念</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ACAIT25_PC.jpg" alt="ACAIT25_PC" loading="lazy" decoding="async">
    <p>课题组许志伟老师受聘作为ACAIT2025 PC</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2024hubeikexie.jpg" alt="2024hubeikexie" loading="lazy" decoding="async">
    <p>课题组论文获得2024年度湖北省科协优秀科技论文</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2025BICTA_Gary.jpg" alt="2025BICTA_Gary" loading="lazy" decoding="async">
    <p>课题组许志伟老师协办2025年度BICTA，并与IEEE Fellow Gary G. Yen教授合影留念[BICTA2025-中国武汉-华中科技大学/武汉科技大学/湖北省运筹学会]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/BICTA25.jpg" alt="BICTA25" loading="lazy" decoding="async">
    <p>课题组许志伟老师协办2025年度BICTA，并与华中科技大学潘林强教授课题组合影留念[BICTA2025-中国武汉-华中科技大学/武汉科技大学/湖北省运筹学会]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2025Gary.jpg" alt="2025Gary" loading="lazy" decoding="async">
    <p>IEEE Fellow Gary G. Yen 教授应邀访问本课题组并做专题报告</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2025Jiujiang.jpg" alt="2025Jiujiang" loading="lazy" decoding="async">
    <p>课题组许志伟老师访问九江学院计算机与大数据科学学院，并作多解多目标最短路径规划专题报告[中国九江，九江学院]，课题组许志伟老师（前排中）和九江学院计算机与大数据科学学院彭虎院长（前排右），九江学院董小刚老师（前排左）合影留念</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2025Ishibuchi.jpg" alt="2025Ishibuchi" loading="lazy" decoding="async">
    <p>IEEE Fellow Ishibuchi 教授和彭丽敏博士应邀访问本课题组并做专题报告</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ACAIT2025.jpg" alt="2025ACAIT" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加[2025年中国人工智能学会青工委年会-中国鄂尔多斯-内蒙古师范大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ECOLE2025.jpg" alt="2025ECOLE" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加[2025年ECOLE演化计算研讨会-中国深圳-南方科技大学],并展示论文海报</p>
  </div>
  <div class="photo-item">
    <img src="images/album/DOCS2025.jpg" alt="2025DOCS" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加[2025年DOCS第七届复杂系统数据驱动优化国际会议-中国太原-太原理工大学],并在动态柔性车间调度赛道获得优秀奖</p>
  </div>
  <div class="photo-item">
    <img src="images/album/CEC2025.jpg" alt="2025CEC" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加[2025年IEEE 演化计算大会 CEC -中国杭州-西湖大学],课题组许志伟老师（右）和哈工大/南科大段琦琦博士合影留念</p>
  </div>
  <div class="photo-item">
    <img src="images/album/CIOC2025.jpg" alt="2025CIOC" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加2025年“树优杯”全国智能优化算法大赛获奖</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ISOS2025.jpg" alt="2025ISOS" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加[2025智能优化与调度会议-中国青岛-青岛科技大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/CWMC2025.jpg" alt="2025CWMC" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加[2025中国膜计算论坛-中国成都-成都信息工程大学],课题组许志伟老师（左）和成都信息工程大学张葛祥教授（中）以及东华理工大学张露萍老师（右）合影留念</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2025CCF-AI.jpg" alt="2025CCF-AI" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加[CCF-AI演化计算学组成立大会-中国杭州-西湖大学/杭州师范大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/CRAIC2024.jpg" alt="CRAIC2024" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加第二十六届中国人工机器人与人工智能大赛获得省二等奖</p>
  </div>
  <div class="photo-item">
    <img src="images/album/BICTA2024_PC.jpg" alt="BICTA2024_PC" loading="lazy" decoding="async">
    <p>课题组许志伟老师受聘作为BICTA2024 Program Chair</p>
  </div>
  <div class="photo-item">
    <img src="images/album/BICTA2024.jpg" alt="BICTA2024" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加[BICTA2024-中国苏州-华中科技大学/苏州大学/湖北省运筹学会]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/DOCS2024.jpg" alt="DOCS2024" loading="lazy" decoding="async">
    <p>[DOCS2024-中国杭州-西湖大学/杭州师范大学]课题组许志伟老师和深圳大学刘松柏老师（右）深圳大学李庚辉老师（左）合影留念</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ECOLE2024.jpg" alt="ECOLE2024" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加[ECOLE2024-中国上海-华东师范大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2023Gary.jpg" alt="2023Gary" loading="lazy" decoding="async">
    <p>2023年IEEE Fellow Gary Yen教授应邀来课题组指导工作, 左为Gary教授, 右为课题组许志伟老师</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ECOLE2023.jpg" alt="ECOLE2023.jpg" loading="lazy" decoding="async">
    <p>2023年课题组许志伟老师参加[ECOLE2023-中国深圳-南方科技大学]，图为课题组许志伟老师和张凌博士与他们的Poster-"Two-Stage Multi-Objective Evolution Strategy for Constrained Multi-Objective Optimization."进行合影</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2022AI.jpg" alt="2022AI.jpg" loading="lazy" decoding="async">
    <p>2022年课题组许志伟老师参加中国光谷人工智能大会[中国武汉-华中科技大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2021CCF.jpg" alt="2021CCF" loading="lazy" decoding="async">
    <p>2021年课题组许志伟老师参加CCF-YOCSEF武汉论坛并获得优秀博士生学术风采展示论坛一等奖</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ECOLE2021.jpg" alt="ECOLE2021" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加[ECOLE2021-中国武汉-武汉大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2020OR.jpg" alt="2020OR" loading="lazy" decoding="async">
    <p>2020年课题组许志伟老师协办第二届鄂鲁陕豫运筹学学术研讨会[中国武汉-华中科技大学-北京大学-武汉科技大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/BICTA2019.png" alt="BICTA2019" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加[BICTA2019-中国郑州-华中科技大学/郑州大学/湖北省运筹学会]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ECOLE2019.jpg" alt="ECOLE2019" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加[ECOLE2019-中国湘潭-湘潭大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/BICTA2018.jpg" alt="BICTA2018" loading="lazy" decoding="async">
    <p>课题组许志伟老师参加[BICTA2018-中国北京-华中科技大学/北京邮电大学/湖北省运筹学会]</p>
  </div>
</div>

<!-- ================= Photo Lightbox Preview Start ================= -->

<div class="photo-lightbox" id="photoLightbox" aria-hidden="true" role="dialog" aria-modal="true">
  <button class="photo-lightbox-close" id="photoLightboxClose" type="button" aria-label="Close image preview">
    &times;
  </button>

  <button class="photo-lightbox-nav photo-lightbox-prev" id="photoLightboxPrev" type="button" aria-label="Previous image">
    &#10094;
  </button>

  <div class="photo-lightbox-content">
    <div class="photo-lightbox-image-wrap">
      <img id="photoLightboxImage" src="" alt="">
      <div class="photo-lightbox-loader" id="photoLightboxLoader">
        <div class="photo-lightbox-spinner"></div>
        <div id="photoLightboxLoadingText">图片加载中，请稍候...</div>
      </div>
    </div>
    <div class="photo-lightbox-caption" id="photoLightboxCaption"></div>
  </div>

  <button class="photo-lightbox-nav photo-lightbox-next" id="photoLightboxNext" type="button" aria-label="Next image">
    &#10095;
  </button>
</div>

<!-- ================= Photo Lightbox Preview End ================= -->

<script>
(function () {
  function initPhotoLightbox() {
    const photoWall = document.querySelector(".photo-wall");
    const lightbox = document.getElementById("photoLightbox");
    const lightboxImage = document.getElementById("photoLightboxImage");
    const lightboxCaption = document.getElementById("photoLightboxCaption");
    const loadingText = document.getElementById("photoLightboxLoadingText");
    const closeBtn = document.getElementById("photoLightboxClose");
    const prevBtn = document.getElementById("photoLightboxPrev");
    const nextBtn = document.getElementById("photoLightboxNext");

    if (!photoWall || !lightbox || !lightboxImage || !lightboxCaption || !loadingText || !closeBtn || !prevBtn || !nextBtn) {
      return;
    }

    const images = Array.from(photoWall.querySelectorAll(".photo-item img"));
    if (images.length === 0) return;

    let currentIndex = 0;
    let targetIndex = 0;
    let touchStartX = 0;
    let touchEndX = 0;
    let isLoading = false;
    let requestToken = 0;

    const imageCache = {};

    function getImageSrc(img) {
      return img.getAttribute("data-full") || img.currentSrc || img.src;
    }

    function getCaption(img) {
      const item = img.closest(".photo-item");
      const caption = item ? item.querySelector("p") : null;
      return caption ? caption.textContent.trim() : (img.alt || "");
    }

    function setLoading(status, message) {
      isLoading = status;
      lightbox.classList.toggle("is-loading", status);
      prevBtn.disabled = status;
      nextBtn.disabled = status;
      if (message) {
        loadingText.textContent = message;
      }
    }

    function preloadImage(src) {
      return new Promise(function (resolve, reject) {
        if (!src) {
          reject(new Error("Empty image source"));
          return;
        }

        if (imageCache[src] === "loaded") {
          resolve(src);
          return;
        }

        const img = new Image();
        img.onload = function () {
          imageCache[src] = "loaded";
          resolve(src);
        };
        img.onerror = function () {
          imageCache[src] = "error";
          reject(new Error("Image load failed: " + src));
        };
        img.src = src;
      });
    }

    function warmupNeighborImages(index) {
      const neighborIndexes = [
        (index - 1 + images.length) % images.length,
        (index + 1) % images.length
      ];

      neighborIndexes.forEach(function (neighborIndex) {
        const img = images[neighborIndex];
        if (!img) return;

        const src = getImageSrc(img);
        if (!src || imageCache[src]) return;

        const preload = new Image();
        preload.onload = function () {
          imageCache[src] = "loaded";
        };
        preload.onerror = function () {
          imageCache[src] = "error";
        };
        preload.src = src;
      });
    }

    /*
     * 核心修复：
     * 先加载目标图片，加载成功后再同时更新 lightboxImage 和 caption。
     * 这样弱网环境下不会出现“标题已经切换，但图片仍然是上一张”的图文错位。
     */
    function updateLightbox(index) {
      if (isLoading) return;

      const img = images[index];
      if (!img) return;

      const src = getImageSrc(img);
      const caption = getCaption(img);
      const alt = img.alt || "Photo preview";
      const token = ++requestToken;

      targetIndex = index;
      setLoading(true, "图片加载中，请稍候...");

      preloadImage(src)
        .then(function () {
          if (token !== requestToken) return;

          currentIndex = targetIndex;
          lightboxImage.src = src;
          lightboxImage.alt = alt;
          lightboxCaption.textContent = caption;
          lightboxCaption.classList.remove("photo-lightbox-error");
          setLoading(false);
          warmupNeighborImages(currentIndex);
        })
        .catch(function () {
          if (token !== requestToken) return;

          lightboxCaption.textContent = "图片加载失败，请检查网络状态或图片路径：" + src;
          lightboxCaption.classList.add("photo-lightbox-error");
          setLoading(false);
        });
    }

    function openLightbox(index) {
      lightbox.classList.add("active");
      lightbox.setAttribute("aria-hidden", "false");
      document.body.classList.add("photo-lightbox-open");
      closeBtn.focus();
      updateLightbox(index);
    }

    function closeLightbox() {
      requestToken++;
      setLoading(false);

      lightbox.classList.remove("active");
      lightbox.setAttribute("aria-hidden", "true");
      document.body.classList.remove("photo-lightbox-open");

      window.setTimeout(function () {
        if (!lightbox.classList.contains("active")) {
          lightboxImage.src = "";
          lightboxImage.alt = "";
          lightboxCaption.textContent = "";
          lightboxCaption.classList.remove("photo-lightbox-error");
        }
      }, 180);
    }

    function showPrevImage() {
      if (isLoading) return;
      const nextIndex = (currentIndex - 1 + images.length) % images.length;
      updateLightbox(nextIndex);
    }

    function showNextImage() {
      if (isLoading) return;
      const nextIndex = (currentIndex + 1) % images.length;
      updateLightbox(nextIndex);
    }

    images.forEach(function (img, index) {
      img.addEventListener("click", function () {
        openLightbox(index);
      });
    });

    closeBtn.addEventListener("click", closeLightbox);

    prevBtn.addEventListener("click", function (event) {
      event.stopPropagation();
      showPrevImage();
    });

    nextBtn.addEventListener("click", function (event) {
      event.stopPropagation();
      showNextImage();
    });

    lightbox.addEventListener("click", function (event) {
      if (event.target === lightbox) {
        closeLightbox();
      }
    });

    document.addEventListener("keydown", function (event) {
      if (!lightbox.classList.contains("active")) return;

      if (event.key === "Escape") {
        event.preventDefault();
        closeLightbox();
      }

      if (event.key === "ArrowLeft") {
        event.preventDefault();
        showPrevImage();
      }

      if (event.key === "ArrowRight") {
        event.preventDefault();
        showNextImage();
      }
    });

    lightbox.addEventListener("touchstart", function (event) {
      touchStartX = event.changedTouches[0].screenX;
    }, { passive: true });

    lightbox.addEventListener("touchend", function (event) {
      touchEndX = event.changedTouches[0].screenX;
      const distance = touchEndX - touchStartX;

      if (Math.abs(distance) < 50) return;

      if (distance < 0) {
        showNextImage();
      } else {
        showPrevImage();
      }
    }, { passive: true });
  }

  if (document.readyState === "loading") {
    document.addEventListener("DOMContentLoaded", initPhotoLightbox, { once: true });
  } else {
    initPhotoLightbox();
  }
})();
</script>