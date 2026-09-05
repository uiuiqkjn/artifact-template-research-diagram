# Research Diagram Style for Codex

一个不依赖参考图片的 Codex 技能，用于生成科研项目技术路线、机器人系统架构和学术论文框架图。

视觉特征：

- 纯黑或透明背景
- 白色圆角模块、彩色细描边、深蓝硬投影
- 淡蓝、薄荷绿、浅紫、浅橙标题栏
- 蓝色实线主流程和橙色虚线反馈闭环
- 严格网格、高信息密度、适合科研汇报 PPT

仓库不包含原始参考图或其预览副本。

## 安装

在 Codex 中发送：

```text
请从以下 GitHub 地址安装技能：
https://github.com/uiuiqkjn/artifact-template-research-diagram/tree/main/research-diagram-style
```

也可以克隆仓库后，将 `research-diagram-style` 文件夹复制到：

```text
~/.codex/skills/research-diagram-style
```

## 使用

```text
$research-diagram-style

请绘制一张竖版 4:5 的科研技术路线图。
标题：多模态机器人自主作业技术路线
阶段：环境感知 → 状态估计 → 任务规划 → 安全执行 → 结果验证
异常恢复：结果验证失败后返回环境感知。
```

建议提供准确的模块名称、连接关系、反馈闭环和画面比例。需要中文完全准确或后续编辑时，请要求输出 SVG 和 PNG。

