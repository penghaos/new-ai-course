# 新 AI 课程

> 面向 AI 时代的学习与协作资料库：从 GitHub 心智模型和实操协作出发，延伸到命令行工作法、AI 学习地图、Prompt 优化与知识卡片生产。

这个仓库不只收集“怎么操作”，更重视三件事：建立正确的心智模型、用可验证的流程完成工作，以及把可复用的方法固化成工具。

## 核心课程

### 1. [GitHub 从零到协作](./GitHub从零到协作/README.md)

给完全新手的实战课。从账号安全和网页操作开始，逐步进入本地 Git、团队协作、开源贡献、冲突处理与 GitHub Actions，最后完成一个人 AI 学习知识库。

- 7 个阶段：课前准备、心智模型、网页协作、本地 Git、团队与开源、安全与进阶、结业项目
- 配套 [GitHub 新手速查表](./GitHub从零到协作/GitHub新手速查表.md)
- 配套 [练习参考答案](./GitHub从零到协作/练习参考答案.md)

### 2. [GitHub 为什么这样工作：10 讲](./GitHub为什么这样工作-10讲/README.md)

一套以“为什么”为主线的概念课。不死记按钮和命令，而是理解 Commit、Branch、本地与远端、Pull Request、Issue、Review、Actions 和 Fork 为什么存在。

10 讲共同围绕一个核心判断：**GitHub 管理的不是文件，而是变化。**

## 专题资料

| 资料 | 用途 |
|---|---|
| [《人工智能小白书》](./人工智能小白书.epub) | EPUB 电子书，用于建立 AI 基础认知 |
| [如何像专家一样使用命令行工具](./像专家一样使用命令行工具.md) | 从观察、定位、预览、修改、验证到自动化的 CLI 工作法 |
| [AI 时代学习地图生成器](./learning-map.md) | 以心智模型、决策地图和生态系统为主线的英文 Prompt 模板 |

## Agent 与 Skill

### `_loki` Prompt 改写代理

[`_loki.zh.md`](./_loki.zh.md) 是中文版，[`_loki.md`](./_loki.md) 是英文版。它只把原始请求改写成更精准、可验证的 Prompt，不执行 Prompt 中的任务。

核心原则：**指定目的地，删除旅程**（Specify the destination. Delete the journey.）。

### [黄衣少年知识卡片 Skill](./yellow-hoodie-knowledge-card/SKILL.md)

把概念、文章或笔记转换为 600 字以内的知识卡片绘图 Prompt。目录内包含角色和视觉规范、布局选择以及风格参考图。

### 开发工作流模板

- [`excute-plan.md`](./excute-plan.md)：按计划文件逐项实施、验证、回写状态并完成差距审计
- [`fix.md`](./fix.md)：遵循“复现 → 诊断根因 → 测试 → 修复 → 验证”的完整修复流程

## 推荐学习顺序

1. 如果你从未使用 GitHub，先学《[GitHub 从零到协作](./GitHub从零到协作/README.md)》并完成每课练习。
2. 再读《[GitHub 为什么这样工作](./GitHub为什么这样工作-10讲/README.md)》，把操作上升为稳定的心智模型。
3. 用《[如何像专家一样使用命令行工具](./像专家一样使用命令行工具.md)》建立安全、可验证的本地工作流。
4. 根据具体任务选用学习地图、`_loki`、知识卡片或开发工作流模板。

## 目录结构

```text
.
├── GitHub从零到协作/              # 新手实战课、速查表与参考答案
├── GitHub为什么这样工作-10讲/      # GitHub 概念与心智模型课
├── yellow-hoodie-knowledge-card/ # 黄衣少年知识卡片 Skill
├── 人工智能小白书.epub             # AI 入门电子书
├── 像专家一样使用命令行工具.md       # CLI 工作法
├── learning-map.md                 # AI 时代学习地图 Prompt
├── _loki.md / _loki.zh.md          # Prompt 改写代理
├── excute-plan.md / fix.md         # 开发工作流模板
└── qingxin-reading-01.css           # 阅读与电子书排版样式
```

## 使用说明

- Markdown 文件可直接在 GitHub、VMark 或其他 Markdown 编辑器中阅读。
- EPUB 文件可下载后用 Apple Books、Calibre 或其他电子书阅读器打开。
- Agent 和 Skill 文件是可复用配置，导入前请先阅读其触发条件、输入边界和工具权限。
- `.vmark/` 为本地 VMark 版本追踪数据，不作为课程内容提交。
