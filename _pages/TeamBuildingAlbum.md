---
layout: default
title: "My Page"
permalink: /TeamBuildingAlbum
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

## 团建相册

<div class="photo-wall">
  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2026LGA.jpg" alt="2026LGA" loading="lazy" decoding="async">
    <p>2026年课题组团建</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2025LGA.jpg" alt="2025LGA" loading="lazy" decoding="async">
    <p>2025年课题组团建</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2024LGA.jpg" alt="2024LGA" loading="lazy" decoding="async">
    <p>2024年课题组团建</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2024Graduation.jpg" alt="2024Graduation" loading="lazy" decoding="async">
    <p>2024年课题组毕业留念</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2024Reunion1.jpg" alt="2024Reunion1" loading="lazy" decoding="async">
    <p>2024年1718级课题组师生聚会</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2024Reunion2.jpg" alt="2024Reunion2" loading="lazy" decoding="async">
    <p>2024年1718级课题组同学会</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2023Graduation.jpg" alt="2023Graduation" loading="lazy" decoding="async">
    <p>2023年课题组毕业留念</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2023LGA.jpg" alt="2023LGA" loading="lazy" decoding="async">
    <p>2023年课题组团建</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2022LGA.jpg" alt="2022LGA" loading="lazy" decoding="async">
    <p>2022年课题组团建</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2022Graduation.jpg" alt="2022Graduation" loading="lazy" decoding="async">
    <p>2022年课题组毕业留念</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2021Graduation.jpg" alt="2021Graduation" loading="lazy" decoding="async">
    <p>2021年课题组毕业留念</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2021LGA.jpg" alt="2021LGA" loading="lazy" decoding="async">
    <p>2021年课题组团建</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2019Graduation.jpg" alt="2019Graduation" loading="lazy" decoding="async">
    <p>2019年课题组毕业留念</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2019LGA.jpg" alt="2019LGA" loading="lazy" decoding="async">
    <p>2019年课题组团建</p>
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
     * 先加载目标图片，加载成功后再同步更新大图与标题。
     * 避免移动端弱网环境下出现“标题已切换，但图片仍停留在上一张”的图文错位。
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