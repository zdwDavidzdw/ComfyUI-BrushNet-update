# ComfyUI-BrushNet-update

基于 [nullquant/ComfyUI-BrushNet](https://github.com/nullquant/ComfyUI-BrushNet) 的维护分支，修复新版 ComfyUI 兼容性问题。

A maintained fork of [nullquant/ComfyUI-BrushNet](https://github.com/nullquant/ComfyUI-BrushNet), with compatibility fixes for newer ComfyUI versions.

---

## 这是什么 / What is this

ComfyUI 的 BrushNet 局部重绘插件，支持：

- **BrushNet** — 图像局部重绘（inpainting）
- **PowerPaint** — 多任务重绘（去物体、扩图等）
- **RAUNet** — 高分辨率优化

ComfyUI custom nodes for image inpainting:

- **BrushNet** — local inpainting
- **PowerPaint** — object removal, outpainting, etc.
- **RAUNet** — higher-resolution support

---

## 更新日志 / Changelog

### 2026-06-01

**中文**

- 修复新版 ComfyUI（含秋叶整合包较新内核）运行 KSampler 时的报错：
  `TypeError: brushNet_out_sample_wrapper() got an unexpected keyword argument 'latent_shapes'`
- 修改文件：`model_patch.py`
- 改动内容：为采样 wrapper 增加 `latent_shapes` 参数并透传给 ComfyUI 核心
- **不影响** BrushNet 原有功能与生成效果，仅为兼容性补丁

**English**

- Fixed KSampler crash on newer ComfyUI builds:
  `TypeError: brushNet_out_sample_wrapper() got an unexpected keyword argument 'latent_shapes'`
- Changed file: `model_patch.py`
- Added `latent_shapes` parameter pass-through in the sampling wrapper
- **No change** to BrushNet behavior or output quality — compatibility fix only

---

## 安装 / Installation

```bash
git clone https://github.com/zdwDavidzdw/ComfyUI-BrushNet-update.git
cd ComfyUI-BrushNet-update
pip install -r requirements.txt
```

将文件夹放入 ComfyUI 的 `custom_nodes` 目录，重启 ComfyUI 即可。

Place the folder in ComfyUI's `custom_nodes` directory and restart.

---

## 原项目 / Original Project

https://github.com/nullquant/ComfyUI-BrushNet
