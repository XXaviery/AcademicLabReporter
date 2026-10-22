---
name: academic-lab-report-workflow
description: Create or revise Chinese university laboratory reports as DOCX files from user-provided task sheets, school templates, material explanations, experiment code, and measured results. Use for laboratory reports across experiment types; not for ordinary academic questions or unrelated papers.
---

# Academic Lab Report Workflow

## Intended result

Produce a Chinese laboratory report in DOCX that follows university formatting requirements and reads naturally as the student's own independently completed work. Convey a coherent experiment, concrete implementation, and evidence-based analysis; never invent experiences or results to create that impression.

Adapt the report to the actual experiment, including electronics, embedded systems, FPGA, communications, signal processing, software, and other laboratory work. Do not impose one chapter outline on every experiment.

Read [the report specification](references/report-spec.md) before planning, writing, formatting, or reviewing a report. It defines content selection, student voice, prohibited wording, evidence boundaries, typography, figures, fields, and review criteria. The user's explicit instructions and school template take precedence over defaults.

When including source code, follow [Source code listings](references/report-spec.md#source-code-listings) for editable in-body text, language-preserving reproduction, program labels, parameter comparisons, dedicated typography, and pagination. Apply it across programming languages and file types; do not derive the style from a particular report.

All report titles and headings must render in black, not theme blue. Every body table must use the specified three-line format; cover tables follow their cover role. Mathematical formulas must appear as rendered equations, never raw LaTeX in ordinary report text. These explicit user requirements override conflicting template defaults.

For post-generation scoring and independent review, read [the parallel review protocol](references/review-protocol.md). Complete internal corrections and verification within the original report request; do not hand off a known defective first draft for the user to find routine mistakes.

## Establish requirements without repeated approval

This skill adds report-writing and quality standards, not a new approval process. Treat a request such as "write the report", "revise it", or "fix the formatting" as authorization to complete the necessary work. Do not turn ordinary progress updates into permission questions.

Reuse the user's instructions, supplied materials, and decisions already settled in the conversation. Use the following as an internal checklist, not a questionnaire to present on every invocation. Ask only for consequential information genuinely missing from the available context:

- The task sheet and experiment requirements.
- The school template, cover, title, and formatting instructions.
- The user's material explanations and mappings between materials and report content.
- Experiment details, actual results, photographs, code, and project files.
- The project root and the purpose of relevant folders.
- One fixed report-generation folder and the final DOCX filename.
- The content plan, proposed figures and tables, and any necessary placeholders.
- Retention or cleanup of generator scripts and intermediate files.

Do not invent experimental facts or infer ambiguous folder purposes. Ask about an unknown project root or necessary school template. Resolve routine writing, formatting, and implementation choices from the template, this specification, and the existing context; these choices do not each require confirmation.

A direct request to create, write, revise, or fix a report authorizes the necessary report-file creation, edits, regeneration, rendering, parent-agent writing, and read-only subagent review within the requested scope. Do not require a separate approval of the plan or ask permission for each file edit. Continue through review corrections and layout fixes to completion. If the user explicitly requests discussion only or review of a plan before implementation, honor that boundary and wait for approval of the requested plan.

Existing authorization and confirmed preferences remain valid across revisions. Ask only when essential information is missing, instructions materially conflict, or the next action would exceed the authorized scope. Missing results block only dependent content; continue independent work without inventing evidence.

## Separate task authorization from system permissions

Within the authorized task and actual platform permissions, execute these operations directly without asking "May I...?" or "Allow the writer to edit...?":

- Read and search the task sheet, template, materials, and experiment code.
- Locate installed runtimes, fonts, Poppler, and other bundled tools.
- Create or edit report-generation scripts, including an existing `create_report.py`.
- Generate or overwrite the report's fixed DOCX and its authorized explanatory figures.
- Render DOCX or PDF pages, count pages, and produce temporary contact sheets for inspection.
- Correct content, script errors, and layout, then regenerate and verify the report.

Using available `pdf2image` and Poppler for PDF-to-page-image conversion is authorized as part of report QA. They do not themselves export DOCX to PDF; use a suitable installed document renderer first. Their use does not add a conversational permission step or authorize bypassing platform restrictions.

Use the established project and generation paths. Locate existing tools through ordinary read-only operations; an executable being installed outside the project is not by itself a reason to request elevated execution. Run routine commands with default sandbox permissions. Do not proactively escalate simply because a command uses Python, PowerShell, Poppler, rendering, or visual QA.

Check the actual writable paths and permission grants, and reuse existing grants for as long as they remain valid. Do not infer that a project lacks write permission merely because an approval card appears. Distinguish tool-level execution approval from filesystem access and task authorization.

If the platform requires additional access to a requested path, request only the necessary access, grouped into one request when supported. Explain the specific path and platform restriction. Do not request access again for each write once it has actually been granted. A user's task instruction does not itself remove sandbox restrictions, and this skill must not bypass approval controls or alter global security settings.

If an actual sandbox denial or execution-environment failure requires a platform-mandated retry, identify the real error and follow that requirement. Do not frame the request merely as permission to perform already authorized report work. When mandatory approval is rejected, do not route the same blocked operation through another agent or tool to evade it.

## Manage paths and files

1. Put the single final report DOCX directly in the confirmed project root. The project root is the user-designated project containing this experiment and report; it is not automatically the generation folder or current working directory.
2. Use one fixed final filename. Overwrite that same DOCX for revisions; do not create numbered copies or multiple final versions.
3. Use one dedicated report-generation folder for the report, commonly the project's `codex/`, at the confirmed location. Reuse the folder and edit the existing generator script for every revision.
4. Keep generator scripts, Markdown drafts, review notes, temporary files, and render outputs in the generation folder, outside the project root.
5. Save generated figures in the user-specified figure-output folder, otherwise `<project-root>/material/generate/` inside the established project. Briefly state the default location without requiring separate approval; ask only if it conflicts with the user's directory map or access constraints.
6. Read source materials and experiment code from their specified locations. Do not create a `code/` folder, move source code, or reorganize the user's folders without direction.
7. Report production does not itself authorize editing experiment source code. Such edits require explicit authorization for that work.
8. Apply only the agreed cleanup. Recommend retaining reusable generator scripts and documentation; do not delete files without explicit authorization. Preserve experiment source code, the `codex/` directory, the report project folder, and unrelated user files.
9. The single-final-report rule governs this report's outputs, not pre-existing unrelated files. Do not delete other files merely to make the root appear to contain one DOCX.

## The parent agent writes; subagents only review

The primary (parent) agent is the report's writer and owns all authorized file changes. It writes the prose, creates and edits generator scripts, produces diagrams and the DOCX, renders pages, prepares inspection images, and applies review corrections. Do not delegate report writing or file modification to a subagent, and do not create a Report writer subagent.

After producing and rendering the complete draft, launch multiple read-only reviewer subagents concurrently according to the parallel review protocol. Normally use three roles: experiment/content/evidence, formatting/visual layout, and natural student language. Each returns scores, located findings, and actionable suggestions. Supply the same saved draft, task sheet, template, evidence, exact project paths, and parent-generated page images to every reviewer. Do not assign chapter drafting, script changes, DOCX generation, rendering, artifact creation, or any other file-writing work to reviewers.

If a reviewer needs another render, extracted artifact, or file change, it reports that need to the parent. The parent performs authorized production and revisions using its own valid platform permissions, then supplies the updated material for review. Reviewers report essential missing facts to the parent; the parent consolidates any necessary questions for the user. Neither agent adds routine conversational permission requests.

The parent applies accepted findings in the existing generation project and resolves disputed findings against the task sheet, template, and evidence instead of inserting speculation. If an earlier Report writer subagent exists, discontinue its writing assignments and use subagents only for read-only review; the parent continues the writing and edits. Changing roles does not authorize bypassing a platform denial.

The parent consolidates findings, corrects all supported defects, regenerates and re-renders, and obtains targeted rechecks. Keep scores and review records outside the report body. Internal full marks mean only that the checked rubric has no known deduction; they do not guarantee a teacher's grade. Never inflate scores, waive a requirement, or invent evidence to reach 100.

If concurrency is limited, use the available reviewer slots, combine roles without dropping criteria, and state the limitation in the handoff. If subagents are unavailable, the parent performs separate review passes and discloses that independent subagent review was unavailable. Do not ask permission for routine scheduling or falsely claim parallel independent review occurred.

## Write, format, and verify

Organize content using the user's material explanations and mappings. Do not invent a separate material classification or assume folder meanings.

Choose the report structure and depth from the template, task sheet, actual experiment, and available evidence. Follow the specification's natural student voice and strict wording restrictions in both report prose and code comments.

Before generation, create an internal requirements checklist from the task sheet, template, and user instructions. Trace requirements to report sections and evidence. In the existing generator, use consistent helpers for headings, body tables, equation insertion, figure placement, and source-code listings so that individual objects do not escape the rules. Check every body table, title/heading, formula, figure, and code listing; do not infer whole-document compliance from a sample or a score.

For DOCX production, use the available `documents:documents` workflow when applicable. The user's template, this specification, and explicit user instructions override its generic visual defaults. Carry the existing task authorization into supporting workflows; do not add optional intake, preview-approval, or per-file confirmation checkpoints. Actual platform approval requirements still apply.

Choose vector drawing, code-based drawing, or image generation for explanatory diagrams according to accuracy, editability, complexity, and available tools. Honor an explicitly requested tool. When using image generation, follow the available image-generation workflow.

Render after the layout is finalized and after substantial layout changes. Inspect every final page at readable resolution, including pages made sparse by oversized images or excessive keep-with-next chains. Contact sheets are navigation aids, not substitutes for detailed inspection. Combine DOCX structure checks with visual inspection; neither properties alone nor screenshots alone prove full compliance.

## Delivery conditions

Before handing off the report, verify internally; this checklist is not another user-approval gate:

- The single current final DOCX is in the confirmed project root under the fixed filename.
- It follows the approved template, content plan, and evidence.
- Substantive reviewer findings have been resolved.
- Every applicable requirement has evidence of verification; none is silently treated as passed when unverified.
- All titles/headings are black; every body table follows the three-line rule; formulas are rendered; figures remain legible without avoidable large gaps or displaced text.
- Missing materials and unresolved issues have been disclosed to the user.
- Any remaining placeholders are retained only with the user's acceptance.
- The body contains no report-editing history, review activity, assistant-style reporting, or self-evaluation.
- The final pages have been visually inspected.

In the handoff message, state the report location, necessary Word field-update instructions, and actual outstanding limitations. Keep those handoff statements out of the report body.

Aim to deliver a corrected report from one user request by completing internal draft/review/fix/recheck cycles autonomously. Do not equate one-request completion with skipping those cycles. Disclose real evidence or tool blockers instead of claiming guaranteed full marks or complete verification.

Acceptance of a placeholder permits a qualified handoff, not verification of the missing evidence or full marks for that requirement.
