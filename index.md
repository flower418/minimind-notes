---
layout: home
title: minimind从零理解llm训练 | 深入理解 LLM 训练的每个设计选择
description: 通过对照实验彻底理解大语言模型训练的每个设计选择。模块化教学、代码示例和实践指南，适合准备大模型岗位面试的同学。
keywords: LLM训练, 大模型训练, Transformer教程, 深度学习教程, LLM面试准备, 大模型实习准备, 从零学习LLM

hero:
  name: "minimind"
  text: "从零理解llm训练"
  tagline: 不再黑盒训练 — 通过对照实验彻底理解 LLM 的每个设计选择
  actions:
    - theme: brand
      text: 🚀 立即开始
      link: #quick-start
    - theme: alt
      text: 📖 学习路线
      link: /ROADMAP
    - theme: alt
      text: 💻 查看代码
      link: https://github.com/joyehuang/minimind-notes
---

<HomeHeroVideo />
<FeaturesCards />
<LearningPathCards />
<ModulesGrid />
<TerminalCode />

## 💡 为什么选择这个教程？

::: tip 🎯 告别"跑通就行"的盲目训练
你有没有遇到过：按教程跑通了代码，但完全不理解为什么？这个教程用**对照实验**告诉你：不这样设计会发生什么，其他方案为什么不行。
:::

::: tip 🔬 每个设计都有实验支撑
不再纸上谈兵 — 每个模块都有**可执行的对比实验**，亲眼看到不同设计的实际效果。理论 + 实践，真正理解 LLM 训练的每个细节。
:::

::: tip 💻 学习实验低门槛
**学习阶段实验**：基于 TinyShakespeare (1MB) 等微型数据集，在 CPU 上几分钟即可运行，无需 GPU。
**完整训练**：如果要从零训练完整模型，需要 GPU（原 MiniMind 项目：NVIDIA 3090 单卡，约 2 小时）。
:::

<style>
/* 确保暗黑模式下 tip 区域文字可读 */
:global(.dark) .vp-doc .custom-block {
  color: var(--vp-c-text-1);
}

:global(.dark) .vp-doc .custom-block p {
  color: var(--vp-c-text-1);
}

:global(.dark) .vp-doc .custom-block strong {
  color: var(--vp-c-text-1);
}
</style>

## 🔗 相关资源

<div class="resource-grid">

**📦 原项目**
[jingyaogong/minimind](https://github.com/jingyaogong/minimind)

**🗺️ 学习路线**
[完整路线图](/ROADMAP)

**💻 代码示例**
[可执行示例](/learning_materials/README)

**📝 学习笔记**
[学习日志](/learning_log) · [知识库](/knowledge_base)

</div>

<style>
.resource-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 1.5rem;
  margin: 2rem 0;
  padding: 2rem;
  background: var(--vp-c-bg-soft);
  border-radius: 12px;
  border: 1px solid var(--vp-c-divider);
}

/* 暗夜主题优化 - shadcn 风格 */
:global(.dark) .resource-grid {
  background: var(--vp-c-accent-bg);
  border: 1px solid var(--vp-c-divider);
}

:global(.dark) .resource-grid strong {
  color: var(--vp-c-brand-1);
}

.resource-grid strong {
  display: block;
  margin-bottom: 0.75rem;
  color: var(--vp-c-brand-1);
  font-size: 1.05em;
}

.resource-grid a {
  color: var(--vp-c-text-1);
  text-decoration: none;
  transition: color 0.2s;
  font-weight: 500;
}

:global(.dark) .resource-grid a {
  color: var(--vp-c-text-1);
}

.resource-grid a:hover {
  color: var(--vp-c-brand-1);
}

:global(.dark) .resource-grid a:hover {
  color: var(--vp-c-brand-2);
}

@media (max-width: 768px) {
  .resource-grid {
    grid-template-columns: 1fr;
    padding: 1.5rem;
  }
}
</style>

<Sponsorship />
