# 叙事型SCI写作 · narrative-sci-writing

把研究思路、论文草稿和真实实验材料组织成“问题 → 关键选择 → 验证证据 → 结论意义”的学术叙事。支持中文构思、英文写作及忠实翻译，既能发展早期想法，也能直接重写已有章节。

## 使用

在Codex中调用：

```text
请使用 $narrative-sci-writing，依据这份稿件和真实结果，提炼一句话主线，指出最重要的两个论证问题，并直接重写引言。
```

其他常用请求：

- “只重写摘要；没有提供的数值标为待补，不延伸审查其他章节。”
- “这个想法与已有方法相似，请先寻找可保留的价值，再提出最小验证方案。”
- “从我给的三篇全文提取引言和讨论的写法，再据此改稿，不复制句子。”
- “忠实翻译确定的中文稿，不升级因果、泛化或显著性主张。”

## 安装到另一台电脑

GitHub账号需要具有本私有仓库的读取权限。将仓库克隆到Codex技能目录；目标目录已存在时先检查，不覆盖原有技能。

macOS / Linux：

```sh
mkdir -p ~/.codex/skills
git clone https://github.com/qihaoxu0/narrative-sci-writing.git ~/.codex/skills/narrative-sci-writing
```

Windows PowerShell：

```powershell
git clone https://github.com/qihaoxu0/narrative-sci-writing.git "$env:USERPROFILE\.codex\skills\narrative-sci-writing"
```

若自行配置了`CODEX_HOME`，安装到该位置的`skills/narrative-sci-writing`。安装后在新会话中调用。技能本身不依赖Python包；阅读文档或查阅论文使用宿主已有工具。

## 文件

- `SKILL.md`：触发条件、论证主线、问题分级、交付规则。
- `references/section-guide.md`：按需读取的标题至结论写法。
- `references/evidence-and-style.md`：证据对应、参考写法提取与中英一致性。
- `agents/openai.yaml`：Codex界面名称与默认调用提示。

## 优化原则

故事感不等于虚构研究过程；肯定语气不等于删除科学限定。摘要的四种功能不是四句话硬模板，图1也不必总是框架图。既不因相似工作轻率否定方向，也不包装重复、负结果或未验证结论为创新。优先解决影响主线的问题，对局部问题给出最小修正，不反复开启已解决质疑。

本仓库基于用户提供的写作要求整理，不包含用户论文、原始实验数据或GitHub凭据。结构校验不等于已在真实论文上验证写作效果。
