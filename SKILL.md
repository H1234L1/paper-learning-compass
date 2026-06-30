---
name: paper-learning-compass
description: Help read academic paper PDFs and generate Obsidian-friendly paper learning notes. Use when Codex needs to read papers from an Obsidian vault, create Chinese main paper notes in Notes/, extract paper-specific methodology notes in Methods/{PaperName}/, extract paper-specific concept notes in Concepts/{PaperName}/, link PDFs from Papers/, and avoid Zotero, tables, reading-progress tracking, or confusion logs.
---

# Paper Learning Compass

## Core Rules

Use Chinese by default for the main paper note. Use bilingual English and Chinese for method notes and concept notes.

Work inside the user's Obsidian vault. Treat `Papers/` as the PDF location, `Notes/` as the main paper-note output location, `Methods/{PaperName}/` as paper-specific methodology-note storage, and `Concepts/{PaperName}/` as paper-specific concept-note storage.

Do not store this skill inside the Obsidian vault. Do not create skill files inside the vault.

Do not use tables. Do not use Zotero. Do not track reading progress. Do not track stuck points, confusion records, or similar learning-state logs.

Use concise study-oriented prose. Do not put long method or concept explanations inside the main paper note; move reusable explanations to `Methods/` or `Concepts/`.

## Output Files

Create or update these files as needed:

* Main paper note: `Notes/{PaperName}.md`
* Method notes: `Methods/{PaperName}/{MethodName}.md`
* Concept notes: `Concepts/{PaperName}/{ConceptName}.md`

Use the PDF filename in the main note with Obsidian wiki-link format, such as `[[ASAP.pdf]]`.

Use folder-aware Obsidian links in main paper notes:

* Methods: `[[Methods/{PaperName}/Actor-Critic|Actor-Critic]]`
* Concepts: `[[Concepts/{PaperName}/Policy|Policy]]`

## Main Paper Note

The main paper note should contain only paper-level summary and links to extracted notes:

```markdown
# Paper Title

PDF: [[PDF filename]]

## 一句话 takeaway

## Problem / 问题

## Core Idea / 核心想法

## Method in 3-5 Steps / 方法 3-5 步

1.
2.
3.

## Evidence / Experiments / 证据与实验

## 3 Things to Remember / 需要记住的 3 件事

1.
2.
3.

## Things Safe to Skip for Now / 现在可以先跳过的内容

## Related Methods / 相关方法

* [[Methods/{PaperName}/00_{PaperName}_Methods_Overview|{PaperName} Methods Overview]]
* [[Methods/{PaperName}/English Name|English Name]]

## Related Concepts / 相关概念

* [[Concepts/{PaperName}/English Name|English Name]]
```

Keep the main note in Chinese except for official English terms and link labels.

## Method Notes

A method is a reusable research method, training strategy, modeling approach, experimental design, evaluation method, baseline method, or implementation/training trick.

Examples include Actor-Critic, Domain Randomization, System Identification, Behavior Cloning, Diffusion Policy, Ablation Study, and Benchmark Construction.

Store each method note at `Methods/{PaperName}/{MethodName}.md` using this format:

```markdown
# English Method Name / 中文方法名

## Seen In / 出现于

English:
* [[Notes/{PaperName}|{PaperName}]], p. X / pp. X-Y / p. X, p. Y

中文：
* [[Notes/{PaperName}|{PaperName}]]，第 X 页 / 第 X-Y 页 / 第 X、Y 页

## Context / 语境

English:
Explain how this method appears in this paper. Say whether it is the core method, a used method, a baseline, a compared method, a training trick, an evaluation method, or background.

中文：
解释这个方法在本文中是怎么出现的。说明它是核心方法、实际使用的方法、baseline、被比较的方法、训练技巧、评估方法，还是背景方法。

## Detailed Explanation / 详细解释

English:
Give a more detailed beginner-friendly explanation. Explain what the method is, what problem it solves, why researchers use it, how it generally works, and how it is related to this paper.

中文：
用更详细、适合初学者的方式解释。说明这个方法是什么、它解决什么问题、研究者为什么用它、它大概怎么工作、它和这篇论文有什么关系。

## How It Works / 工作机制

English:
Explain the method in 3-6 concrete steps.

中文：
用 3-6 个具体步骤解释这个方法怎么工作。

## Why It Matters / 为什么重要

English:
Explain why this method is useful for reading future papers or understanding this field.

中文：
解释为什么这个方法对以后读论文或理解这个领域有用。

## Related / 相关

English:
* [[Related Method or Concept]]

中文：
* [[相关方法或概念]]
```

