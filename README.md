# 拓竹 A1 mini · 交互图解

**在线体验：** https://wouigw.github.io/3d-printer-demo-manual/

把 A1 mini 的纸质说明书，做成一个能转、能拆、能一步步演给你看的网页图解。
单个 HTML 文件，零依赖，双击即可离线打开。

## 它能做什么

- **360° 转台**：任意角度都能看，遮挡与深度由引擎自动排序，转一整圈也不会穿帮
- **五步流程**：装打印板 → 装载耗材 → 自动调平 → 开始打印 → 取下模型，每步都有对应动画、提示与温度读数
- **透视拆解**：外壳一键变线框，17 处内部结构都标了名字（PTFE 管、Z 丝杠、挤出轮、X 线轨、加热块…）
- **手绘等轴画风**：可调手绘抖动、5 套配色（芥黄 / 番茄 / 薄荷 / 钴蓝 / 藕粉）、透视标签

片中的数字都能在源码里查到：36 点调平对应 `6×6` 探测网格，打印时喷嘴 220℃、热床 60℃，各阶段时长见 `a1mini/figure.html` 的 `stepSim()`。

## 怎么打开

- 在线：https://wouigw.github.io/3d-printer-demo-manual/a1mini/a1mini.html
- 本地：直接双击 [`a1mini/a1mini.html`](a1mini/a1mini.html)，不需要服务器、不需要联网

操作：拖动画面旋转 · 双击回到正面 · 点左侧五步按钮播放流程 · 右上角「透视 / 标签」切换拆解视图。

## 目录

```
a1mini/
├── a1mini.html        成品：单文件页面（引擎脚本已内联）
├── figure.html        源文件：场景、五步逻辑、标注
├── core.js            引擎副本（构建时使用）
└── research/          拓竹官方 wiki / 快速入门的中文快照，作为建模与文案依据
colorfigures/
├── assets/core.js     等轴投影、遮挡排序、配色、标签
└── scripts/build.py   把引擎内联进成品
index.html             GitHub Pages 首页，跳转到图解
.github/workflows/     Pages 自动部署
```

重新打包：`python3 colorfigures/scripts/build.py a1mini/figure.html a1mini/a1mini.html`

## 来源与致谢

- 图解引擎：**Colorfigures** — https://april-zhu.com/colorfigures
- 机型资料：拓竹官方 wiki 与 A1 mini 快速入门（快照在 `a1mini/research/`）
- 页面无第三方脚本、无外部字体请求

## 声明

非官方个人项目，仅用于学习与演示，与拓竹（Bambu Lab）官方无关。
「拓竹」「A1 mini」是各自的商标，此处仅用于指明机型。
