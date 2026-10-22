# Parallel Review and Scoring Protocol

Use this protocol after the parent has generated and rendered the complete report. The parent remains the sole writer and file editor; subagents only inspect existing materials and return reviews. The goal is a corrected delivery from one user request, not an unreviewed first draft or a guaranteed teacher grade.

## Prepare one consistent review package

The parent provides:

- The task sheet, school template, user instructions, and teacher's rubric if available.
- The user's material explanations and underlying code, measurements, photographs, or result records.
- The exact saved DOCX and matching PDF/page images, identified by a parent-assigned revision identifier or file hash.
- A map of requirements to report locations and supporting evidence.
- An inventory of body tables, figures, formulas, and source-code listings, with cover tables identified separately. Do not infer exceptions to explicit user formatting rules from conflicting template defaults.

Prepare needed exports, XML extracts, and inspection images in the existing generation folder before delegation. Reviewers must not generate files, render, modify scripts, or request edit permissions. If material is inaccessible or more extraction is needed, return the need to the parent. Actual platform restrictions still apply.

All initial reviewers inspect the same saved revision. Do not mix scores from different revisions or present an earlier review as verification of a later file.

## Launch independent reviewers concurrently

Normally start these three reviewer subagents in parallel, fitting the available slots:

1. **Experiment and evidence reviewer:** Task coverage, technical accuracy, implementation explanations, measurement provenance, analysis, and conclusions. Check that code or simulations are not misrepresented as hardware observations.
2. **Formatting and visual reviewer:** Template compliance, black headings, actual fonts and sizes, every body table's effective three-line borders, figures and adjacent-page flow, rendered equations, captions, contents fields, page numbers, and every source-code listing against [its dedicated specification](report-spec.md#source-code-listings). Use both document structure and actual page images.
3. **Student-language reviewer:** Read all prose in context for generic or inflated narrative, repeated stock paragraphs, conversational assistant wording, banned constructions, unsupported personal experiences, and conclusions lacking experiment-specific substance. Check comments that are part of the report or authorized review scope without modifying source code.

Tell each reviewer to evaluate honestly against the supplied criteria and evidence. Do not supply a desired score, ask them to certify full marks, or expose other reviewers' conclusions before their initial reviews. Domain assignments do not prevent reporting a serious cross-domain error.

With fewer slots, run at least two reviewers concurrently when possible and combine domains without omitting checks; complete any remaining review in the next available slot. If independent review is unavailable, the parent performs separate domain passes and reports the limitation. Do not ask the user for routine scheduling decisions or claim a concurrency level that was not available.

## Score against evidence

Use the teacher's supplied rubric exactly where applicable. If none exists, use this provisional internal rubric:

| Criterion | Points | Primary reviewer |
| --- | ---: | --- |
| Task coverage and technical correctness | 25 | Experiment and evidence |
| Evidence, results, analysis, and supported conclusions | 20 | Experiment and evidence |
| Template, typography, structure, fields, equations, and source-code listings | 20 | Formatting and visual |
| Three-line tables, figures, captions, and page flow | 20 | Formatting and visual |
| Natural student prose and prohibited-expression compliance | 15 | Student language |
| Total | 100 | Parent consolidates |

Each reviewer reports earned points and the maximum for assigned criteria: normally 45, 40, and 15. The parent combines these distinct criteria into one 100-point assessment; do not average three differently scoped scores. With a teacher rubric or combined roles, state ownership of each criterion before scoring so that no criterion is omitted or counted twice.

Before initial scoring, the parent maps each broad criterion to applicable requirement-level subitems and explicit weights that sum to its maximum. Share the same mapping with all reviewers; record partial-credit rules and deduction reasons. Do not change weights after seeing defects to make the total higher. Some language and layout judgments remain qualitative; support them with specific passages or pages and distinguish genuine requirement violations from preferences.

For each applicable requirement, mark `verified`, `failed`, or `unverified` and give its location and evidence. Mark `not applicable` only with a reason grounded in the actual experiment; do not use it to excuse a required but missing result. For the provisional rubric, exclude genuinely inapplicable subitems and redistribute their weight within the same criterion, stating the change. Do not alter a teacher rubric without direction.

Do not award points for unverified requirements. If unknowns materially affect the total, report the assessment as provisional, state earned and unassessed points separately, and do not call it a fully verified score. A high total cannot override a mandatory requirement failure.

User-approved placeholders remain unverified evidence requirements, not verified results or automatic full-credit items.

An internal 100/100 is possible only after all applicable requirements have evidence and no known deduction remains. Label it as an internal rubric result, not a predicted or guaranteed teacher grade. Never put a score or quality endorsement in the report body.

## Required review response

Return the following to the parent in the review message, without writing review files:

- Reviewed revision identifier and assigned scope.
- Criterion scores, maxima, evidence, and deductions; identify unassessed items separately.
- Findings with a page, heading, paragraph, table, figure, equation, or code location.
- The exact violated instruction or technical concern, supporting observation, and practical correction suggestion.
- Severity: blocking, substantive, or minor. Distinguish a requirement violation from an optional stylistic preference.
- Any inaccessible material, missing evidence, or additional parent-generated inspection material needed.
- A verdict: corrections required, verified within assigned scope, or unable to verify.

Merely saying "looks good", "all requirements met", or "full marks" is not a review. For language findings, cite the specific passage and explain the defect; do not use an AI-detector label as evidence.

## Parent correction and recheck loop

1. Consolidate findings, resolve duplicates, and compare disputed points with the task sheet, template, and evidence. Record accepted corrections and reasons for rejecting unsupported suggestions in the generation workspace.
2. Correct the existing prose, generator, or layout. Fix every affected object, including repeated errors across all tables or headings; do not repair only the example a reviewer noticed.
3. Regenerate the same final DOCX, export it, and re-render affected pages and neighboring pagination. If a change alters page count or broad document flow, regenerate the full page set.
4. Supply the new revision and relevant artifacts to the responsible reviewers for targeted rechecks. Reviewers verify the correction, related criteria, and regressions; they do not automatically raise a score because the parent says a fix was applied.
5. Reconcile scores for the latest revision and perform a final full-page sweep and requirement check before delivery. Carry forward unaffected verified findings only when their evidence still applies; do not imply all reviewers reread the final file if they did not.

Continue while concrete, fixable defects remain. Avoid endless full rescoring for its own sake. If the same correction fails repeatedly, change the implementation or rendering approach and inspect the actual cause rather than repeating an ineffective edit. If a real blocker remains, complete unaffected work and disclose the unresolved requirements; do not fabricate evidence, soften the rubric, or ask the user to rediscover routine defects.

## Acceptance and handoff

Mandatory criteria include black titles/headings, compliant body-table rules, readable typeset formulas, sensible figure sizing and page flow, task coverage, evidence integrity, and absence of prohibited assistant-style reporting. Missing required data, failed mandatory checks, and unverified mandatory items prevent an unconditional completion or full-score claim.

The parent delivers the single final DOCX in the established project root. Keep scoring sheets, evidence maps, review notes, PDFs used only for inspection, and page images in the generation workspace. In the handoff, briefly state what was checked and any unresolved limits; report internal scores only when useful or requested. Do not put review activity, self-evaluation, or submission endorsements into the student's report.
