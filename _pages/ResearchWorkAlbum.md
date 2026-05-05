---
layout: default
title: "My Page"
permalink: /ResearchWorkAlbum
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
    <img src="images/album/26LC.jpg" alt="26LC">
    <p>课题组许志伟老师、余倩倩老师参加中国仿真学会资源规划仿真与决策专委会暨第一届学术年会。图为武汉科技大学管理学院彭琨琨老师、武汉科技大学机械工程学院张子凯老师、李梓响老师、武汉科技大学计算机科学与技术学院许志伟老师、余倩倩老师合影留念</p>
  </div>
  <div class="photo-item">
    <img src="images/album/26LC_YQQ.jpg" alt="26LC_YQQ">
    <p>课题组余倩倩老师获聘中国仿真学会资源规划仿真与决策专业委员会委员</p>
  </div>
  <div class="photo-item">
    <img src="images/album/26LC_XZW.jpg" alt="26LC_XZW">
    <p>课题组许志伟老师获聘中国仿真学会资源规划仿真与决策专业委员会委员</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2026DJ.jpg" alt="2026DJ">
    <p>课题组许志伟老师、余倩倩老师参加中国仿真学会智能优化与调度专委会党建活动</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2026DQQ.jpg" alt="2026DQQ">
    <p>江西财经大学段琦琦老师访问本课题组并做学术报告</p>
  </div>
  <div class="photo-item">
    <img src="images/album/GAIIS2026.jpg" alt="GAIIS2026">
    <p>课题组许志伟老师担任GAIIS 2026国家会议程序主席，并在大会作报告</p>
  </div>
  <div class="photo-item">
    <img src="images/album/TY2025.jpg" alt="TY2025">
    <p>国家级青年人才田野教授应邀访问本课题组并做专题报告</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ACAIT2025YCT.jpg" alt="ACAIT2025YCT">
    <p>课题组许志伟老师参加[2025年亚洲人工智能技术大会ACAIT2025-中国鄂尔多斯-中国人工智能学会青工委],课题组许志伟老师（右）和郑州大学岳彩通教授合影留念</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ACAIT25_PC.jpg" alt="ACAIT25_PC">
    <p>课题组许志伟老师受聘作为ACAIT2025 PC</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2024hubeikexie.jpg" alt="2024hubeikexie">
    <p>课题组许志伟老师论文获得2024年度湖北省科协优秀科技论文</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2025BICTA_Gary.jpg" alt="2025BICTA_Gary">
    <p>课题组许志伟老师协办2025年度BICTA，并与IEEE Fellow Gary G. Yen教授合影留念[BICTA2025-中国武汉-华中科技大学/武汉科技大学/湖北省运筹学会]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/BICTA25.jpg" alt="BICTA25">
    <p>课题组许志伟老师协办2025年度BICTA，并与华中科技大学潘林强教授课题组合影留念[BICTA2025-中国武汉-华中科技大学/武汉科技大学/湖北省运筹学会]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2025Gary.jpg" alt="2025Gary">
    <p>IEEE Fellow Gary G. Yen 教授应邀访问本课题组并做专题报告</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2025Jiujiang.jpg" alt="2025Jiujiang">
    <p>课题组许志伟老师访问九江学院计算机与大数据科学学院，并作多解多目标最短路径规划专题报告[中国九江，九江学院]，课题组许志伟老师（前排中）和九江学院计算机与大数据科学学院彭虎院长（前排右），九江学院董小刚老师（前排左）合影留念</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2025Ishibuchi.jpg" alt="2025Ishibuchi">
    <p>IEEE Fellow Ishibuchi 教授和彭丽敏博士应邀访问本课题组并做专题报告</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ACAIT2025.jpg" alt="2025ACAIT">
    <p>课题组许志伟老师参加[2025年中国人工智能学会青工委年会-中国鄂尔多斯-内蒙古师范大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ECOLE2025.jpg" alt="2025ECOLE">
    <p>课题组许志伟老师参加[2025年ECOLE演化计算研讨会-中国深圳-南方科技大学],并展示论文海报</p>
  </div>
  <div class="photo-item">
    <img src="images/album/DOCS2025.jpg" alt="2025DOCS">
    <p>课题组许志伟老师参加[2025年DOCS第七届复杂系统数据驱动优化国际会议-中国太原-太原理工大学],并在动态柔性车间调度赛道获得优秀奖</p>
  </div>
  <div class="photo-item">
    <img src="images/album/CEC2025.jpg" alt="2025CEC">
    <p>课题组许志伟老师参加[2025年IEEE 演化计算大会 CEC -中国杭州-西湖大学],课题组许志伟老师（右）和哈工大/南科大段琦琦博士合影留念</p>
  </div>
  <div class="photo-item">
    <img src="images/album/CIOC2025.jpg" alt="2025CIOC">
    <p>课题组许志伟老师参加2025年“树优杯”全国智能优化算法大赛获奖</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ISOS2025.jpg" alt="2025ISOS">
    <p>课题组许志伟老师参加[2025智能优化与调度会议-中国青岛-青岛科技大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/CWMC2025.jpg" alt="2025CWMC">
    <p>课题组许志伟老师参加[2025中国膜计算论坛-中国成都-成都信息工程大学],课题组许志伟老师（左）和成都信息工程大学张葛祥教授（中）以及东华理工大学张露萍老师（右）合影留念</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2025CCF-AI.jpg" alt="2025CCF-AI">
    <p>课题组许志伟老师参加[CCF-AI演化计算学组成立大会-中国杭州-西湖大学/杭州师范大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/CRAIC2024.jpg" alt="CRAIC2024">
    <p>课题组许志伟老师参加第二十六届中国人工机器人与人工智能大赛获得省二等奖</p>
  </div>
  <div class="photo-item">
    <img src="images/album/BICTA2024_PC.jpg" alt="BICTA2024_PC">
    <p>课题组许志伟老师受聘作为BICTA2024 Program Chair</p>
  </div>
  <div class="photo-item">
    <img src="images/album/BICTA2024.jpg" alt="BICTA2024">
    <p>课题组许志伟老师参加[BICTA2024-中国苏州-华中科技大学/苏州大学/湖北省运筹学会]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/DOCS2024.jpg" alt="DOCS2024">
    <p>[DOCS2024-中国杭州-西湖大学/杭州师范大学]课题组许志伟老师和深圳大学刘松柏老师（右）深圳大学李庚辉老师（左）合影留念</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ECOLE2024.jpg" alt="ECOLE2024">
    <p>课题组许志伟老师参加[ECOLE2024-中国上海-华东师范大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2023Gary.jpg" alt="2023Gary">
    <p>2023年IEEE Fellow Gary Yen教授应邀来课题组指导工作, 左为Gary教授, 右为课题组许志伟老师</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ECOLE2023.jpg" alt="ECOLE2023.jpg">
    <p>2023年课题组许志伟老师参加[ECOLE2023-中国深圳-南方科技大学]，图为课题组许志伟老师和张凌博士与他们的Poster-"Two-Stage Multi-Objective Evolution Strategy for Constrained Multi-Objective Optimization."进行合影</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2022AI.jpg" alt="2022AI.jpg">
    <p>2022年课题组许志伟老师参加中国光谷人工智能大会[中国武汉-华中科技大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2021CCF.jpg" alt="2021CCF">
    <p>2021年课题组许志伟老师参加CCF-YOCSEF武汉论坛并获得优秀博士生学术风采展示论坛一等奖</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ECOLE2021.jpg" alt="ECOLE2021">
    <p>课题组许志伟老师参加[ECOLE2021-中国武汉-武汉大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/2020OR.jpg" alt="2020OR">
    <p>2020年课题组许志伟老师协办第二届鄂鲁陕豫运筹学学术研讨会[中国武汉-华中科技大学-北京大学-武汉科技大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/BICTA2019.jpg" alt="BICTA2019">
    <p>课题组许志伟老师参加[BICTA2019-中国郑州-华中科技大学/郑州大学/湖北省运筹学会]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/ECOLE2019.jpg" alt="ECOLE2019">
    <p>课题组许志伟老师参加[ECOLE2019-中国湘潭-湘潭大学]</p>
  </div>
  <div class="photo-item">
    <img src="images/album/BICTA2018.jpg" alt="BICTA2018">
    <p>课题组许志伟老师参加[BICTA2018-中国北京-华中科技大学/北京邮电大学/湖北省运筹学会]</p>
  </div>
</div>

