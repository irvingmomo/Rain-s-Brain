---
title: LLM 知识库工作流
tags: [学习成长, AI, 知识管理, 方法论]
source: AI
updated: 2026-08-03
---

> [!note] AI 生成
> 本文由 Claudian 根据 Andrej Karpathy 的推文编译整理，代表方法论提炼，非个人原创观点。
> 原始来源：[[Andrej Karpathy on X_ _LLM Knowledge Bases__Something I'm finding very useful recently_ using LLMs to build personal knowledge bases for various topics of research interest. In this way, a large fraction of my rece (1)|Karpathy：LLM 知识库推文（Raw）]]

# LLM 知识库工作流

Andrej Karpathy 在 2026 年 4 月提出的一套用 LLM 构建个人知识库的工作流。核心观点：**LLM 不只是代码助手，更是知识管理员。** 他的 token 使用方向正从"操控代码"转向"操控知识"。

---

## 五个核心环节

### 1. 数据摄入（Raw/）

把来源文档——文章、论文、代码仓库、数据集、图片——存入 `raw/` 目录，作为未经加工的"原始矿石"。

- 工具推荐：Obsidian Web Clipper（网页剪藏 → Markdown）
- 图片：快捷键一键下载到本地，使 LLM 可以直接读取
- 此目录只放原料，**不手动整理**

### 2. LLM 编译（Wiki）

LLM 读取 `raw/` 内容，**增量"编译"**为一个 wiki——一组按目录组织的 `.md` 文件。编译产物包括：

- 每个原始文档的摘要
- 反向链接（Backlinks）
- 概念分类与概念文章
- 所有概念之间的交叉链接

> **关键原则：Wiki 由 LLM 书写和维护，用户几乎不直接手动编辑。**

### 3. IDE 前端（Obsidian）

Obsidian 作为可视化前端，同时查看：

- `raw/` 中的原始资料
- 编译后的 wiki 文章
- 衍生可视化内容（图表、幻灯片）

可配合 Marp 插件直接在 Obsidian 中渲染幻灯片。

### 4. 问答与输出

Wiki 足够大（如：~100 篇文章、~40 万词）后，可向 LLM 提出复杂问题，LLM 在 wiki 内"研究"答案。

输出形式多样：
- Markdown 文章
- Marp 幻灯片
- matplotlib 图表

**重要：输出归档回 wiki。** 每次探索都"累积"进知识库，知识库越用越聪明。

### 5. 健康检查（Linting）

定期让 LLM 对 wiki 做"体检"：

- 找出数据不一致之处
- 用网络搜索补充缺失数据
- 发现有趣的概念连接，提出新文章候选

---

## 在本 Vault 的对应实践

| Karpathy 环节 | 本 Vault 实现 |
|---|---|
| `raw/` 原始目录 | `Raw/` 文件夹 |
| LLM 编译 wiki | 主题文件夹（`教育规划/`、`财务与政策/`、`健康/` 等） |
| 自维护索引文件 | [[笔记索引]] |
| Obsidian IDE | Obsidian + Claudian 插件 |
| Q&A 查询 | 直接与 Claudian 对话 |
| 健康检查 | 运行 `/review` 指令 |

---

## 关键启示

> "用 LLM 操控知识，就像过去用 LLM 操控代码一样。"

Karpathy 认为这个方向存在"一个极好的新产品机会"，而不只是一堆脚本的临时拼凑。

**对个人用户的最简起步：**
1. 用 `Raw/` 收集原始资料（文章、推文、剪藏）
2. 告诉 Claudian："把这篇编译成一篇概念文章"
3. 让输出自动链接到已有笔记
4. 定期让 Claudian 检查连接和缺口

---

## 延伸阅读

- [[Your AI Mastery Roadmap — 2026 Edition]]：AI 工具完整学习路线，Phase 2 有 NotebookLM 深度应用推荐
- [[笔记索引]]：本 Vault 全局导航，含各笔记摘要
