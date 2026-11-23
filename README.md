# my_codex 内容与工作记录

这个仓库采用同时便于人类浏览和模型检索的文档格式，用于后续新增主题、操作笔记、设计方案与工作记录。当前仅初始化阅读与维护结构，尚无归档主题。

This repository uses a shared human- and model-readable documentation format for future topics, guides, designs, and work records. The reading infrastructure is initialized; no topic documents have been archived yet.

<!-- BEGIN GENERATED RESEARCH INDEX -->
## 内容索引 · Content Index

暂无已归档主题。 · No topics have been archived yet.

<!-- END GENERATED RESEARCH INDEX -->

## 如何阅读 How to read

1. 从本页分类索引选择主题。完整的机器入口是 [content-index.json](content-index.json)。
2. 读取文档顶部的稳定编号、核心问题、带证据标签的摘要和适用边界。
3. 引用具体结论时继续读原正文、来源、版本、命令环境和验证记录。摘要用于定位，不能替代执行条件。

Use the index to select relevant documents, then read the full source conditions. English titles and topics are retrieval aids; most prose may remain in Chinese.

## 稳定身份与证据 Identity and evidence

- 新主题使用永久 `CDX-NNN` 编号，例如首个真实主题使用 `CDX-001`。编号一经归档不重新分配，路径保持稳定。
- `content-index.json` 是导航元数据的权威来源，包含双语标题、主题、文档类型、核心问题、摘要、边界与关联 ID。
- `evidence_as_of` 仅记录明确的资料核查或证据截止日期，未知为 `null`；内容记录日可另写 `content_date` 和 `content_date_kind`。
- `indexed_on` 是首次纳入阅读格式的日期，`updated_on` 是索引更新时间，二者都不代表重新验证了内容。
- 文档可以是普通笔记、操作指南、设计方案或实验记录。模板、占位内容和目录本身不计为已完成主题。

Evidence labels apply to specific claims, not an entire mixed document:

| 标签 Tag | 含义 Meaning |
|---|---|
| `[FACT]` | 可核查的文档或代码事实 / Verifiable documentation or code fact |
| `[AUTHOR_REPORT]` | 外部作者或评测方报告，保留归属 / Attributed external report |
| `[AUTHOR_HYPOTHESIS]` | 原作者提出的假说 / Attributed hypothesis |
| `[DISCUSSION]` | 分析、推断与类比 / Interpretation or analogy |
| `[PROPOSAL]` | 待实施或验证的方案 / Proposed work |
| `[LOCAL_RESULT]` | 实际记录的本地结果，保留环境和范围 / Recorded local result with scope |
| `[USER_CONTEXT]` | 用户提供的上下文 / User-provided context |
| `[AS_OF:YYYY-MM-DD]` | 明确的证据日期 / Explicit evidence cutoff |

不能把设计改写成已实施，也不能把历史运行记录改写成当前服务状态。模型引用时保留文档 ID、来源归属、日期与验证范围。

## 新增主题必须同步更新 Adding topics

1. 以 [主题模板](templates/topic-note.zh-CN.md) 为起点，在 `notes/` 或 `docs/` 下保存真实内容。
2. 在 `content-index.json` 中追加下一个未使用的 `CDX-NNN`，填写完整元数据、2–3 条带标签摘要及真实关联。
3. 运行 `python3 scripts/build_reading_index.py`，同步 README 索引与文档入口。
4. 运行 `python3 scripts/build_reading_index.py --check`，确认覆盖、编号、日期、链接关系和生成内容一致。
5. 将正文、注册表与生成内容保存在同一个提交中。现有主题有实质变化时，也同步核查摘要与证据日期。

The generator uses only the Python standard library. Future additions must update the registry and pass the consistency check in the same commit. The check validates documentation structure; it does not run the proposed work or certify its results.

模型维护约定见 [AGENTS.md](AGENTS.md)。本格式延续 [robot-rsi-research](https://github.com/ReadbytheBeach/robot-rsi-research) 的稳定 ID、双语导航、证据分层和同源生成方式。
