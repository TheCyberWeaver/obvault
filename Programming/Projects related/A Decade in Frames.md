## 项目开发流程总览

> 把 300 张自拍炼成 **“瑞士钟表级”** timelapse，一共就三大块：  
> **筹备 → 算法/Pipeline 实现 → 输出与交付**。每块再细分若干任务，下面按实际落地顺序给你一份“战术蓝图”。

---

### 1 | 筹备阶段 — 让一切可复制

|步骤|要点|交付物|
|---|---|---|
|**1.1 需求梳理**|- FPS 24、窗口±3 d、EV±1、最终 4 K？1080p？音轨？|简明需求文档 (README.md)|
|**1.2 数据盘点**|确认 300 张命名、EXIF、分辨率、色深|`dataset/raw/`|
|**1.3 环境 & 依赖**|Python ≥ 3.10、OpenCV、MediaPipe、NumPy、FFmpeg CLI|`requirements.txt` / Dockerfile|
|**1.4 目录骨架**|`src/`, `notebooks/`, `tests/`, `output/`|Git repo 初始化|

---

### 2 | 算法 & Pipeline 实现

> 你说算法自己设计，这里只列 **接口** & **责任分层**，方便模块化调换。

| 层级                | 关键任务                                  | 建议文件/函数                         |
| ----------------- | ------------------------------------- | ------------------------------- |
| **2.1 预处理层**      | - 图像统一缩放- 备份原图                        | `preprocess.py::resize()`       |
| **2.2 对齐层**       | - 人脸关键点检测- 仿射对齐- 裁剪/填充                | `align.py::align_face()`        |
| **2.3 排序优化层**     | - 特征抽取 `(L,a,b)` or deep- 局部最短路/DP 排序 | `reorder.py::reorder(window=3)` |
| **2.4 曝光校正层**     | - 求解 `e_i` 最小二乘+约束                    | `exposure.py::solve_gains()`    |
| **2.5 质量评估层**     | - 曲线/直方图、闪烁指标- 可视化 diff               | `metrics.py`                    |
| **2.6 导出层**       | - 临时 PNG → ffmpeg 合成- ProRes/H264 输出  | `export.py::render_video()`     |
| **2.7 CLI / GUI** | - `main.py` 命令行入口- 日志 & 进度条 (tqdm)    | `bin/autolapse`                 |

**最佳实践**

- **函数式→流水线**：每层只做一件事，文件中不混业务。
    
- **配置中心**：`config.yaml` 存放分辨率、λ、EV 限制等，可随时热切换。
    
- **日志**：Python `logging` + 彩色等级，错误栈写文件、INFO 打控制台。
    

---

### 3 | 测试 & 调优

|切面|做什么|工具|
|---|---|---|
|**单元测试**|关键数值函数要 pytest 覆盖率 ≥ 80 %|`pytest`, `tox`|
|**A/B 对比**|不同 λ、窗口长度，自动跑指标|`notebooks/ab_experiments.ipynb`|
|**性能剖析**|大头在关键点检测 & CV warp，考虑批处理 / GPU|`cProfile`, numba, torch|
|**主观回看**|低 fps 草稿片先看跳帧，别一上来就 4 K|VLC, mpv|

---

### 4 | 最终输出 & 交付

|项|说明|
|---|---|
|**产物**|`selfie_timelapse_4k.mp4` + `project_report.pdf`|
|**脚本**|一键跑：`bash run_all.sh --config config.yaml`|
|**文档**|① 高层设计说明书 ② API docstring → Sphinx 生成 ③ CHANGELOG|
|**版本标记**|Git tag `v1.0.0`，打 release asset|
|**备份/归档**|原始+对齐+最终帧分别 zip，硬盘+云双备|

---

### 5 | 时间线（参考）

|周|目标|
|---|---|
|1|环境、数据、骨架 OK|
|2|对齐模块验证，30 张小样跑通|
|3|排序 & 曝光算法原型，CLI alpha|
|4|指标调优 + 完整 300 张跑通|
|5|性能优化、GUI（可选）|
|6|文档、打包、发布|

---

### 6 | DevOps Tips

- **Git hooks**：commit 前自动 lint (`ruff`, `black`)。
    
- **CI**：GitHub Actions 跑 pytest + flake8；PR 图标一目了然。
    
- **Docker**：锁死依赖版本，跨机器跑同样可复现。
    
- **Makefile**：把常用命令 (`make align`, `make render`) 写好，不用背。
    

---

> **一句话：**  
> 结构化目录、分层职责、自动化脚本、可视化指标 —— 把开发流程打造成 **“随便换算法都不崩”** 的稳固轨道，你就能放心花精力在创意和数学上。  
> 祝代码像 ETH Zürich 的钟摆一样精准，视频像瑞士山谷的滑雪道一样顺滑！