# Tender Analysis

Use this reference before drafting the full technical proposal. The first-stage output must be a small analysis document that helps the user understand the tender and confirm the writing strategy.

This is a gated stage. After producing the analysis document, stop and wait for explicit user approval before drafting the full technical proposal.

## Purpose

Do not start the full proposal immediately. First parse the tender and produce:

- Project overview and background extracted from the tender
- Tender budget, estimated amount, project scale, deadline, page limits, and submission constraints when present
- Scoring structure: major scoring modules and detailed sub-scoring points
- Original-source mapping: clause/page/section references and short excerpts
- Reusable tender text: project status, background, construction goals, scope, pain points, and buyer requirements that can be quoted or paraphrased
- Proposal sizing recommendation: target page range and detail level
- Writing strategy: sections to expand, sections to keep concise, evidence needed, and knowledge-base search keywords
- Open questions that require user confirmation

Every substantive conclusion must be traceable. Include the source file name, page number when available, section/clause number when available, and a short original excerpt. If page numbers are unavailable, use the nearest heading, clause number, table title, or paragraph anchor.

## Required Output File

Create:

```text
01-extraction/tender-analysis.md
```

Use this structure:

```text
# 招标文件解析

## 1. 项目基本信息
- 项目名称:
- 招标人/采购人:
- 预算/最高限价:
- 项目规模:
- 工期/服务期:
- 技术标页数/格式限制:
- 投标截止/关键时间:

## 2. 项目背景与现状摘录
| 来源位置 | 原文摘录 | 可用于方案的位置 | 使用建议 |

## 3. 评分大模块
| 模块 | 分值 | 关注点 | 对技术方案的影响 |

## 4. 小得分点拆解
| 编号 | 所属模块 | 小得分点 | 分值 | 原文依据 | 可摘录内容 | 响应策略 | 需要材料 |

## 5. 必须响应条款
| 编号 | 条款来源 | 要求 | 风险等级 | 响应建议 |

## 6. 方案篇幅与详细程度建议
- 建议深度:
- 目标页数:
- 判断依据:
- 重点展开:
- 简写处理:

## 7. 知识库检索关键词
| 主题 | 关键词 | 目标材料类型 |

## 8. 待确认问题
```

Add this approval gate at the end:

```text
## 9. 下一步确认

我已完成招标文件解析。请复核以上出处、评分点和篇幅建议。

只有在你明确回复类似“解析没问题，继续写技术方案”后，我才会继续检索资料库、生成响应矩阵并编写完整技术方案。
```

## Citation Rules

Use source labels consistently:

```text
[来源: 招标文件.pdf, 第 23 页, 第三章 评审办法, 技术方案评分表]
```

If page numbers are unavailable:

```text
[来源: 招标文件.docx, 章节: 采购需求/项目背景]
```

For tables, use:

```text
[来源: 招标文件.pdf, 第 31 页, 表: 技术评分标准]
```

For each project background excerpt, scoring point, mandatory clause, sizing basis, and risk conclusion, include one of these source labels plus a short excerpt. Do not write unsupported conclusions as facts; mark them as "待确认" or "推断".

## Extraction Rules

Prioritize scoring tables and technical evaluation methods. When the tender contains a scoring table:

1. Treat each top-level scoring category as a major module.
2. Treat every scoreable sentence, bullet, or clause under that category as a sub-scoring point.
3. Keep the original score when present.
4. Preserve exact tender wording for short phrases that affect scoring.
5. Note when a scoring point has no clear original background text and must be answered from company materials.
6. For every sub-scoring point, include the original source label and an excerpt short enough for review.

For project background and current status, search sections with names like:

- 项目背景
- 项目概况
- 建设背景
- 建设内容
- 现状分析
- 采购需求
- 技术要求
- 服务要求
- 项目目标
- 总体要求

Use short excerpts only. Do not paste long tender passages into the final answer unless the user asks for a working extract file.

## Sizing Rules

If the tender includes budget or maximum price, use it as the first proposal-depth signal. If not, infer scale from:

- number of systems/modules
- implementation duration
- integration/data/security complexity
- technical score weight
- amount of required documentation
- buyer type and acceptance strictness

Then read `proposal-sizing.md` and recommend a target range.

If budget is missing, write:

```text
Budget not found in tender. Initial target based on complexity: 40-60 pages. Ask user to confirm budget before final drafting.
```

## Handoff To Full Draft

After the tender analysis is complete:

1. Stop and ask the user to review the analysis document.
2. Do not search the knowledge base, build the final response matrix, or draft the full proposal yet.
3. Continue only after the user explicitly confirms the analysis and instructs drafting to continue.
4. Then ask the user to confirm key missing items only if they materially affect drafting.
5. Search the knowledge base with the keywords from the analysis.
6. Build the technical response matrix from the scoring-point table and mandatory clauses.
7. Draft the full proposal to match the recommended depth and score priorities.
