# Response Matrix

Use a response matrix before writing long-form technical proposal text. The matrix prevents missed clauses and makes the final draft auditable.

## Recommended Columns

- `id`: Stable requirement identifier, such as `T-001`.
- `source`: Tender file name, page, section, or clause number.
- `requirement`: Exact or summarized requirement.
- `scoring_module`: Major scoring module when the row comes from an evaluation table.
- `scoring_point`: Detailed sub-scoring point or scoreable clause.
- `score`: Points available, if stated.
- `original_excerpt`: Short original tender excerpt that supports the requirement or scoring point.
- `type`: Mandatory, scoring, technical spec, service, schedule, acceptance, format, or clarification.
- `priority`: High, medium, low. Mandatory and high-score items are high.
- `response_status`: Comply, exceed, partially comply, clarify, unable, or unknown.
- `technical_response`: Short proposed answer.
- `evidence`: User-provided proof, case, certificate, product spec, screenshot, test report, or placeholder.
- `proposal_section`: Where the final text should appear.
- `risk_or_gap`: Missing proof, risky promise, conflict, ambiguity, or owner question.
- `owner`: Person/team expected to confirm.

## Extraction Rules

Extract requirements from:

- Qualification or scoring tables that mention technical capability, project team, cases, implementation plan, service plan, demonstrations, or documentation.
- Technical specifications, functional requirements, non-functional requirements, drawings, appendices, and data/interface requirements.
- Acceptance, training, operation, maintenance, warranty, and service-response clauses.
- Submission format requirements for the technical volume: naming, page limit, signatures, stamps, binding, catalog order, and file format.

Do not bury uncertainty. If evidence is missing, set `response_status` to `unknown` or `clarify` and add an owner question.

## Drafting From The Matrix

For each final section, group matrix rows by proposal theme. Make the first sentence of a paragraph directly answer the strongest matching requirement. Use the evidence column to decide whether the paragraph can make a firm promise or should use an assumption/placeholders.

When a requirement is partially met, do not hide the gap. Propose a mitigation, clarification question, or alternative technical path.
