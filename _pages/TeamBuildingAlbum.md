---
layout: default
title: "My Page"
permalink: /TeamBuildingAlbum
---


  <style>
    .photo-wall {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
      gap: 20px;
      padding: 20px;
    }

    .photo-item {
      text-align: center;
      display: flex;
      flex-direction: column;
      justify-content: flex-start;
      overflow: hidden; /* 确保图片放大时不会溢出容器 */
    }

    .photo-item img {
      width: 100%;
      height: 300px; /* 设置统一的图片高度 */
      object-fit: cover; /* 保证图片内容在限定大小内自适应 */
      border-radius: 8px;
      transition: transform 0.3s ease; /* 设置平滑的过渡效果 */
    }

    /* 鼠标悬停时的放大效果 */
    .photo-item img:hover {
      transform: scale(1.5); /* 鼠标悬停时将图片放大1.2倍 */
    }

    .photo-item p {
      margin-top: 10px;
      font-size: 14px;
      color: #333;
      text-align: center; /* 保持文字居中 */
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

