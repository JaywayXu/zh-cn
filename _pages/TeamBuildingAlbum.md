---
layout: default
title: "My Page"
permalink: /TeamBuildingAlbum
---


<style>
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
</style>

## 课题组相册

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
    <img src="images/TeamBuildingAlbum/2023LGA.jpg" alt="2023LGA.jpg">
    <p>2023年课题组团建</p>
  </div>
  <div class="photo-item">
    <img src="images/TeamBuildingAlbum/2022LGA.jpg" alt="2022LGA.jpg">
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

