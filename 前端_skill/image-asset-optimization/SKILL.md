---
name: image-asset-optimization
description: 优化图片压缩、懒加载、占位图、响应式图片和静态资源路径。Use when reducing image weight, adding lazy loading, optimizing static assets, responsive images, placeholders, or frontend media delivery.
---

# Image Asset Optimization

## Quick Start

处理图片资源时：

1. 先查静态资源目录、构建配置、CDN 路径、图片组件和已有压缩流程。
2. 明确图片用途：图标、头像、封面、banner、内容图、背景图或截图。
3. 根据用途选择格式、尺寸、压缩、懒加载和占位策略。
4. 优化应保证图片可用性和视觉质量，不只追求最小体积。

## Must Do

- 大图要压缩并限制展示尺寸，避免上传原图直接进入首屏。
- 列表和非首屏图片优先使用懒加载和占位图。
- 响应式场景要提供合适尺寸，避免移动端加载桌面大图。
- 图片路径要兼容 Vite 构建、部署 base 和 CDN。
- 关键图片要有合理 alt 或可访问替代说明，装饰图可标记为空 alt。
- 不要把大量图片转成内联 base64，除非明确收益大于成本。

## Verification

- 检查首屏、列表滚动、懒加载、加载失败、移动端和部署路径。
- 检查图片清晰度、尺寸、alt、缓存和构建产物体积。
- 运行项目约定的构建命令。
