# Report Specification

Use this specification for planning, writing, formatting, and review. The school template and explicit user instructions override defaults. Reuse settled decisions. State necessary assumptions briefly; ask only about consequential missing information or conflicts, not routine file edits or formatting choices. A direct production or revision request authorizes work within its scope; a separate plan-approval gate applies only when the user explicitly requests it.

## Content structure and depth

### Adapt the structure to the experiment

Use the school template and task sheet first. If they do not prescribe the structure, choose an outline based on the experiment's goals, implementation, and available materials, briefly describe it, and proceed. Wait for outline approval only when the user explicitly requests review before writing.

Do not require identical chapters for every report. Merge related content where useful. Do not repeat material merely to fill sections or add experiment content unsupported by the materials.

The reader should understand what the experiment aims to achieve, the relevant principles, the implementation and procedure, the actual results, and what those results mean. These functions need not each occupy a separate chapter.

### Select relevant content

Select and scale the following according to the actual task:

- **Purpose and tasks:** Extract learning goals, required functions, and verifiable criteria; avoid copying the task sheet wholesale.
- **Principles:** Explain the theories, equations, and mechanisms used in the implementation and connect them to the design. Avoid unrelated textbook background.
- **Conditions:** Describe instruments, components, software and hardware environments, connections, and parameters relevant to execution and results.
- **Design and implementation:** Explain the overall approach, module relationships, key design choices, and implementation logic. Explain essential code rather than translating it line by line.
- **Procedure:** Describe configuration, connection, execution, measurement, and recording in the actual operational order, so the reader can understand how the experiment was performed.
- **Results:** Organize measurements, waveforms, screenshots, and photographs around the task criteria. State testing conditions and explain figures and tables in the text.
- **Analysis:** Compare expected and observed results where evidence permits; analyze differences, errors, or anomalies. Distinguish established causes from hypotheses.
- **Conclusion:** Answer the experiment's goals, state conclusions supported by the results, and identify relevant limitations. Avoid generic reflections.

Never fabricate chapters, procedures, or results to satisfy this list.

### Adjust emphasis to the verification method

These are selection guides, not mandatory chapter templates:

| Experiment characteristics | Relevant emphasis |
| --- | --- |
| Measurement or verification | Measurement conditions, theoretical versus measured values, errors and their sources |
| Hardware design | Structure, connections, parameter choices, signal relationships, physical verification |
| FPGA or digital logic | Module relationships, states or timing, simulation and board-level evidence |
| Algorithms or signal processing | Methods, parameters, input data, outputs, performance comparisons |
| Software implementation | Functional logic, runtime conditions, test inputs and outputs, boundary cases |
| Integrated systems | Module interaction, interfaces, integration procedure, overall function verification |

An experiment can combine these characteristics. Include only analysis relevant to the task and supported by the materials. Distinguish simulation, software execution, and physical testing; do not present one as evidence of another.

## Natural student voice and factual boundaries

### Write about the actual experiment

Use first-person or objective descriptions consistently; do not force first-person wording into every paragraph.

Connect principles to the implementation, explain key choices when the materials support their rationale, relate concrete figure or table observations to the task, and ground conclusions in preceding results.

Avoid stock phrases, repeated summaries, vague significance claims, unrelated textbook exposition, and line-by-line code paraphrases.

Make the report read as the student's independently completed work through coherent reasoning, concrete procedures, and grounded analysis. Do not manufacture experiences or repeatedly announce independent authorship.

### Review language beyond a phrase blacklist

Read the complete prose for relevance and naturalness, not just forbidden tokens. Flag generic praise, claims of significance unsupported by the experiment, repeated "purpose-method-result-significance" paragraphs, mechanical transitions, inflated adjectives, and conclusions that merely restate the introduction.

Replace vague assertions with specific objects, parameters, observations, and explanations already present in the materials. Prefer a short accurate account over padded completeness. Keep technical terms where they clarify the experiment; avoid promotional language such as `充分体现了`, `显著提升了综合能力`, or `为后续研究奠定了坚实基础` when they substitute for experimental analysis. Do not treat an isolated transition word as proof of poor writing; judge the passage in context.

After a language revision, check that factual meaning, quantities, uncertainty, and the strict prohibited constructions remain correct. Do not intentionally add mistakes, fabricated personal anecdotes, or detector-evasion tricks to simulate student authorship. Do not claim that an AI detector establishes authorship or use a detector score as the acceptance criterion.

