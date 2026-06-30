# Paper Learning Compass 🧭

**Read papers lightly, accumulate methods deeply.**
**轻量读论文，深度积累方法。**

Paper Learning Compass is a Codex skill that converts research papers into Obsidian-friendly notes.

它会把一篇论文 PDF 自动整理成：

* `Notes/`：论文主笔记
* `Methods/`：论文中出现的方法与方法汇总
* `Concepts/`：论文中涉及的概念与术语

---

## What It Solves / 解决什么问题

Many beginners can understand a paper once, but the knowledge is hard to reuse later.

很多时候论文当下读懂了，但方法、概念和术语没有沉淀下来，下次看到还是像第一次见。

This skill helps with:

1. **Reading priority / 阅读优先级**
   Identify the main storyline and mark details safe to skip for now.
   提炼论文主线，并标出当前可以暂时跳过的细节。

2. **Method accumulation / 方法积累**
   Extract methods, baselines, training tricks, and evaluation methods into separate notes.
   把方法、baseline、训练技巧和评估方法单独整理成笔记。

3. **Clear structure / 清晰分类**
   Separate paper notes, method notes, and concept notes.
   把论文主笔记、方法笔记和概念笔记分开存放。

4. **Bilingual understanding / 中英双语理解**
   Keep English terms, Chinese explanations, page numbers, and paper context together.
   同时保留英文术语、中文解释、页码和原文语境。

---

## Output Structure / 输出结构

```text
PaperVault/
  Papers/
    Your Paper.pdf
  Notes/
    Your Paper.md
  Methods/
    Your Paper/
      00_Your Paper_Methods_Overview.md
      Method A.md
  Concepts/
    Your Paper/
      Concept A.md
```

---

## How To Use / 使用方法

1. Create an Obsidian vault with:

```text
Papers/
Notes/
Methods/
Concepts/
```

2. Put your PDF into `Papers/`.

3. Run Codex in the vault and call:

```text
Use $paper-learning-compass.

Process this paper:

PDF:
Papers/your-paper.pdf

Paper name:
Your Paper Name

Create the outputs in the current Obsidian vault.
```

---

## Do Not Upload / 请勿上传

This repo is for the skill only. Do not upload private materials:

这个仓库只放 skill 本体，请不要上传私人材料：

```text
PaperVault/
Papers/
Notes/
Methods/
Concepts/
.obsidian/
private PDFs
personal notes
```

---

## License

MIT License

