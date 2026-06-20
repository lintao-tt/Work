# Technical Proposal Writer Skills

This repository contains Codex and Claude Code skills for writing tender technical proposals.

## Install From Another Device

After pushing this folder to a GitHub repository, install the skill in Codex from:

```text
https://github.com/<owner>/<repo>/tree/main/skills/technical-proposal-writer
```

Example prompt in Codex:

```text
Use $skill-installer to install the skill from https://github.com/<owner>/<repo>/tree/main/skills/technical-proposal-writer
```

Restart Codex after installation so the skill is discovered.

## Claude Code Usage

For Claude Code, use the Claude skill at:

```text
.claude/skills/write-technical-proposal/SKILL.md
```

Typical prompt in Claude Code:

```text
/write-technical-proposal
Tender file: D:\Projects\A\招标文件.pdf
Knowledge base: E:\投标资料库
Budget: 300万（optional; the skill first tries to extract it from the tender）
Output folder: D:\Projects\A\技术方案输出
```

The Claude skill is self-contained and has its own `references/` folder, so it can work on an intranet/offline machine after this repository is copied there.

The skill works in two stages:

1. Produce a first-stage tender analysis document with project overview, budget/scale clues, scoring modules, sub-scoring points, original-source evidence, reusable tender excerpts, sizing recommendation, and open questions.
2. Stop and wait for explicit user approval, such as "解析没问题，继续写技术方案".
3. Draft the full technical proposal after approval, using the local knowledge base and the recommended page/detail standard.

The first-stage analysis must cite source file, page/section/clause when available, and a short original excerpt for each substantive conclusion.

## Repository Layout

```text
.claude/
  skills/
    write-technical-proposal/
      SKILL.md
      references/
knowledge-base-template/
skills/
  technical-proposal-writer/
    SKILL.md
    agents/openai.yaml
    references/
```

## Knowledge Base

Use `knowledge-base-template/` as the starting structure for a private online proposal knowledge base. Keep historical bids, reusable templates, cases, certificates, diagrams, product docs, and resumes there.

Recommended setup:

- Keep this skill repository lightweight.
- Put real historical proposal materials in a private repository or synced drive.
- Maintain `INDEX.md` and `metadata/reusable-materials.csv` so Codex can find reusable content before drafting.
- Do not publish confidential tender/client files in a public repository.

## Notes

- Use a private GitHub repository if the skill includes company-specific proposal methods, templates, or source material.
- Keep client tender documents, quotes, qualifications, and project files outside this repository unless they are intentionally shared.
- The skill defaults proposal process/output work to `D:\Codex\BidProposals\<project-slug>\` when that path is available and writable.