### Keep claims within the evidence

Use the supplied code, project files, measurement records, observations, and photographs as the basis for experiment-specific claims.

- Code can establish implementation logic; code alone cannot prove successful physical operation.
- Theory and expected behavior belong in principles or analysis, not as measured results.
- First-person experiences, troubleshooting, design motivations, and reflections require support in the user's materials.
- Do not invent measurements, observations, successful tests, hardware behavior, apparatus photographs, or references.
- Do not present an uncertain causal explanation as established fact.

Use the user's material explanations and mappings. Consolidate questions about consequential gaps, contradictions, and ambiguous materials rather than inventing answers.

If required results or photographs are missing, insert clear placeholders and tell the user what is needed. The evidence-dependent requirements remain incomplete and unverified until the materials arrive. User acceptance of placeholders permits delivery with that disclosed limitation; it does not verify the evidence or earn points for the missing requirement.

When external sources are needed, follow the school's citation rules and verify the sources; never invent references.

### Prohibited constructions: report prose and code comments

The following Chinese constructions are strictly prohibited in both report prose and code comments. Also avoid equivalent change-reporting formulations. There is no exception for describing actual debugging:

- `新增了…` / `添加了…` / `增加了…`
- `修改了…` / `改成了…` / `调整了…`
- `在原有（基础）上…` / `在此基础上…`
- `优化了…` / `完善了…` / `重构了…`
- `根据要求…` / `按照您的要求…`

Enforce these restrictions in all produced report prose, report-included code comments, and comments authored or edited in report-generation files or other explicitly authorized code changes. Existing experiment-source comments do not expand the edit scope: flag relevant violations without changing the source unless source editing is authorized. When adapting a code excerpt's comments for the report, preserve its behavior and meaning and do not claim that the source file itself was changed.

Describe the design, operations, observations, and causes directly. Code comments describe what a variable, function, branch, module, or signal does.

Actual troubleshooting may appear if supported by evidence, but rephrase it as an experiment narrative without these constructions and without altering the facts.

Illustrative rewrites, usable only when supported by the actual materials:

- Instead of `增加了按键消抖功能`, write `按键输入采用延时消抖`.
- Instead of `修改了采样周期`, write `采样周期设为 10 ms`.
- If the record establishes a parameter change, write `采样周期由 20 ms 缩短至 10 ms，随后记录输出波形`.

These examples illustrate wording only; they do not supply facts or values for a report.

### No assistant reporting, self-evaluation, or endorsement in the body

The report body must never address the user as a writing assistant or describe AI involvement, agent delegation, report editing, or review activity.

Strictly prohibit:

- `该报告满足所有要求` / `完全符合任务` / `已达 100 分格式`.
- `测试没问题，可以提交` / `经测试一切正常` / `验证通过`.
- `如有需要可继续完善` / `以上即为本报告全部内容`, or similar conversational closing remarks.
- Any evaluation of the report's own quality, completeness, formatting compliance, or readiness for submission.

Conclusions address the experiment and its results. State test conditions, data, and observations rather than blanket endorsements, even when actual testing took place.

For example, only with supporting records: `连续进行 20 次按键操作，每次操作均对应一次计数变化。`

Never invent a count, measurement, or observation merely to replace a prohibited phrase.

## Document structure and typography

The deliverable is a Chinese laboratory report in DOCX. Follow the supplied cover and title template; do not design a cover or title page. Ask if necessary template or title requirements are missing.

All report titles and heading levels must be explicitly black (`#000000`). This user requirement overrides a template's blue heading defaults. Set the relevant paragraph/character styles and any conflicting direct run formatting; remove or override theme color, tint, or shade attributes that could restore blue. Check existing and newly inserted headings, including numbering, in the saved DOCX and rendered pages. A black heading style alone is insufficient if a run or linked style overrides it.

Defaults:

- Chinese body text: `仿宋_GB2312` where available, otherwise FangSong.
- Latin letters, numbers, and symbols: Times New Roman.
- Body: 小四号 / 12 pt, regular weight, first-line indent of two Chinese characters, 1.5 line spacing.
- First-, second-, and third-level headings: 黑体, black, bold, respectively 三号 / 16 pt, 四号 / 14 pt, and 小四号 / 12 pt.
- Western characters and Arabic numerals in headings: Times New Roman.
- Heading line spacing: 1.5.
- Margins: 2 cm on all four sides.
- Heading numbers: `1`, `1.1`, `1.1.1`, unless the template requires another system.
- Body prose, headings, table text, and captions: 1.5 line spacing unless the template specifies otherwise. Source-code paragraphs use the dedicated rules below.

