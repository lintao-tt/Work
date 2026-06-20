---
name: write-technical-proposal
description: Write tender technical proposals in Claude Code. Use when the user provides a tender/RFP file and optionally a local folder of historical bids, reusable templates, cases, product documents, diagrams, resumes, certificates, or standard wording. The skill extracts requirements, searches reusable local materials, sizes proposal depth by budget and scoring weight, drafts the technical proposal, and produces response matrices and review notes. This is for technical proposals, not pricing or commercial/legal bid documents.
---

# Write Technical Proposal

Use this Claude Code skill to generate or revise technical proposal documents for tenders/RFPs. It is designed for intranet or offline work where reusable proposal materials live in local folders.

## Expected Invocation

The user should provide paths in the prompt when possible:

```text
/write-technical-proposal
Tender file: D:\Projects\A\招标文件.pdf
Knowledge base: E:\投标资料库
Budget: optional; extract from tender first
Output folder: D:\Projects\A\技术方案输出
```

If paths are missing, ask only for the missing path that blocks the work. Do not require a persistent config file when the user gives paths in the prompt.

## Workflow

1. Confirm inputs: tender file/folder, local knowledge-base folder if provided, output folder, deadline, and required output format. Do not require budget upfront if it can be extracted from the tender.
2. Create a project workspace under the requested output folder. If no output folder is supplied, create one beside the tender file when allowed.
3. Read the tender and produce the first-stage tender analysis document before drafting. Include project overview, budget/scale clues, scoring modules, sub-scoring points, original-source evidence, reusable background excerpts, mandatory clauses, and open questions. Every substantive conclusion must include source file, page/section/clause when available, and a short original excerpt. Read `references/tender-analysis.md`.
4. Stop after delivering the tender analysis document. Do not search the knowledge base, build the final response matrix, or draft the full technical proposal until the user explicitly confirms the analysis is correct and says to continue, such as "解析没问题，继续写技术方案".
5. Ask the user to confirm or supplement only missing items found in the tender analysis, such as budget, project scale, page limit, knowledge-base path, or special writing priorities.
6. Read `references/proposal-sizing.md` and choose proposal depth from budget, scoring weight, page limits, and complexity.
7. If a knowledge-base path is provided, read `references/knowledge-base.md`, inspect its index/catalog if present, then search only relevant folders/files.
8. Build a response matrix before drafting. Map each technical requirement and scoring point to response status, source evidence, reusable material, risk, and final proposal section.
9. Draft the technical proposal in the tender's language and required order.
10. Produce process files: tender analysis, sizing note, tender keywords, reuse candidates, response matrix, risk/open-question list, and final draft.
11. Review compliance before final delivery.

## Workspace Layout

Use this layout in the output folder:

```text
00-inputs\          Tender files and user-provided source material
01-extraction\      Tender analysis, tender keywords, scoring points, sizing note
02-matrix\          Response matrix, reuse candidates, risk register
03-drafts\          Draft sections and revision history
04-review\          Compliance checks and open questions
05-final\           Final proposal files
_kb-cache\          Selected knowledge-base extracts only
```

Keep historical material read-only. Copy selected excerpts or indexes into `_kb-cache` only when useful for traceability.

## Local Knowledge Base

The knowledge base can be any readable local folder. The user may have a simple two-folder layout:

```text
E:\投标资料库\
  通用模板\
  历史投标材料\
```

Each historical project folder usually contains its tender file and corresponding technical proposal:

```text
E:\投标资料库\历史投标材料\
  2024-某智慧园区项目\
    招标文件.pdf
    投标技术方案.docx
```

Do not require `INDEX.md` or CSV. If no index exists, search folder names and file names, compare historical tender files with the current tender, then inspect likely matching technical proposals.

Do not invent cases, certifications, performance numbers, staffing commitments, dates, or customer names. If proof is missing, mark it as an open question.

## Proposal Depth

Use budget as a sizing signal:

- Under 500k RMB: concise, usually 15-30 pages.
- 500k-2m RMB: standard, usually 30-60 pages.
- 2m-10m RMB: detailed, usually 60-120 pages.
- Over 10m RMB: comprehensive, usually 120+ pages or main document plus appendices.

Override this when the tender has strict page limits or when technical score weight is unusually high/low. Always obey tender page limits over default page targets.

## Boundaries

Include technical solution, architecture, requirement response, implementation, testing, acceptance, training, operations, service, risk controls, and technical evidence.

Do not draft pricing, bid bond, tax/payment terms, legal deviations, commercial negotiations, or qualification originals unless the user explicitly asks and provides sources. Flag these as handoff items when they affect technical commitments.

## References

Read only what is needed:

- `references/knowledge-base.md`: local material reuse and source tracing.
- `references/tender-analysis.md`: first-stage tender parsing, scoring breakdown, original excerpts, and sizing handoff.
- `references/proposal-sizing.md`: budget/depth rules.
- `references/response-matrix.md`: requirement extraction and matrix fields.
- `references/technical-section-library.md`: technical proposal section patterns.
- `references/review-checklist.md`: final compliance review.
- `references/company-materials.md`: company cases, certificates, templates, and standard wording.
