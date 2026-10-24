# 优先论文架构

这是整篇SCI论文规划与重写的首选参考架构。保留用户给出的顺序和编号层级，不自行改成结果先行或另增独立章节。用户当前的明确目录与期刊强制格式优先；标题、摘要、关键词按期刊要求放在正文之前。

## 完整参考目录

```text
I. Introduction
   末尾：3—4条创新／贡献点

II. Related Works
II-A. MRI Reconstruction
II-B. Reference-based MRI Reconstruction

III. Method
III-A. Motivation
III-B. Framework
III-C. Specific Modules
III-C-1. Shallow Feature Extraction (SFE)
III-C-2. Low-Frequency Information Filtering (LFIF)
III-C-3. Dense Block (DB)
III-C-4. Reconstruction Module
III-C-5. Spatially Decoupled Block (SD-Block)
III-C-6. Feature Fusion
III-D. Algorithm
III-D-1. Super-resolution Reconstruction Algorithm
III-E. Loss Function
III-E-1. Spatial-decoupled Loss

IV. Experiment
IV-A. Implementation Details
IV-B. Ablation Study
IV-C. Comparative Study
IV-D. Comparison of the Number with State-of-the-art Methods

V. Conclusion
References
```

## 各章的论证职责

### I. Introduction

从任务需要收窄到具体困难，说明现有做法的限制，再提出核心洞察。末尾优先列3—4条贡献，每条回答“新增了什么、解决哪个问题、由什么证据支持”。避免所有条目都写成“设计一个模块”；方法、问题理解、验证发现和资源贡献只有确有区别时才分开。

若当前只能支持少于3条，不编造贡献或把一项拆开凑数；在写作说明中指出证据缺口，并给出最小补强方向。未完成实验不能作为已经实现的贡献。

### II. Related Works

II-A交代MRI重建的主要路线、假设和局限；II-B进一步聚焦参考信息如何引入、匹配和融合，以及失配、参考质量或信息冗余等与本研究真正有关的问题。不将“未评价”写成“不能解决”，不堆与本文决策无关的文献。

### III. Method

- **Motivation**：用事实、已有观察或明确假设解释为什么当前选择值得研究，与引言的问题对应，不重复背景综述。
- **Framework**：给出输入、输出、整体数据流和关键依赖，配合实际框架图说明各模块如何合作。
- **Specific Modules**：逐模块写困难、具体操作、公式与接口、设计理由及验证对应关系。概念出场顺序服从实际数据流，不能为了参考目录而写出不真实的执行顺序。
- **Algorithm**：用伪代码或明确步骤串联已经定义的模块，说明输入输出、训练／推理或迭代流程，不另造与方法正文不一致的算法。
- **Loss Function**：先定义目标、各损失项和权重，再解释Spatial-decoupled Loss或实际使用的对应目标。只写真实采用的损失，不因为模板存在此节就增加新损失。

### IV. Experiment

- **Implementation Details**：数据与划分、预处理、评价指标、实现环境、训练／推理设置、对照公平性和模型选择规则。
- **Ablation Study**：与贡献点和模块选择对应，说明控制了什么、观察到什么及有哪些混杂解释。材料中没有的消融标为待补，不能写成已完成。
- **Comparative Study**：在明确且相同的任务条件下报告总体定量与定性比较，保留失败案例、代价和不利指标。
- **IV-D规模对照**：原参考标题中的“Number”未指明数量对象。正文必须说明究竟是参数量、FLOPs/MACs、运行时间、显存或其他数量；指标口径、输入尺寸和测量条件需一致。可以在对象明确后采用更清楚的标题，如“Parameter Count and Computational Complexity Comparison”。不要把未实测的延迟写成已测，不能默认参数少就速度快或质量高。

讨论可以融入结果解释和结论；无期刊或用户要求时，不为了通用模板强加独立Discussion章。

### V. Conclusion 与 References

结论闭合引言提出的问题与3—4条贡献，提炼实际新增理解，不重复摘要、不增加新结果。文献只列已核实且正文真正使用的来源。

## 适配边界

此目录是优先参考，不是声称每篇论文已经采用这六个模块。MRI稿件尽量沿用层级和标题，但SFE、LFIF、DB、SD-Block、Feature Fusion及Spatial-decoupled Loss仅在真实方法中存在时保留；模块名称和数量与实际模型对齐。其他领域保持五章及方法的功能顺序，把MRI主题换成真实任务。没有参考输入、重建任务、可学习损失等内容时，不虚构相应设计。

全文重写先给出与现有材料对应的目录和贡献映射，再直接完成能可靠撰写的正文；不强制等待一轮审批。缺失材料在对应位置明确标注。用户只要求局部改写时不扩展范围。
