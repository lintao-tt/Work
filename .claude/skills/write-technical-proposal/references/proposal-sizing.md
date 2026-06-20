# Proposal Sizing

Use this reference to adjust technical proposal length and detail level according to tender amount, page limits, technical-score weight, buyer expectations, and project complexity.

## Inputs

Collect these when available:

- Tender amount or estimated budget
- Technical score weight and scoring table detail
- Required page limit or file size limit
- Project complexity: low, medium, high
- Delivery risk: low, medium, high
- Buyer type: government, state-owned enterprise, enterprise, school/hospital, private company
- Required demonstrations, diagrams, resumes, cases, certificates, or appendices

If tender amount is unknown, size the proposal from technical-score weight and requirement complexity.

## Default Size Bands

Adapt the thresholds to the user's industry when better local rules are known.

| Tender amount | Suggested depth | Typical technical volume |
| --- | --- | --- |
| Under 500k RMB | concise | 15-30 pages |
| 500k-2m RMB | standard | 30-60 pages |
| 2m-10m RMB | detailed | 60-120 pages |
| Over 10m RMB | comprehensive | 120+ pages, often with appendices |

Always obey tender page limits over these defaults.

## Depth Rules

### Concise

Use when amount is small, scope is clear, or page limit is tight.

- Keep solution architecture to 1-2 diagrams or tables.
- Use short requirement-response paragraphs.
- Focus on mandatory requirements, high-score items, delivery plan, acceptance, and service.
- Avoid long generic company introductions.

### Standard

Use for common technical proposals.

- Include project understanding, overall solution, requirement responses, implementation, testing, training, service, risk, and deliverables.
- Use tables for requirement mapping, milestones, staffing, and service response.
- Include selected cases and certificates only when scoring points reward them.

### Detailed

Use when amount, score weight, or complexity is high.

- Expand architecture, data/interface design, security, performance, deployment, migration, testing, acceptance, and service governance.
- Add diagrams, detailed milestone plans, role/responsibility tables, risk register, quality controls, and evidence mapping.
- Use prior-bid material only after adapting it to current tender requirements.

### Comprehensive

Use for large or strategic projects.

- Treat the proposal as a full delivery plan.
- Include executive technical summary, methodology, work breakdown, governance, detailed design, implementation, testing, cutover, operations, SLA, emergency response, training, documentation, and appendices.
- Separate detailed evidence into appendices when the main text would become hard to read.

## Scoring Override

Increase depth when:

- Technical score weight is high.
- Scoring table awards points for detailed methods, cases, diagrams, team roles, SLA, security, testing, or risk controls.
- The tender asks for demonstrations, proof materials, or detailed implementation plans.
- The buyer has strict acceptance, migration, integration, or data/security requirements.

Decrease depth when:

- Page limit is tight.
- Technical scoring is low and format compliance matters more.
- Requirements are simple and over-writing may make the proposal look unfocused.

## Practical Output Target

Before drafting, write a one-page sizing note:

```text
Proposal depth:
Target pages:
Reason:
Sections to expand:
Sections to keep concise:
Knowledge-base material to reuse:
Open questions:
```

Keep this note in `01-extraction/proposal-sizing-note.md`.
