# my_codex 阅读与更新约定

## 阅读顺序

先读 `README.md`，再用 `content-index.json` 的主题、核心问题、类型和摘要选择文档。读取适用边界后，继续检查所需正文、来源、版本和验证记录。无需预读无关主题。

This repository currently contains a documentation scaffold and no archived topics. Do not treat the template or empty registry as completed work.

## 未来新增与更新必须使用本格式

- 新的自有主题文档放在 `notes/` 或 `docs/` 下，使用 `templates/topic-note.zh-CN.md` 或适合内容的正文结构。
- 追加永久 `CDX-NNN`，不得复用或按排序重分已有编号。
- 在 `content-index.json` 维护双语标题与主题、文档类型、核心问题、2–3 个带标签摘要、适用边界和关联 ID。注册表是导航元数据的权威来源。
- `evidence_as_of` 只用原文明确的核查或截止日期，未知为 `null`。讨论、存档或记录日期使用 `content_date` 和 `content_date_kind`，不自动当作证据截止。
- `indexed_on`、`updated_on` 是格式日期，不能刷新历史事实。保留作者报告、假说、讨论、方案、本地结果与用户上下文的区别。
- 历史部署记录不等于当前在线状态；未运行的命令、流程和设计不改写为已完成结果。
- 更新正文或新增主题后运行 `python3 scripts/build_reading_index.py`，再运行 `python3 scripts/build_reading_index.py --check`。同一次提交包含正文、注册表和生成内容。
- 保留原路径、H1 与正文。生成器只维护自身标记区和身份元数据；不要手工修改生成摘要来绕过注册表。
- 模板、第三方许可证、代码资产和自动生成产物不作为虚构主题注册。

Preserve claim attribution, scope, and dates when summarizing. A passing format check is not execution, reproduction, deployment, or approval of the work described.
