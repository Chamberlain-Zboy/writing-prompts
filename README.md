# 写作 Prompt 拆分索引

以下文件由主 `README.md` 的 Part I 拆分得到，可在 IDE 对话中按需引用。

## Prompt 文件

- `01_zh_to_en.md`：中转英（翻译+学术润色）
- `02_en_to_zh.md`：英转中（LaTeX 到中文直译）
- `03_zh_rewrite.md`：中转中（中文学术重写，Word 场景）
- `04_shorten_en.md`：缩写（英文微缩）
- `05_expand_en.md`：扩写（英文微扩）
- `06_polish_en_academic.md`：表达润色（英文论文）
- `07_polish_zh_academic.md`：表达润色（中文论文）
- `08_logic_check_en.md`：逻辑检查（仅报致命问题）
- `09_de_ai_en.md`：去 AI 味
- `10_paper_arch_diagram.md`：论文架构图
- `11_plot_recommendation.md`：实验绘图推荐
- `12_figure_title_en.md`：生成图标题
- `13_table_title_en.md`：生成表标题
- `14_experiment_analysis.md`：实验分析
- `15_reviewer_audit.md`：Reviewer 视角审视

## 配套约束文件

- `90_style_anchor_no_dependency.md`：让 LLM 参考 `templates/sections/*.tex` 的文笔和用词，但避免过度依赖模板。
- `99_pipeline_ide.md`：IDE 中的高效使用流水线，含每步应引用哪些文件、对话框放什么内容。

## 最小使用法

1. 引用一个主任务 prompt（如 `06_polish_en_academic.md`）。
2. 若是论文正文写作，同时引用 `90_style_anchor_no_dependency.md` 和对应章节模板（如 `templates/sections/1_intro.tex`）。
3. 在对话框只贴本次待处理文本，不要把整篇论文一次性贴入。