Use the template for unspecified items such as table-caption fonts and TOC typography. Source-code typography is specified below rather than inherited from a template. Where the template is silent on other items, choose readable typography consistent with the documented report style and proceed; do not present that choice as a school requirement. Ask only if a necessary school rule is unknown or an explicit requirement conflicts with the proposed choice.

## Source code listings

These rules apply to source code included in the report, including MATLAB, C/C++, Verilog, and other languages. Do not limit them to particular languages, extensions, or a reference report. They override general body-text size, first-line indentation, and line-spacing defaults for code paragraphs, as well as conflicting template code styling. Ordinary prose and the rest of the report retain their existing rules.

### Editable placement and labels

Place code as editable text in the report body, not screenshots, rasterized code, embedded source objects, or attachments. Use ordinary paragraphs, not a table or text box that would introduce a frame or table-border rules.

Before each listing, place a separate label paragraph containing `基准程序` or `实验程序`, according to its actual role. For parameter comparisons, also put a separate, factual change description immediately before the relevant variant, for example `参数变化：N 由 3 改为 5`. The example supplies a label pattern, not values to invent. These objective comparison labels do not replace the existing prohibition on assistant-style change reports.

Identify programs by their role, not code filenames, extensions, or source paths in report labels, prose, or explanatory comments. Omit filename-only provenance comments from report excerpts. Preserve any syntax-essential include/import operands or string literals inside the actual code rather than deleting executable tokens to hide a filename. Do not rename or edit original source files for report presentation.

### Preserve source meaning and structure

Preserve logic, identifiers, operators, literals, indentation, source line breaks, blank lines, and necessary comments. Map each source line to its own code paragraph, including intentional blank lines; do not merge code into prose paragraphs or put an entire listing into one paragraph with manual line breaks.

Preserve leading and repeated whitespace in Word, including significant spaces and tabs; use whitespace-preserving text and appropriate tab stops. Do not let smart quotes, automatic bullets, automatic capitalization, or typographic substitutions change code tokens.

Keep the language's syntax and comment delimiters: for example `%` in MATLAB and `//` or `/* ... */` where valid in C/C++ or Verilog. For other languages, use their actual syntax. Comments briefly explain code purpose; do not translate code into long explanatory comments or replace comment symbols with another language's conventions. Necessary rewording of a report excerpt's comments must preserve their meaning and follow the existing prohibited-expression rules without changing the original source.

### Dedicated code typography and decoration

- Latin code, numbers, and symbols: Times New Roman. Chinese comment text: `仿宋_GB2312`, with the existing FangSong fallback only if that font is unavailable.
- All code and comments: 五号 / 10.5 pt, regular weight, explicitly black (`#000000`). Set script-specific font properties so Chinese comments do not inherit the Latin font and do not switch to a default monospace code font.
- White background. Remove inherited paragraph/run shading, highlighting, syntax colors, and complete frames. Do not add syntax highlighting or top, bottom, right, or internal borders.
- One thin light gray-blue vertical rule on the left of the code block, approximately `#A7B5C4`; use a thin paragraph border, such as 0.5 pt. Keep border settings and alignment consistent across the code paragraphs so the rule reads as one block edge, including across intentional blank source lines.
- Paragraph spacing before and after: 0 pt. Use compact single line spacing with enough height for Chinese glyphs; check for clipping instead of inheriting the body's 1.5 spacing.
- Use a small, consistent left paragraph indent and clear the inherited two-character first-line indent. Preserve the source's own indentation separately; do not insert extra blank paragraphs as spacing.

Keep the program label and parameter description as separate non-code paragraphs, attached to the beginning of the listing. A dedicated code paragraph style and reusable insertion helper should apply these settings consistently without changing ordinary body styles.

### Pagination and parameter comparisons

Keep a complete code block on one page when it fits without causing a large avoidable gap. Keep each source-line paragraph intact. Attach labels to the first code lines, but do not unconditionally chain every paragraph of a long block or join its final line to following prose.

If a block is longer than a page, allow pagination at sensible code-section boundaries and keep several lines together on either side; avoid leaving only one or two code lines on the next page. Reflow nearby material or revise document-level indentation/spacing before introducing a large blank area. Do not alter source line breaks or continuation syntax, clip long lines, shrink below 10.5 pt, or turn code into an image to force a fit. If a source line cannot fit at the required size within the allowed layout, resolve that specific layout constraint without changing program semantics or silently claiming compliance.

