# taskiller

万能学术交付 skills。把一整个项目文件夹交给 Codex，让它先读清楚任务，再推进到可交付文件。

## 这是什么

很多学术任务不是“写一篇文章”这么简单。真实情况通常是：brief 一份、rubric 一张截图、旧稿一个、导师反馈几段、参考文献一堆、数据表一个，最后还要求交 Word、PPT、PDF、代码附件或整理好的 submission。

`taskiller` 这套 skills 的入口是 `runpro`。它做的不是直接开写，而是先把项目读明白：

- 最后到底要交什么文件
- rubric 和 brief 里有哪些硬要求
- 导师反馈哪些必须改
- 现在材料够不够
- 哪些地方不能硬编
- 最后交付文件应该放在哪里

确认范围后，再进入执行。

## 主要 skills

### runpro

项目文件夹执行器。把 brief、rubric、旧稿、反馈、参考文献、截图、数据表都放进一个文件夹，然后调用 `runpro`。

它会先做 intake、可行性判断和需求锁定，再按项目类型走不同路线：报告、论文、PPT、数据分析、代码项目、混合交付物都可以分开处理。

### checkpro

交付前的学术审查。重点看 rubric 覆盖、论证质量、引用是否支撑说法、结构是否回答题目，而不是只看格式好不好看。

### replacewords

把改好的文字回填进原 DOCX，尽量保留原来的字体、字号、段落格式、引用格式和文档结构。

### pptpro

把报告、论文、阅读材料或展示内容做成可编辑 PPTX。目标是像认真做过的汇报，不是把文字塞进模板。

### final-delivery-clean

交付前清理过程性文字。把 workflow 说明、内部备注、文件路径、状态记录这类不该出现在最终文件里的东西删掉。

### zinxtick

通用表情包制作 skill。输入一个角色或物品，选择风格和主题后，生成一套适合提交到微信表情开放平台的表情包素材。

## 一个典型用法

```text
project-folder/
├── brief.pdf
├── rubric.png
├── draft.docx
├── supervisor-feedback.txt
├── references/
└── data.xlsx
```

然后让 Codex 调用：

```text
runpro
```

`runpro` 会先还原任务和交付要求。确认后，它会创建工作区：

```text
runpro_workspace/
├── 10_analysis/
├── 20_working/
├── 20_drafts/
├── 30_tools/
└── submission/
```

真正要交的最终文件只放在 `submission/`。

## 不是什么

- 不保证外部评分结果。
- 不会在核心材料缺失时假装已经完成。
- 不应该把没有来源支撑的事实硬编进去。
- 不会把过程文件混进最终 submission。

这套 workflow 的目标是提高学术交付的可靠性：先把任务读清楚，再做，再查，最后交干净文件。

## 安装

熟悉 Codex skills 的话，把 `skills/` 里的目录放进本机 Codex skills 目录即可。

```bash
cp -R skills/* ~/.codex/skills/
```

然后在 Codex 里调用对应 skill，例如：

```text
runpro
```
