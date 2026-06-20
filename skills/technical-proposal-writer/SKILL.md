---
name: technical-proposal-writer
description: Create, analyze, and revise technical proposal responses for tenders, RFPs, procurement documents, and bid technical sections. Use when Codex needs to parse tender requirements, extract technical scoring points, build a response matrix, draft implementation/architecture/service/project-delivery sections, align a technical solution to evaluation criteria, review compliance risks, or prepare process files and final technical proposal deliverables. Do not use for pricing, legal bid documents, bid bonds, commercial quotations, or commercial negotiations except to flag technical dependencies and handoff items.
---

# Technical Proposal Writer

## Overview

Use this skill to turn a tender/RFP into a technical response package: requirement extraction, scoring-point mapping, technical solution outline, draft sections, review notes, and final deliverables. Keep the work centered on the technical proposal; commercial content is only tracked when it affects technical commitments.

## Default Workflow

1. Confirm scope: identify the project name, tender files, deadline, output format, and whether the user has a preferred output directory.
2. Set up the workspace: create a clean project folder for process files and final outputs.
3. Read the tender and produce a first-stage tender analysis document before drafting the full proposal. The analysis must list project overview, budget/scale clues, scoring modules, sub-scoring points, original-source evidence, reusable background excerpts, mandatory clauses, and open questions. Every substantive conclusion must include source file, page/section/clause when available, and a short original excerpt. See `references/tender-analysis.md`.
4. Stop after delivering the tender analysis document. Do not search the knowledge base, build the final response matrix, or draft the full technical proposal until the user explicitly confirms the analysis is correct and says to continue, such as "解析没问题，继续写技术方案".
5. Ask the user to confirm or supplement only the missing items discovered in the tender analysis, such as budget, project scale, page limit, knowledge-base path, or special writing priorities. Do not ask for these upfront if they can be extracted from the tender.
6. If a proposal knowledge base is available, search it for reusable templates, prior proposal sections, cases, diagrams, certifications, staffing descriptions, and standard wording before drafting. See `references/knowledge-base.md`.
7. Choose proposal depth from tender amount, scoring weight, page limits, and project complexity. See `references/proposal-sizing.md`.
8. Build a response matrix before drafting. Map every technical requirement and scoring point to a response status, original-source evidence, proposed answer, reusable source/evidence, owner, and risk.
9. Draft the technical proposal from the tender analysis, response matrix, selected knowledge-base materials, and the user's company/project materials.
10. Run compliance review: check missing responses, weak evidence, risky commitments, deadline conflicts, and format/submission requirements.
11. Produce final files plus process files the user can audit.

## Workspace Rules

Prefer the user's requested working root. If none is specified and filesystem permission allows it, use:

```text
D:\Codex\BidProposals\<project-slug>\
```

Use this structure:

```text
00-inputs\          Original tender files and user-provided source material
01-extraction\      Requirement extracts, scoring points, clause notes, tender analysis
02-matrix\          Technical response matrix and risk register
03-drafts\          Section drafts and revision history
04-review\          Compliance checks and open questions
05-final\           Final technical proposal files
_kb-cache\          Optional local copy/index of reusable knowledge-base materials
```

If the preferred directory is unavailable or not writable, use the current workspace and tell the user which path is being used. Do not silently scatter process files across unrelated folders.

## Inputs To Request

Ask only for missing inputs that materially affect the technical response. Useful inputs include:

- Tender/RFP document, clarification notices, drawings, appendices, and templates
- Existing technical方案, product brochures, architecture diagrams, certifications, case studies, and resumes
- Knowledge-base location: local folder, synced drive folder, GitHub repository, or exported archive
- Company standard wording for project management, implementation, operations, security, training, after-sales, and warranty service
- Tender budget/estimated amount and technical-score weight, if available
- Red lines: technologies not supported, delivery periods that cannot be promised, SLA limits, staffing limits, and prohibited claims
- Required output format: Word, PDF, Markdown, response matrix only, or section drafts

When the user has not provided company materials, draft with placeholders and a visible open-question list instead of inventing qualifications, certifications, project cases, headcount, or delivery commitments.

## Technical Proposal Boundaries

Include:

- Technical response to requirements and scoring criteria
- Overall solution, architecture, modules, integrations, security, performance, compatibility, and scalability
- Implementation plan, milestone schedule, project organization, staffing model, QA/testing, acceptance support, training, operations, maintenance, and risk controls
- Evidence mapping: cases, certificates, screenshots, test reports, product specs, resumes, and manufacturer letters when provided
- Clarification questions and technical assumptions

Exclude from drafting unless the user explicitly asks and provides the source:

- Prices, discount strategy, bid bond, payment terms, tax, legal commitments, commercial deviation sheets, and legal qualification documents
- Claims about awards, certifications, partnerships, cases, personnel, or delivery capacity not supported by supplied material

Flag commercial/legal dependencies when they affect technical content, for example: delivery period, warranty period, service response time, acceptance standards, liquidated damages tied to technical milestones, or required on-site staffing.

## Drafting Standards

Write in the tender's language and tone. For Chinese government/procurement technical proposals, prefer formal, specific, auditable wording. Use "响应", "满足", "优于", "拟采用", "确保", and "提供" only when supported by the matrix.

For every major section:

- Start with a direct response to the requirement or scoring point.
- Then explain the method, architecture, process, staffing, tools, controls, and deliverables.
- End with measurable evidence, acceptance criteria, or a verification method where possible.
- Avoid vague filler such as "advanced", "leading", "high quality", or "rich experience" unless paired with concrete proof.

## Reference Files

Read only the reference needed for the current task:

- `references/response-matrix.md`: Use when extracting requirements or creating the response matrix.
- `references/tender-analysis.md`: Use before full drafting to create the first-stage tender analysis document.
- `references/knowledge-base.md`: Use when connecting to or searching reusable prior proposal materials.
- `references/proposal-sizing.md`: Use when deciding proposal length, detail level, and section depth from tender amount and complexity.
- `references/technical-section-library.md`: Use when drafting or restructuring proposal sections.
- `references/review-checklist.md`: Use before final delivery or when asked to review a proposal.
- `references/company-materials.md`: Use when organizing reusable company cases, certificates, templates, and standard wording.

For final `.docx` output, use the available document-generation/editing capability and visually verify layout when possible. Keep the technical response matrix and review notes as separate process files so the user can trace each paragraph back to tender requirements.
