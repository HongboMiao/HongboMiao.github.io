---
permalink: /
title: "缪弘博 | Hongbo Miao"
excerpt: "电子科技大学（深圳）准研究生（研0），研究生阶段为 2027.09–2030.06，关注 GPU 并行计算、通信与算子优化、AI 系统。GWBP 独立第一作者，Euro-Par 2026 接收。"
author_profile: true
redirect_from:
  - /about/
  - /about.html
  - /zh-cn/
---

<span class="anchor" id="about-me"></span>

# 👋 你好，欢迎来到我的主页！

我是**缪弘博（Hongbo Miao）**，**电子科技大学（深圳）准研究生**，将于 **2027 年 9 月**入学，目前就读于青海大学计算机科学与技术专业。

我主要围绕 **GPU 并行计算、通信与算子优化**开展学习和科研实践，也关注深度学习系统、推理优化与多尺度时序预测。

我喜欢从实际应用中定位性能瓶颈，再通过算法实现、内存管理与并行调度改善端到端效率。

欢迎通过[邮件](mailto:macro_bou@163.com)交流相关实习机会与科研合作，也可以在 [GitHub](https://github.com/HongboMiao) 查看我的开源项目。

<span class="anchor" id="news"></span>

# 🔥 近期动态

- **2026.05**：论文 **GWBP** 被 **Euro-Par 2026** 接收。[论文](files/GWBP_Euro-Par.pdf) / [代码](https://github.com/OptiYouth-Lab/GWBP)
- **2025.12**：获得**国家奖学金**。
- **2025.10**：入选腾讯犀牛鸟开源人才培养计划并获评**腾讯开源贡献者**。

<span class="anchor" id="-xscg"></span>
<span class="anchor" id="publications"></span>

# 📝 代表论文

<div class="paper-box gwbp-publication">
  <div class="paper-box-image">
    <figure>
      <div class="badge">Euro-Par 2026</div>
      <a href="files/GWBP_Euro-Par.pdf" aria-label="阅读 GWBP 论文 PDF">
        <img src="images/gwbp-workflow.png" alt="GWBP 端到端流程：GPU 常驻数据、任务批处理与资源复用、双 stream 重叠调度" loading="lazy" width="1197" height="697">
      </a>
      <figcaption></figcaption>
    </figure>
  </div>
  <div class="paper-box-text">
    <h2 class="publication-title"><a href="files/GWBP_Euro-Par.pdf">GWBP: Accelerating Weighted Back-Projection for Image Reconstruction via Efficient GPU Parallel Optimization</a></h2>
    <p><strong>Hongbo Miao</strong>, Haodong Bian</p>
    <p><em>Euro-Par 2026</em> · CCF B </p>
    <p>面向 cryo-ET 的加权反投影重建，将 weighting、3D-CTF correction 与 back-projection 迁移至 GPU，结合中间数据常驻、分片感知批处理、资源复用和双 stream 调度，优化完整重建流程。</p>
    <p>在单张 <strong>NVIDIA A100</strong>、<strong>Proteasome-A</strong> 数据集上，相比多核 CPU 基线，端到端时间从 <strong>3.131 s</strong> 降至 <strong>0.655 s</strong>，最高加速 <strong>4.78×</strong>。</p>
    <p class="publication-links"><a href="files/GWBP_Euro-Par.pdf">[论文 PDF]</a> <a href="https://zenodo.org/records/20506358">[代码]</a> <a href="#gwbp-project">[个人工作]</a></p>
  </div>
</div>

<span class="anchor" id="-kyjl"></span>
<span class="anchor" id="projects"></span>

# 🔬 项目与科研经历

<span class="anchor" id="gwbp-project"></span>

## GWBP：GPU 加速加权反投影重建

*2025.12 – 2026.03 · 青海大学 HDACP 实验室*

- **我的工作**：基于 CUDA 完成 weighting、3D-CTF correction 与 back-projection 的 GPU 化改写，使中间数据和重建体常驻 GPU，减少主机与设备间的重复传输。
- **系统优化**：根据倾角几何约束缩减有效切片范围，进行批处理；复用 buffer 与 cuFFT plan，并通过双缓冲、双 stream 和事件同步重叠预处理与反投影。
- **实验结果**：在 V100、A100 两个平台及两个数据集上进行单 GPU 评估，端到端加速 **3.16–4.78×**；A100 / Proteasome-A 的阶段分析中，3D-CTF 最高加速 **14.08×**。使用相同重建参数，以 **RME < 0.001** 为数值校验标准。

[论文 PDF](files/GWBP_Euro-Par.pdf) / [GitHub](https://github.com/OptiYouth-Lab/GWBP)

## Batch To Batch 通信算子传输优化

*2025.07 – 2025.09 · 腾讯犀牛鸟开源人才培养计划*

- **我的工作**：面向 HBM 中 10K 个离散块（128 B–2 MB）的跨节点搬运，基于 **CUDA + RDMA** 实现端到端传输与校验原型，完成批量聚合、多通道并行、动态批量及缓冲区复用优化。
- **实验结果**：端到端平均吞吐由 **3.6 GiB/s** 提升至最高 **6.84 GiB/s**；2 MB 大块吞吐最高达到 **7.31 GiB/s**。
- **项目认可**：腾讯开源贡献者、腾讯犀牛鸟开源人才培养计划优秀学生。

[GitHub](https://github.com/HongboMiao/Design-of-Batch-to-Batch-Communication-Operator) / [项目新闻](https://blog.csdn.net/tencent__open/article/details/151729620)

## 面向高分辨区域模式的高可扩展并行及智能计算技术

*2025.11 – 2026.06 · 国家超级计算无锡中心*

参与“千万核可扩展公里级海陆气耦合区域气候模式及预测系统”的子课题项目。基于 **GPTL** 定位计算瓶颈，通过调整循环顺序、保持连续维度为内层循环及提前计算循环不变量优化访存与计算路径；结合 **OpenMP 多线程、AVX2 自动向量化与浮点优化**，在数值校验通过的前提下，实现热点算子最高 **3.996×** 加速。

## 大小模型协同的电力负荷多尺度时序预测

*2025.10 – 2026.10 · 电子科技大学大数据研究中心 / 国网青海电力公司*

基于国网青海省公司数据中台，参与大模型与时序模型协同的电力负荷预测研究，完成数据处理、模型设计与结果分析。主要负责**新能源发电预测模型构建**，面向青海省省级、市州级光伏与风电发电量预测任务，开展多尺度建模、训练与评估。

<details class="additional-experience" markdown="1">
<summary>其他研究与早期项目</summary>

**具身智能世界模型自适应精度推理优化**<br>
*2026.02 – 至今 · 青海大学高性能与云计算实验室*

围绕模块精度敏感性与误差传播，探索分层精度分配、中间激活复用和显存生命周期管理，比较不同精度配置下的生成质量、吞吐与显存占用。

**基于无人机遥感的退化草地分类研究**<br>
*2024.12 – 2025.12 · 青海大学*

参与数据清洗、标注规范与增强策略设计，搭建可复现实验流程；基于 YOLOv8 进行类别不均衡处理、训练调参与消融对比。

</details>

<span class="anchor" id="-xl"></span>
<span class="anchor" id="education"></span>

# 🎓 教育经历

**电子科技大学（深圳） · 研究生**<br>
*2027.09 – 2030.06*

- **当前阶段**：研0（入学前），将于 2027 年 9 月入学。

**青海大学 · 计算机科学与技术 · 本科**<br>
*2023.09 – 至今*

- **学业成绩**：GPA **4.33/5.00**，均分 **92.5**，专业排名 **2/255（前 1%）**。
- **相关课程**：并行计算（95）、数据结构与算法（97）、计算机系统平台（95）、线性代数（98）、离散数学（98）、Python（98）。
- **英语能力**：CET-4（521）、CET-6（501）。

<span class="anchor" id="-ryjx"></span>
<span class="anchor" id="awards"></span>

# 🏅 竞赛与荣誉

- **2026**：ASC 世界大学生超级计算机竞赛，**一等奖 · 队长**。
- **2026**：第十届华为 ICT 大赛挑战赛中国总决赛，**二等奖 · 队长**。
- **2025**：ASC 世界大学生超级计算机竞赛，**二等奖**。
- **2025**：第五届线性解法器算法与性能优化竞赛，**二等奖**。
- **2025**：全国大学生计算机系统能力大赛（先导杯），**三等奖**。
- **2025**：第二届海洋计算挑战赛，**星锐奖**。

<span class="anchor" id="-rjry"></span>

- **2025**：**国家奖学金**。
- **2023–2025 学年**：青海大学优秀学生奖学金、五好学生、优秀共青团员，均连续两届。

<details class="additional-experience" markdown="1">
<summary>其他竞赛奖项</summary>

- **2025**：蓝桥杯青海赛区 C/C++ 程序设计，二等奖。
- **2025**：第十六届全国大学生数学竞赛青海赛区，二等奖。

</details>