In a parameter comparison, preserve the baseline and change only the parameter or parameters the task requires observing. Do not substitute every matching number, refactor the program, or change unrelated settings. State the actual parameter name and old/new values before each variant; preserve corresponding necessary comments and calculated relationships. A listing variant alone is not evidence that it was executed or produced a measured result.

### Verification

For every listing, compare the editable text with its source or authorized variant, then inspect the rendered pages. Check line-to-paragraph mapping, indentation, comment syntax, labels, absence of filename-based labeling, 五号 / 10.5 pt fonts, black text, white background, the lone pale left rule, intact lines, and neighboring-page flow. Check that parameter differences are limited to the required observations. A screenshot cannot establish text editability, and saved paragraph properties alone cannot establish readable pagination.

## Tables

Put captions above tables. Follow the template's caption typography; if unspecified, use typography consistent with the figure captions unless existing user instructions specify another choice.

Every body table must use the three-line format: black 1 pt top and bottom rules, a black 0.5 pt rule below the header, no vertical borders, and no other internal horizontal rules. This explicit user requirement overrides conflicting body-table borders in the template. Cover tables follow the cover template and are exempt.

Apply the rule to every body table, including copied or template-derived tables. Identify cover tables by their role, not by assuming that the document's first table is always a cover table. Clear unwanted inherited `Table Grid` effects and conflicting table/cell borders. The visible rules must be the top edge, the bottom edge of the header block, and the bottom edge of the final data row. For a multirow header, put the middle rule below its last header row. Border sizes in Word XML are in eighths of a point: 1 pt is `w:sz="8"`, and 0.5 pt is `w:sz="4"`.

Maintain an internal inventory of body tables with location, caption, and header rows; identify exempt cover tables separately. Do not infer body-table exceptions from inherited template grid styling. Inspect effective table and cell borders in the saved document and inspect each rendered table for extra lines, missing rules, incorrect widths, and broken rule segments across merged cells. Nonprinting Word gridlines do not count as borders; check the exported page. Do not accept one correct table as evidence that all tables are correct.

Cell text is centered, 五号 / 10.5 pt. Chinese text uses `仿宋_GB2312` or FangSong; Latin text, numbers, and symbols use Times New Roman.

Keep a body table on one page where feasible. Apply `keep_with_next` to relevant table paragraphs or move the whole table to the next page. Do not mechanically apply this table measure to images or code blocks.

Avoid a keep-with-next chain that joins the entire table to following prose. Release unnecessary links at the end of the table and check the neighboring pages for avoidable blank space.

If a table cannot fit on one page while remaining readable, use a split-table or multipage arrangement consistent with the template, with repeated headers where appropriate. Ask only if this would contradict an explicit requirement; do not shrink the table into illegibility.

For continuation pages, follow the school's explicit continuation naming and header conventions while retaining the required three-line borders. Otherwise use clearly labeled continuation table segments, each with a repeated header and its own three-line rules; inspect every rendered segment rather than exempting a long table from border checks.

## Figures, captions, and diagrams

Center images and captions. Put captions below images, by default in the form `图2-3 xxxx`. Chinese caption text uses `仿宋_GB2312` or FangSong, 五号 / 10.5 pt; Western characters, numbers, and symbols use Times New Roman. Caption and editable in-figure explanatory text use 1.5 line spacing by default.

The figure prefix follows the visible first-level heading number. Count figures in appearance order within each first-level section, starting at 1; restart in the next section. Follow the template's numbering system without converting it to another system.

### Drawing method

Choose vector drawing, code-based drawing, or image generation according to text accuracy, editability, complexity, and tool availability. Honor an explicitly requested tool. For image generation, use the currently available tool and its workflow; do not hard-code a model version.

Save generated figures in the confirmed output folder, by default `<project-root>/material/generate/`. Inspect the actual figures before insertion.

### Figure content

Keep diagrams restrained and academic. Use accurate nodes and connections, legible text inside its shapes, and no clipping, overflow, overlap, or blur. Avoid decorative styling and irrelevant task labels.

Generated diagrams explain concepts, structures, or procedures. They must not impersonate apparatus photographs, instrument screenshots, measured waveforms, or other experimental evidence.

Use clear placeholders for missing experiment photos and result screenshots. Wait for the user's materials before replacing those placeholders, while continuing sections and layout work that do not depend on the missing evidence.

