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

  .photo-lightbox img {
    max-width: 96vw;
    max-height: 82vh;
    object-fit: contain;
    border-radius: 10px;
    box-shadow: 0 16px 48px rgba(0, 0, 0, 0.55);
    animation: lightboxZoomIn 0.28s ease;
    cursor: default;
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
    transition: background 0.2s ease, transform 0.2s ease;
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
    transition: background 0.2s ease, transform 0.2s ease;
  }

  .photo-lightbox-nav:hover,
  .photo-lightbox-nav:focus {
    background: rgba(255, 255, 255, 0.28);
    transform: translateY(-50%) scale(1.06);
    outline: none;
  }

  .photo-lightbox-prev {
    left: 28px;
  }

  .photo-lightbox-next {
    right: 28px;
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

  body.photo-lightbox-open {
    overflow: hidden;
  }

  @media (max-width: 768px) {
    .photo-lightbox {
      padding: 18px;
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
    .photo-lightbox-nav {
      transition: none;
      animation: none;
    }
  }

  /* ================= Fullscreen Lightbox End ================= */
</style>

## 团建相册

<div class="photo-wall">
  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2026LGA.jpg" alt="2026LGA">
    <p>2026年课题组团建</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2025LGA.jpg" alt="2025LGA">
    <p>2025年课题组团建</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2024LGA.jpg" alt="2024LGA">
    <p>2024年课题组团建</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2024Graduation.jpg" alt="2024Graduation">
    <p>2024年课题组毕业留念</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2024Reunion1.jpg" alt="2024Reunion1">
    <p>2024年1718级课题组师生聚会</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2024Reunion2.jpg" alt="2024Reunion2">
    <p>2024年1718级课题组同学会</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2023Graduation.jpg" alt="2023Graduation">
    <p>2023年课题组毕业留念</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2023LGA.jpg" alt="2023LGA">
    <p>2023年课题组团建</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2022LGA.jpg" alt="2022LGA">
    <p>2022年课题组团建</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2022Graduation.jpg" alt="2022Graduation">
    <p>2022年课题组毕业留念</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2021Graduation.jpg" alt="2021Graduation">
    <p>2021年课题组毕业留念</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2021LGA.jpg" alt="2021LGA">
    <p>2021年课题组团建</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2019Graduation.jpg" alt="2019Graduation">
    <p>2019年课题组毕业留念</p>
  </div>

  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2019LGA.jpg" alt="2019LGA">
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
    <img id="photoLightboxImage" src="" alt="">
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
    const closeBtn = document.getElementById("photoLightboxClose");
    const prevBtn = document.getElementById("photoLightboxPrev");
    const nextBtn = document.getElementById("photoLightboxNext");

    if (!photoWall || !lightbox || !lightboxImage || !lightboxCaption || !closeBtn || !prevBtn || !nextBtn) {
      console.warn("Photo lightbox initialization failed: required DOM elements are missing.");
      return;
    }

    const images = Array.from(photoWall.querySelectorAll(".photo-item img"));
    if (images.length === 0) return;

    let currentIndex = 0;
    let touchStartX = 0;
    let touchEndX = 0;

    function getCaption(img) {
      const item = img.closest(".photo-item");
      const caption = item ? item.querySelector("p") : null;
      return caption ? caption.textContent.trim() : (img.alt || "");
    }

    function updateLightbox(index) {
      const img = images[index];
      if (!img) return;

      currentIndex = index;
      lightboxImage.src = img.currentSrc || img.src;
      lightboxImage.alt = img.alt || "Photo preview";
      lightboxCaption.textContent = getCaption(img);
    }

    function openLightbox(index) {
      updateLightbox(index);
      lightbox.classList.add("active");
      lightbox.setAttribute("aria-hidden", "false");
      document.body.classList.add("photo-lightbox-open");
      closeBtn.focus();
    }

    function closeLightbox() {
      lightbox.classList.remove("active");
      lightbox.setAttribute("aria-hidden", "true");
      document.body.classList.remove("photo-lightbox-open");

      window.setTimeout(function () {
        if (!lightbox.classList.contains("active")) {
          lightboxImage.src = "";
          lightboxImage.alt = "";
          lightboxCaption.textContent = "";
        }
      }, 180);
    }

    function showPrevImage() {
      const nextIndex = (currentIndex - 1 + images.length) % images.length;
      updateLightbox(nextIndex);
    }

    function showNextImage() {
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