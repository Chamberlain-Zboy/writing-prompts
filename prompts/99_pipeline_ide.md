# IDE 写作流水线

## 总原则

1. 每轮只处理一个小目标（一个段落或一个表格）。
2. 每轮都引用对应 prompt 文件，不要靠自然语言临时描述规则。
3. 章节写作时，始终额外引用：
   - `prompts/90_style_anchor_no_dependency.md`
   - 对应章节模板（`templates/sections/*.tex`）

## 流程

1. 中译英初稿
   - 引用：`prompts/01_zh_to_en.md`
   - 若是某章节正文，再加：`prompts/90_style_anchor_no_dependency.md` + 对应 `templates/sections/*.tex`
   - 对话框输入：仅粘贴本段中文草稿（不要空消息）。

2. 英文深度润色
   - 引用：`prompts/06_polish_en_academic.md`
   - 同时引用：`prompts/90_style_anchor_no_dependency.md` + 对应章节模板
   - 对话框输入：上一步英文结果 + 你想保留的术语/句子（可选）。

3. 去 AI 味（投稿前）
   - 引用：`prompts/09_de_ai_en.md`
   - 对话框输入：当前英文段落。

4. 逻辑红线检查
   - 引用：`prompts/08_logic_check_en.md`
   - 对话框输入：当前段落或小节全文。

5. 摘要专门流程
   - 引用：`prompts/01_zh_to_en.md` 或 `prompts/06_polish_en_academic.md`
   - 同时引用：`prompts/90_style_anchor_no_dependency.md` + `templates/sections/0_abstract.tex`
   - 对话框输入：你的摘要内容。
   - 说明：推荐“引用榜样摘要 + 提示词 + 输入待处理文字”，而不是只引用文件不输入内容。

6. 表格与图题
   - 改实验分析文字：`prompts/14_experiment_analysis.md`
   - 图标题：`prompts/12_figure_title_en.md`
   - 表标题：`prompts/13_table_title_en.md`
   - 绘图类型推荐：`prompts/11_plot_recommendation.md`
   - 对话框输入：原始数据或中文描述。

7. 模板合规检查（最终）
   - 引用：`prompts/08_logic_check_en.md`
   - 同时引用：目标章节模板（必要时多节）
   - 对话框输入：你的最终文本，并补一句“只检查与模板写作规范冲突的硬问题，不做风格改写”。

## 你问的关键问题：在文件里写还是对话框写？

- 结论：两者都要。
- 文件引用用于“规则约束”和“风格锚点”。
- 对话框输入用于“本轮待处理内容”。
- 如果对话框什么都不写，LLM通常只能泛化建议，不能精准改写。
