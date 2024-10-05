---
layout: default
title: "My Page"
permalink: /photowall
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
}

.photo-item img {
  width: 100%;
  height: auto;
  border-radius: 8px;
}

.photo-item p {
  margin-top: 10px;
  font-size: 16px;
  color: #333;
}
</style>

## 团队活动照片墙

<div class="photo-wall">
  <div class="photo-item">
    <img src="images/album/DOCS2024.jpg" alt="DOCS2024">
    <p>DOCS2024课题组许志伟老师和深圳大学刘松柏老师（右）深圳大学李庚辉老师（左）合影留念</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ECOLE2024.jpg" alt="ECOLE2024">
    <p>课题组参加ECOLE2024</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2024Graduation.jpg" alt="2024Graduation">
    <p>2024年课题组毕业留念</p>
  </div>

</div>