Rules for method notes:

* All sections must be bilingual English + Chinese.
* Do not make the explanation too short.
* Do not be vague.
* Keep it beginner-friendly.
* Do not use tables.
* Do not invent page numbers. If page number is unclear, write `page unclear / 页码不清楚`.
* When updating an existing method note, add the new paper under `Seen In` without duplicating the same paper/page entry.

## Per-Paper Method Overview

For each processed paper, create `Methods/{PaperName}/00_{PaperName}_Methods_Overview.md`.

Use this format:

```markdown
# {PaperName} Methods Overview / {PaperName} 方法汇总

## Paper / 论文

English:
* Main note: [[Notes/{PaperName}|{PaperName}]]
* PDF: [[{PDF filename}]]

中文：
* 主笔记：[[Notes/{PaperName}|{PaperName}]]
* PDF：[[{PDF filename}]]

## Method Map / 方法地图

English:
Group the methods by role:
* Core methods
* Used methods
* Training tricks
* Evaluation methods
* Baselines / compared methods
* Background methods

中文：
按照角色给方法分组：
* 核心方法
* 本文实际使用的方法
* 训练技巧
* 评估方法
* Baseline / 对比方法
* 背景方法

For each method, use bullet points like:

* [[Methods/{PaperName}/{MethodName}|MethodName]]: one-sentence English explanation.  
  中文：一句话中文解释。

## Reading Priority / 阅读优先级

English:
List which methods the user should understand deeply, roughly understand, or just recognize.

中文：
列出哪些方法需要深入理解，哪些大概理解即可，哪些只需要认识名字。

### Must understand / 必须理解
* ...

### Rough understanding is enough / 大概理解即可
* ...

### Recognize only / 认识名字即可
* ...
```

In `Notes/{PaperName}.md`, under `Related Methods / 相关方法`, place this overview link before individual method links:

```markdown
* [[Methods/{PaperName}/00_{PaperName}_Methods_Overview|{PaperName} Methods Overview]]
```


## Concept Notes

A concept is a term, background idea, field-specific vocabulary, assumption, object, or thing the user needs to recognize when reading papers.

Examples include Policy, Trajectory, Observation, Action Space, Proprioception, Reference Motion, Sim-to-real, Privileged Information, Reward, Loss, and Baseline.

Store each concept note at `Concepts/{PaperName}/{ConceptName}.md` using this format:

```markdown
# English Name / 中文名

## Seen In / 出现于

* [[PaperName]], p. X / pp. X-Y

## Context / 语境

English context sentence.
中文语境说明。

## Explanation / 解释

English beginner-friendly explanation.
中文初学者友好的解释。

## Related / 相关

* [[Related Method or Concept]]
```

When updating an existing concept note, add the new paper under `Seen In` without duplicating the same paper/page entry.

## Page Number Rules

Use page numbers for where each method or concept appears:

* If it appears once, write `p. X`.
* If it appears across consecutive pages, write `pp. X-Y`.
* If it appears in several separate places, write `p. X, p. Y, p. Z`.
* Do not invent page numbers.
* If the page number is unclear, write `page unclear`.

## Extraction Rules

Extract methodologies generously:

* Include methods used by the paper.
* Include methods mentioned in background or related work.
* Include baselines and compared methods.
* Include evaluation methods and training tricks.
* Include reusable experimental designs.
* Include useful concepts for understanding future papers.
* Do not include tiny one-off implementation details unless reusable.

Prefer methods over concepts when an item is a reusable procedure, training approach, evaluation method, baseline, or trick. Use concepts for vocabulary, objects, assumptions, metrics, fields, and background ideas.