Size images for readability and page fit. Do not impose a uniform height limit on portrait photos; verify their placement and clarity by rendering.

### Fit each figure into its surrounding text

Choose dimensions separately for each figure. Preserve aspect ratio, keep it within the usable page width, and account for caption height and paragraph spacing when estimating vertical fit. Prefer inline placement unless the template needs another layout; avoid unstable floating anchors and text wrapping.

If a large figure pushes nearby prose onto the next page or leaves a large avoidable gap on the preceding page, inspect both pages and adjust image size, spacing, or the local placement. Keep the figure with its caption, but do not chain an entire section to the figure. Remove accidental manual page breaks, empty paragraphs, inherited page-break-before settings, or overly broad keep-with-next chains when they cause the gap. Preserve intentional cover, chapter, or template page breaks.

Do not apply a single large width to every image, force every image onto a separate page, stretch an image, or reduce labels to illegibility merely to fit a page. If readability prevents fitting in the remaining space, use the next page and reflow nearby prose where appropriate. Unavoidable whitespace is acceptable; a nearly empty page caused by a fixable oversized image is a defect.

Check each image-caption pair, its preceding page, and its following text after rendering. A later size change can move tables, equations, headings, and page numbers, so recheck affected pagination.

## Mathematical formulas

Formulas must appear as typeset mathematics in the final report. Prefer native editable Word equations (OMML). If the available workflow cannot reliably produce or render a required equation, use a sharp rendered equation image, preferably vector where supported, sized to match the surrounding text and checked in the exported pages. Keep source LaTeX only in generation working files; it is not the report's visible formula.

Do not leave LaTeX commands or delimiters such as `\frac`, `\sum`, `\begin{...}`, `$...$`, `$$...$$`, or `\[...\]` as ordinary report prose. A source-code listing that intentionally demonstrates LaTeX is a separate case, not an excuse to leave experimental formulas unrendered.

Check every equation for missing glyphs, incorrect fractions, roots, sums, subscripts, superscripts, symbol fonts, clipping, baseline alignment, and legibility. Explain variables and units where needed. Follow the template's equation numbering and alignment when prescribed. Verify both the saved equation representation and its actual rendering; merely inserting an OMML node does not establish that the exported equation is readable.

## Tables of contents, page numbers, and Word fields

Use real Word fields for the TOC and page numbers, not ordinary text imitations. Preserve a real TOC field.

By default, leave updating to the user and put the instruction in the handoff: in Word, press `Ctrl+A`, then `F9`, or accept the update prompt on opening. If the user requests a pre-refreshed DOCX, prefer LibreOffice to refresh and save it; use Word COM only as a last resort.

Do not display page numbers on the cover or other front matter. Insert a section break at the start of the body and restart at page 1 using section `pgNumType` start value `1`.

Use automatically recalculated fields such as `PAGE`, `NUMPAGES`, and `SECTIONPAGES`; do not calculate totals by subtracting a fixed front-matter count in a formula field.

When the body is one section restarting at 1, use `第 { PAGE } 页 共 { SECTIONPAGES } 页`. Insert actual fields, not literal braces and field names.

If the template requires multiple body sections, design the total-page display for that arrangement; do not treat one section's `SECTIONPAGES` as the total for the entire body.

Render and verify the first and last body page numbers and the total. Field displays can depend on refresh state and the rendering tool; code inspection alone is insufficient.

Keep Word field-update instructions in the handoff, never in the body.

## Parallel subagent scoring and review

The primary (parent) agent writes the report and performs all authorized file changes, generation, rendering, and corrections. Subagents are used only for read-only review; do not delegate report writing or file modification. Provide reviewers with the exact project paths, existing materials, draft, and parent-generated page images, subject to their actual platform permissions.

After the complete report is generated and rendered, follow [the parallel review protocol](review-protocol.md): launch multiple reviewers concurrently for content/evidence, document formatting/visual layout, and natural language. They score their assigned criteria and return specific findings and correction suggestions. Use the teacher's rubric where supplied; otherwise label the protocol's 100-point rubric as an internal provisional assessment. Scores and review records belong in the generation workspace or handoff, never in the report body.

The reviewer reads the task sheet, the user's material explanations, the underlying materials, the draft, and supplied page images without editing files or creating artifacts. Return findings and suggestions to the parent. Report missing facts, required renders, or proposed changes to the parent instead of drafting sections, running production scripts, or asking the user for file-edit permission. The parent handles necessary user questions and all authorized corrections.

