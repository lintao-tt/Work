# Knowledge Base

Use this reference when the user provides a local folder of reusable proposal materials.

The user may not have a formal knowledge base. Prefer a simple, practical folder workflow over requiring indexes, catalogs, tags, or database-style metadata.

## Expected Simple Layout

The most common layout is:

```text
投标资料库\
  通用模板\
    技术方案模板.docx
    实施方案通用版.docx
    售后服务方案.docx
    培训方案.docx
  历史投标材料\
    2024-某智慧园区项目\
      招标文件.pdf
      投标技术方案.docx
      澄清文件.pdf
    2025-某系统集成项目\
      招标文件.docx
      技术标.docx
```

Folder names may differ. Treat these as equivalent:

- 通用模板, 通用版本, 模板, 标准模板, 标准话术
- 历史投标材料, 历史项目, 已投项目, 投标案例, 过往标书

Do not require `INDEX.md` or `metadata/reusable-materials.csv`. Use them if present, but work from folder names and file names when they are absent.

## Inputs

The user can provide one path:

```text
资料库在：E:\投标资料库
```

Or two paths:

```text
通用模板在：E:\投标资料库\通用模板
历史投标材料在：E:\投标资料库\历史投标材料
```

Use the paths provided in the current request. Do not ask the user to create a config file.

## Retrieval Workflow

After the user approves the tender analysis document:

1. Extract search signals from `01-extraction/tender-analysis.md`:
   - project type
   - industry/domain
   - buyer type
   - system/module names
   - technical keywords
   - service/implementation requirements
   - budget/scale band
   - scoring modules and sub-scoring points
2. Search the generic template folder first for baseline structure.
3. Search the historical project folder for similar projects.
4. For each candidate historical project, inspect both its tender file and technical proposal when present.
5. Compare the historical tender with the current tender before reusing the historical proposal. Prefer materials whose tender requirements are similar, not just whose proposal wording sounds good.
6. Record candidate materials in `02-matrix/reuse-candidates.csv`.
7. Open only the most relevant files and sections.

## Similar Historical Project Matching

Score candidate historical project folders informally using these signals:

- Same or similar industry/domain
- Same buyer type, such as government, school, hospital, enterprise, state-owned enterprise
- Similar system/module names
- Similar project goals, background, or current-state problems
- Similar implementation, integration, data, security, service, training, or acceptance requirements
- Similar budget/scale band
- Similar scoring modules

Classify each historical project:

- high relevance: inspect and reuse structure/sections
- medium relevance: reuse selected paragraphs or section ideas
- low relevance: use only as writing reference
- reject: mismatched, outdated, or risky

## Reuse Rules

- Prefer structure and methods from old proposals; do not blindly copy paragraphs.
- Do not carry over old customer names, project names, dates, prices, contacts, contract terms, or confidential details unless the user explicitly confirms.
- Reuse generic templates for common sections such as implementation plan, training, after-sales service, quality assurance, testing, acceptance support, and risk management.
- Reuse historical proposals only after checking their tender context.
- If a historical proposal conflicts with the current tender, follow the current tender.
- If the old material contains unsupported claims, mark them as requiring confirmation.

## Output Artifacts

Create:

```text
02-matrix/reuse-candidates.csv
04-review/reuse-risk-notes.md
```

Recommended `reuse-candidates.csv` columns:

```text
id,source_folder,source_file,material_type,matched_reason,relevance,reusable_parts,risk_or_cleanup_needed,planned_use
```

The final technical proposal should not expose internal local folder paths.

## Optional Future Improvement

If the user's library grows large, suggest adding a simple `INDEX.md` later. Do not block the current task on it.
