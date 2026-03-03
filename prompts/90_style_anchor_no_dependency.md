# 模板文笔参考约束（防模板依赖）

将本文件与主任务 prompt、对应章节模板一起引用，用于约束 LLM。

## 目标

在不复制模板内容的前提下，学习其文笔、句式节奏、术语风格与段落组织方式。

## 章节映射

- Abstract：`templates/sections/0_abstract.tex`
- Introduction：`templates/sections/1_intro.tex`
- Related Work：`templates/sections/2_relatedworks.tex`
- Method：`templates/sections/3_method.tex`
- Experiment：`templates/sections/4_experiment.tex`
- Conclusion：`templates/sections/5_conclusion.tex`

## 强约束

1. 只参考风格，不复用内容：
   - 不得复用模板中的具体结论、数字、实验设定、方法名称、图表描述。
2. 只学写法，不学题材：
   - 不要被模板研究主题绑定，必须以我当前给出的研究内容为主。
3. 结构借鉴而非复刻：
   - 可借鉴段落推进顺序，但不得按模板逐段改写或镜像复现。
4. 术语一致性优先：
   - 以我提供的术语表与命名为最高优先级；若模板术语冲突，忽略模板写法。
5. 不编造信息：
   - 若我的输入缺少关键事实，明确标注缺口，不得用模板内容补空。

## 输出前自检

- 是否出现了模板中的专有名词或数字被直接搬用？
- 是否出现“换壳复写”迹象（句子骨架与模板高度同构）？
- 是否每一句都能追溯到我的输入材料而不是模板？

若任一项为“是”，先重写再输出。