Check:

1. Coverage of task requirements and user-specified content.
2. A structure suited to the experiment, without irrelevant or mechanically imposed chapters.
3. Consistency between principles, design, procedure, results, and conclusions.
4. Technical accuracy and internal consistency.
5. Evidence for factual claims, with expected behavior, simulations, code logic, and measurements correctly distinguished.
6. Figure and table references, explanations, numbering, and content consistency.
7. Concrete analysis and conclusions supported by results.
8. Vague, repeated, unrelated textbook material or line-by-line code paraphrase.
9. Natural, coherent prose without invented experiences or report-editing history.
10. Strict compliance with the prohibited constructions in both prose and code comments, including equivalent change-reporting wording.
11. Absence of assistant-style reporting, self-evaluation, endorsements, and conversational closings in the body.
12. Missing essentials, unresolved placeholders, and questions requiring user input.
13. Black titles/headings, effective three-line borders in every body table, rendered formulas, and per-figure sizing with sensible neighboring-page flow.

For each finding, provide its chapter, paragraph, figure, table, or code location; the reason and supporting basis; an actionable correction; and whether user-supplied material is required.

Distinguish substantive correctness or completeness problems from optional stylistic suggestions. Do not treat personal preferences as errors.

The primary (parent) agent applies all corrections in the existing project without another conversational file-edit approval. Questions that the materials cannot resolve go to the user in a consolidated batch. Corrections and wording replacements must preserve facts, not invent them.

After substantive corrections, the reviewer rechecks affected content. Do not repeat review without new changes or unresolved concerns.

The parent resolves overlapping findings without double-counting deductions and uses targeted rechecks after corrections. Do not instruct reviewers to award full marks, repeatedly sample reviews until a favorable score appears, or average away an unresolved defect. Full internal marks require verification of every applicable criterion and no known deduction, not a promise of a teacher's grade. Unavailable evidence and unchecked requirements stay explicitly unverified.

## Visual inspection and handoff checks

Rendering, page-count checks, temporary contact sheets, and corrections are included in the user's report-production or revision request. Perform them directly within existing platform permissions. The quality requirements in this specification do not add a per-command or per-file human-approval step. Use the established generation folder and already available tools; follow the entrypoint's rules if actual platform access or execution fails.

`pdf2image` and Poppler are allowed for PDF-to-image QA. Use an installed DOCX-capable renderer to export the saved DOCX to PDF before rasterizing it. Use existing dependencies without unnecessary installation or approval questions. Do not treat conversion success or a matching page count as a layout check.

Keep each render in a revision-specific subfolder of the existing generation workspace and supply a page list for that revision. Verify that the PDF and page images come from the current saved DOCX and that page counts agree; do not count stale images or reuse an old contact sheet after regeneration. This does not create another final DOCX or a new report project.

Render the DOCX to page images after layout finalization and substantial layout changes. Small text edits can receive focused inspection of affected pages; inspect every page before final delivery.

Check clipped text, missing glyphs, inconsistent headings or fonts, broken tables, awkward table pagination, unclear images, separated figures and captions, awkward whitespace, unintended blank pages, front matter, section boundaries, page numbering, and figure/table reference consistency.

Use contact sheets to locate issues, then open each final page at a readable scale. Inspect every table and formula at sufficient resolution to judge borders and symbols. Pair visual checks with saved-DOCX checks of heading color overrides, fonts and sizes, table/cell borders, equation objects or images, picture dimensions, and Word fields. Maintain a requirement-level record of verified, failed, unverified, and not-applicable items in the generation workspace.

Do not infer visual correctness from `python-docx` properties or document source alone. Keep render intermediates in the generation folder, outside the project root.

Verify the confirmed project root, filename, and folder roles. Keep one final DOCX for this report in the project root and overwrite it for revisions; do not create numbered copies or move or delete unrelated user files.

Content review and visual inspection are separate requirements; neither substitutes for the other. Disclose checks that could not be completed in the handoff without claiming they passed.

Complete the draft, parallel review, parent corrections, and final checks within the original authorized request rather than handing routine defect discovery back to the user. Aim for one corrected delivery, allowing as many justified internal edits as needed. Stop only when applicable checks are satisfied or a concrete evidence, instruction, or tool blocker prevents further progress; identify that blocker precisely instead of inventing a pass or silently lowering the standard.
