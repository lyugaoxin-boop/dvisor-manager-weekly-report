---
name: dvisor-manager-weekly-report
description: "Create evidence-grounded weekly reports for academic advisors or workplace managers by learning a reusable recipient profile plus report style from stated preferences, feedback, chat screenshots, behavioral examples, and reference templates, then producing editable documents or presentations. Use when the user provides weekly research or work materials plus at least one recipient or style source."
---

# 面向导师或领导的周报助手

为学生、科研人员和职场人士生成面向导师或领导的周报。分别建立可复用的导师/领导画像与周报风格画像：前者决定什么内容最值得强调、需要多强的证据以及如何呈现风险和下一步，后者决定语言、结构与视觉表达。忠实使用用户提供的论文、实验、项目、图片、表格和日志。

## Terminology

- **Recipient**：周报的导师、领导或其他直接汇报对象。
- **Recipient profile**：导师/领导画像；记录汇报对象稳定的目标、判断标准、证据偏好、风险取向、反馈习惯和信息优先级，用于决定周报写什么、先写什么以及写到什么程度。
- **Report style profile**：周报风格画像；记录语言、结构、篇幅、排版与视觉规则，用于决定周报怎样表达和呈现。
- **Behavioral evidence**：用户提供的、与汇报和反馈有关的可观察行为材料，例如微信或其他聊天截图、批注文档、会议记录、口头反馈转述，以及导师/领导对不同汇报方式的具体反应。
- **Recipient template**：导师或领导提供的模板。
- **Peer template**：师兄师姐或同事提供的参考模板。
- **Unlabeled reference template**：用户已上传或提供、但没有明确说明来源属于导师/领导还是师兄师姐/同事的模板；默认按 recipient template 处理。
- **Recipient/style source**：用户口头或文字描述的汇报对象偏好、behavioral evidence、对既往周报的反馈、recipient template、peer template 中的任意一种。
- **Temporary requirement**：用户只针对本次周报提出的特殊要求。

## Non-negotiable gates

Do not draft the complete report until both gates have passed:

1. **Goal gate**：关键目标已经澄清，向用户复述理解与默认值，并得到明确确认。
2. **Preview gate**：已经展示本次周报的风格示例，并得到用户明确的“确认”“继续生成”或等价指令。

Read-only inspection of supplied files is allowed before the goal gate when needed to ask an informed question. Do not create substantive report content before that gate.

## Intake and clarification

1. Inventory the supplied recipient/style sources and weekly materials.
   - Accept user-supplied WeChat or other chat screenshots, annotated reports, meeting notes, feedback excerpts, and concrete descriptions of the recipient's day-to-day reporting behavior as possible recipient-profile evidence.
   - For screenshots or conversations, distinguish the recipient's messages from the user's and other participants' messages. If authorship is consequential and unclear, apply the recipient-profile inquiry conditions before asking; exclude ambiguous material from profile evidence when it cannot be clarified.
   - Ignore unrelated conversation content, contact details, avatars, group-member information, and other personal data that does not change the weekly-report adaptation.
   - Classify template provenance only from the user's explicit description. Treat every unlabeled or ambiguously labeled reference template as a recipient template by default, including when several unlabeled templates are supplied. Do not ask merely to distinguish recipient from peer provenance, and do not infer peer provenance from filenames, embedded names, metadata, writing quality, or visual style. A later explicit user statement about a template's source overrides this default classification.
2. Require at least one recipient/style source. If none is present, ask the user to provide one before proceeding.
3. Use the current date in the user's local timezone unless the user specifies a report date or period. Follow the date style in the selected template; otherwise use `YYYY年MM月DD日` for Chinese output and ISO style for other languages.
4. Identify only uncertainties that materially affect format, structure, emphasis, evidence, or delivery.
5. In conversational intake, ask exactly one question at a time. Explain why the answer changes the result, then wait for the answer.
6. Use heuristic, as-needed questions rather than a fixed questionnaire. Infer what is safe to infer from templates and materials; do not repeat questions already answered by evidence.
7. If the user asks for a questionnaire or prefers faster batch intake, generate a compact, adaptive, behavior-based questionnaire instead of enforcing the one-question conversational mode. Ask about concrete examples of what the recipient praised, challenged, requested, ignored, or sent back for revision. Make every item optional, allow the user to answer only what they know, and explain that the answers will produce profile hypotheses for confirmation rather than a personality assessment.
8. Stop questioning once the remaining uncertainty would not materially change the result.
9. Summarize the understood goal, selected defaults, inputs, intended output, and unresolved non-blocking assumptions. Obtain explicit confirmation before continuing.

Treat template structure separately from template instance data. A template may establish that a field exists and how it is formatted, but values such as reporter, presenter, respondent, author, name, student/employee ID, team, project, client, or other identity- and assignment-specific content are not reusable profile information. Never carry those values into a new report, recipient profile, or report style profile. For missing person-identity fields such as reporter, presenter, respondent, or author, use the literal value `xxx` by default without asking; a current user-supplied value always overrides this default. This `xxx` fallback is an execution default, not a recipient preference. For other required assignment-specific values, ask one question at a time or use a clearly marked placeholder only when the user explicitly chooses to proceed without them.

When the recipient-profile inquiry conditions below are met, consider these dimensions only as needed. Use the answers to build the recipient profile rather than running a fixed questionnaire:

- what the recipient cares about most;
- conclusion-first versus process-first communication;
- preferred concision and detail;
- reliance on quantitative evidence;
- treatment of failures, risks, and incomplete work;
- figure-to-text and table-to-text balance;
- expected specificity of next steps;
- disliked expressions or presentation patterns.

Treat recipient-facing language style as a first-class style dimension, independent from visual formatting. Learn it from representative template passages and user-described preferences: sentence length and density, conclusion-first versus process-first order, paragraph organization, technical depth, preferred verbs, degree of formality, use of first person or passive voice, bullet-versus-prose balance, transition patterns, and how the recipient expects progress, results, failures, and next steps to be phrased. Do not reduce language-style learning to topic structure or typography.

### Plain-language baseline

Write every report for a smart reader with no assumed background in the topic. Use simple, direct language to make the core point, evidence, and logic easy to follow on the first read.

- Prefer concrete subjects and verbs, short logical steps, and explicit cause-and-effect links.
- Put one main idea in each sentence or tightly connected sentence group. Remove abstract padding, stacked modifiers, empty formality, internal slang, management buzzwords, and literal translation patterns.
- Do not use obscure industry jargon as a substitute for explanation. When an exact technical term, method name, metric, model, or official title is necessary for correctness or traceability, keep it and explain its practical meaning in plain language at first use. Preserve an official English name in parentheses when that improves identification; do not create a stiff word-for-word translation.
- Make the reader understand what was done, what changed, why it matters, and what happens next without needing specialist knowledge.

Template language style is an adaptation layer on top of this baseline. Learn the template's tone, sentence length, detail level, order, voice, and paragraph rhythm, but do not copy jargon, internal shorthand, opaque abstractions, or translation-like phrasing that would violate the baseline. Only an explicit current user instruction that the deliverable targets a specialist audience may relax the need to explain standard domain terms; clarity and accurate logic still apply.

Keep planning, source analysis, structural design, and logical checking as professional and rigorous as the task requires. Do not expose private step-by-step reasoning or drafting process in the report. Deliver the resulting conclusion, evidence chain, and necessary explanation in clear prose.

## Authority order

Resolve conflicts in this order:

1. Temporary requirements for the current report.
2. User-described recipient preferences and user-confirmed recipient-profile rules derived from feedback or behavioral evidence.
3. Recipient template.
4. Peer template.

Do not silently reconcile a consequential conflict. Surface the conflict during clarification or preview and apply the highest-priority confirmed instruction.

When multiple unlabeled templates have all been classified as recipient templates, they share the same authority level. Learn stable common rules across them. If they conflict on a consequential rule that affects the current deliverable, ask one question about that rule or present the conflict in the preview for confirmation; never demote one template to peer status merely to resolve the conflict.

## Format selection

Use an explicitly confirmed user format first.

- If supplied templates use the same format, match it unless the user asks otherwise.
- If templates use different formats, ask the user which final format to use and explain the impact of the choices.
- If the only recipient/style source is a verbal preference description, ask the user to confirm the output format.
- For PPT or PPTX output, invoke `$ppt-master` to inspect the template, reproduce its visual system, create editable slides, and render-check the result. If `$ppt-master` is unavailable, explain the dependency before proceeding.
- For other formats, use the appropriate document, PDF, spreadsheet, or presentation capability. Preserve editability when possible and visually verify layout-sensitive output.

Preserve the selected template's page or slide size, hierarchy, typography, colors, margins, spacing, header/footer conventions, page/slide numbering, and figure/table placement unless a higher-priority instruction overrides them.

Inspect and reproduce the document title and every observed heading level independently. For level 1, level 2, level 3, and any deeper level, record and apply its own font family, font size, weight, color, alignment, numbering pattern, indentation, line spacing, spacing before/after, and keep-with-next/page-break behavior. Do not infer all headings from one example, flatten distinct levels into the same style, or preserve numbering while losing the corresponding typography. If the current report uses a heading level absent from the applicable template, derive it from the nearest observed levels while keeping a clear hierarchy, and disclose the fallback in the preview.

Learn body-paragraph spacing from the applicable template as an independent style rule. Inspect multiple representative body paragraphs and record the effective line-spacing mode and value—such as single, multiple, exact, or at-least spacing—together with paragraph spacing before/after. Distinguish stable body variants such as ordinary prose, lists, and table-cell text when the template does. Do not infer body spacing from headings, captions, or one locally overridden paragraph. If the template provides no reliable body-spacing evidence, use a restrained format-appropriate fallback and disclose it in the preview.

Treat formulas and equation numbers as a separate typography role. Unless a current user instruction or a confirmed applicable-template equation style establishes a different size, set formula text to the same point size as the confirmed body text. Do not shrink formulas merely to make them fit; reflow or break a long formula while preserving mathematical meaning and editability.

Learn wording separately from paragraph spacing. Internal evidence caution must not leak into the recipient-facing report as audit commentary. Do not write sentences that enumerate absent thresholds, random seeds, repeat statistics, unfinished planned epochs, or other missing evidence and then explain what cannot be concluded or claimed. Keep those constraints in the internal evidence ledger. In the report, state only the strongest supported current result in the learned language style—for example, `已恢复训练并完成首轮验证`—and omit the meta-explanation about unsupported stronger claims. When missing evidence affects the next action, state the next action directly and concisely instead of narrating the evidentiary limitation.

Preserve the label and placement of identity fields when applicable, but never copy their prior values from a template.

## Recipient profile

### Recipient-profile inquiry conditions

Establishing or updating a profile does not automatically require an interview. Apply these conditions to questions about the advisor's or manager's reporting preferences; collecting weekly facts and confirming a proposed profile are separate actions.

**Timing and user choice.** Normally evaluate the need for profile inquiry after the user finishes uploading the current material batch, or clearly presents it as complete, and after inspecting the available evidence and any confirmed profile for the same recipient. While the user says more materials are coming, inventory them without starting a profile interview. An explicit request to start an interview now permits an earlier start. Honor the user's current inquiry preference and any applicable inquiry-preference gate before asking substantive questions; agreeing to inquiry permits useful questions but does not require a full interview.

| Situation | Action |
|---|---|
| The user explicitly requests a profile interview or questionnaire | Start the requested mode, focusing on information not already supplied. |
| First use or a different recipient, and supplied evidence leaves a consequential preference unknown | Ask about the highest-impact gap, such as what counts as progress or which results should lead. First use alone is not a trigger. |
| An existing profile leaves a gap that changes this week's content priority, evidence depth, risk treatment, or next-step framing | Ask only about that gap; reuse the rest of the confirmed profile. |
| New feedback or materials conflict with an applicable profile rule, and instruction priority does not resolve the conflict | Ask about the specific conflict or whether the feedback is temporary or stable, if that distinction affects the report or a proposed reusable rule. |
| Materials sufficiently support a new profile, or the existing confirmed profile still applies | Build a supported draft for confirmation or reuse the confirmed profile; skip the interview. |
| Only nonessential schema fields are empty, the same preference was already answered, or new evidence merely repeats a known rule | Keep unknowns explicit where useful; do not ask just to complete the schema or because another week has begun. |

**Question selection and stopping.** Before asking, identify the unresolved preference and the concrete report decision its answer would change. If no such decision can be named, skip the question unless the user requested broader profile exploration. Ask one question at a time unless batch intake was requested. Reevaluate after each answer and stop when the material decisions are supported, the user declines further inquiry, or the user says they do not know. Do not rephrase the same gap repeatedly or turn an unknown into an inferred preference. In skipped or declined inquiry, use supported rules, leave unsupported preferences unknown, and disclose consequential assumptions in the goal summary or preview. If a separately required input is missing, identify that input rather than restarting the profile interview. Confirmation of a new or updated profile remains separate and follows the existing confirmation rules.

Maintain a reusable recipient profile separately from the report style profile. The recipient profile answers **what matters to this person and how they judge progress**; the report style profile answers **how the report should look and sound**.

Reuse a previously confirmed recipient profile by default. Establish or update it only when:

- no confirmed recipient profile exists;
- the user supplies new recipient preferences, feedback, or behavioral evidence;
- a new recipient template provides relevant evidence;
- the user explicitly requests reanalysis.

Build the profile from explicit user statements, recipient feedback on earlier reports, behavioral evidence, and stable patterns supported by supplied recipient templates. Record the source and confidence of every profile rule. Treat screenshot-, behavior-, template-, and feedback-derived interpretations as hypotheses until the user confirms them. Never infer personality, private motives, demographic traits, relationships, health, beliefs, or other sensitive attributes.

Translate behavior only into report-relevant hypotheses. For example, repeated requests for baselines may support a hypothesis that comparisons should be prominent. Do not infer a stable preference from response time, punctuation, emoji use, message length, social warmth, or an isolated reaction. Preserve plausible alternative explanations when the evidence is ambiguous.

Do not infer recipient-profile rules from a peer template. If no recipient-specific evidence exists, create only a minimal draft with unknown fields and apply the recipient-profile inquiry conditions above. Missing profile fields alone do not require questions. The peer template may still inform the report style profile at its lower authority level.

Keep stable preferences separate from current-report goals and temporary requirements. A preference observed once must not become permanent merely because it affected one report.

Use the confirmed recipient profile to:

- rank current content by the recipient's goals and evaluation criteria;
- choose the opening conclusion and the evidence needed to support it;
- decide the depth of process, technical detail, comparison, failure, and risk discussion;
- frame progress and next steps in terms the recipient uses to judge value;
- omit irrelevant detail without omitting evidence that changes a decision.

Before drafting, create an internal recipient-fit map from each substantive content unit to the recipient concern or evaluation criterion it serves. This map guides selection and emphasis; do not expose it in the final report unless the user asks.

Read [references/recipient-profile-schema.md](references/recipient-profile-schema.md) when establishing or updating the recipient profile. When screenshots, behavioral examples, or a questionnaire are used, also read [references/recipient-profile-intake.md](references/recipient-profile-intake.md).

Show a new or updated recipient profile to the user as a separate confirmation artifact so the user can correct unsupported or inaccurate interpretations. Never place the recipient profile, its confidence notes, its source table, or the recipient-fit map inside the weekly report. Keep profile confirmation visibly separate from recipient-facing report content.

## Report style profile

Reuse a previously confirmed report style profile by default. Establish or update it only when:

- no confirmed report style profile exists;
- the user supplies a new template;
- the user supplies new recipient preferences, feedback, or behavioral evidence that changes how the report should sound or look;
- the user explicitly requests reanalysis.

Read [references/style-profile-schema.md](references/style-profile-schema.md) when establishing or updating the report style profile.

Store user-specific recipient profiles, report style profiles, and runtime materials outside the installed Skill directory. If no location is specified, use a clearly private local working-data directory and tell the user where it is. Never upload or commit user data automatically.

Deliver each profile when it is first established or updated. Do not redeliver an unchanged profile every week.

## Material analysis and evidence

Before drafting, build an internal evidence ledger that maps every consequential claim, number, citation, completion status, figure, and table to its source.

Classify statements as:

- verified fact;
- user interpretation;
- model inference;
- missing information.

Never invent numbers, citations, experimental settings, project status, causes, or conclusions. Preserve uncertainty internally by narrowing the allowed report wording. Use `[待补充：...]` or an equivalent marker only for a required report field that cannot be completed and that the user has chosen to leave unresolved; do not use placeholders or caveat paragraphs to expose ordinary evidence gaps, absent experiment settings, or stronger claims that were intentionally omitted.

The evidence ledger is internal by default. Deliver it only when the user requests it. Read [references/report-production-rules.md](references/report-production-rules.md) for its schema and scenario-specific material handling.

### Default literature-review content

For each reviewed paper, include necessary formulas, experimental settings (including a dataset introduction), and experimental results by default, alongside the research problem, method, and relevance. These are normal per-paper content, not optional formula-test additions requiring a separate user request. Read the per-paper coverage rules in [references/report-production-rules.md](references/report-production-rules.md) for selection and evidence handling.

Select only formulas needed to understand the core method, objective, or evaluated metric, explain their symbols and practical meaning, and preserve native editability where supported. Describe the dataset or simulation/case-study setup actually used by the paper and report its concrete findings with their conditions and comparison basis. Clearly attribute these results to the paper; never present them as the user's own experiments. Do not invent formulas, datasets, settings, or numbers for papers that do not provide them. Clarify consequential missing source material one question at a time; do not fill the report with audit-style explanations.

### Default literature metadata enrichment

For every paper discussed in a literature-review unit, include by default:

- one language-routed journal partition metric:
  - when both the applicable template and the confirmed report body are Chinese, the latest verifiable **新锐期刊分区（新锐分区）**, with its edition/year;
  - when both the applicable template and the confirmed report body are English, the latest verifiable **JCR quartile**, with its JCR year and Web of Science category;
  - when the template and body languages differ, either language is ambiguous, or the body uses another language, ask one consequential question before the preview to select the partition system;
- the latest verifiable Journal Impact Factor, with its JCR/JIF year;
- every corresponding author's name, country, and top-level institution.

Use the paper's exact English original title in the recipient-facing report. Do not translate the paper title. The default Chinese presentation is exactly `英文论文题目（期刊名称；年份；最新新锐分区；影响因子；通讯作者；国家单位）`. Keep these six metadata fields in this order inside the same pair of full-width parentheses immediately after the title, separated by full-width semicolons. The year field is the paper's publication year; retain the partition edition and JIF year within their respective fields. Format the last field as `国家—单位`. Do not move any metadata field into a separate paragraph or repeat it in a separate metadata line. Natural line wrapping is allowed; this is one logical title-and-metadata block, not a requirement to shrink text onto one physical line. Preserve the existing English/JCR routing below, using the same field order. Do not show a DOI in the weekly report. A DOI may remain in the internal evidence ledger for verification and disambiguation.

An explicit current user instruction overrides this language routing. Treat the confirmed report-body language as content, not merely as an interface language; do not route from the user's chat language alone.

These values are time-sensitive. Verify them during the current report run from current online or user-provided sources; never reuse an old weekly report's value merely because it was previously confirmed. For Chinese output, prefer the official 新锐期刊分区表 platform; never call 新锐分区 a Chinese Academy of Sciences partition. For English output, prefer Clarivate Journal Citation Reports for both JCR quartiles and Journal Impact Factor. Use a journal or publisher's official page as supporting evidence when appropriate. If an official source is inaccessible and only a secondary source can be checked, label the source and verification limitation instead of presenting the value as officially verified. Never substitute CiteScore, SJR, an institutional metric, an old CAS partition, or a guessed quartile for the routed partition metric or Journal Impact Factor.

Identify corresponding authors from the paper's explicit correspondence markers or correspondence section. Link each author to the affiliations stated in that paper and derive country only from those affiliations or their addresses, not from the person's name or presumed nationality. If multiple corresponding authors or multiple applicable affiliations exist, include all distinct results. For a university affiliation, output only the university name and omit school, faculty, department, institute, center, and laboratory subdivisions. For a non-university affiliation, output the top-level organization such as the company, hospital, research institute, or national laboratory. Preserve an explicit unresolved marker when any field cannot be verified; do not invent it.

Read [references/report-production-rules.md](references/report-production-rules.md) for source priority, normalization, evidence-ledger fields, and report placement. Treat these metadata lines as supporting paper metadata: they add to, rather than replace or compress, the per-paper discussion of problem, method, findings, relevance, and limitations.

## Length and content allocation

Match length by the smallest meaningful semantic content unit inside each section, not by total report length or a fixed whole-section length.

- Literature review: treat each paper as a unit and match each paper's discussion to a comparable paper discussion in the templates.
- Experiments: treat each distinct experiment, result set, or independently supported conclusion as a unit and match it to comparable experiment/result units.
- Code and projects: treat each independently reportable implementation, module, issue, milestone, or conclusion as a unit and match it to comparable units.
- Workplace results: treat each work item, metric/result group, risk, or decision-relevant conclusion as a unit.

Infer unit boundaries from both the templates and current evidence. If a template section covers several units, derive a per-unit length and information-density range from those units; never assign that entire section's length to the current section regardless of how many units it contains. The current section allocation should grow with the number of current units: ten papers normally require substantially more space than one paper, while each paper remains approximately as detailed as a comparable template paper. Apply the same principle to experiments, code conclusions, project items, and business results.

Do not force every unit to exactly the same length. Adjust an individual unit for evidence volume, complexity, importance, and the recipient's priorities, while retaining the template's typical per-unit depth. Shared introductions and summaries may add small section-level overhead but must not replace unit-level coverage.

When a required content type is absent from the templates, exclude covers, contents pages, references, appendices, and decorative slides, then use the average length and information density of identifiable substantive content units—not whole sections—as the initial per-unit target. If no meaningful units can be identified, state the low-confidence assumption in the preview and prioritize complete, non-repetitive evidence coverage. Do not pad with repetition or remove important evidence merely to hit a target.

Read [references/report-production-rules.md](references/report-production-rules.md) before calculating section targets.

## Figures and tables

Embed all non-redundant user-supplied figures and result tables in the main report unless the user explicitly says they do not all need to be included. A table screenshot is redundant when the same result is already available as a genuine native/editable table or when an approved reconstruction has produced an editable table; in those cases, keep the screenshot only in the evidence set unless the user explicitly requests both.

Classify each supplied image before the preview as: table screenshot, chart/plot with axes, or other image.

For every table screenshot, ask whether the user wants it reconstructed as an editable native table. Inventory all detected table screenshots in one question when possible, explain that reconstruction improves editability and readability but requires cell-by-cell transcription, then wait for the answer. Do not reconstruct or replace the screenshot silently.

When the same data is supplied as a genuine native/editable table—such as a DOCX table, XLSX range, CSV/TSV table, or another structured table—use that table and do not include a duplicate screenshot in the report. This case does not require a reconstruction question unless the screenshot contains additional information not present in the native table.

- If the user chooses reconstruction, verify every visible cell against the source image, preserve merged cells, units, footnotes, ordering, and emphasis, and mark unreadable cells instead of guessing. Use the editable table in the main report by default and retain the original image as evidence; include both in the report only when the user requests both.
- If the user declines reconstruction, include the screenshot as an image with a caption and nearby analysis.

Keep production mechanics out of recipient-facing prose. Do not write statements such as `表 2 将原始截图还原为可编辑表格`, `本图已翻译坐标轴`, or other narration about transcription, reconstruction, embedding, conversion, or document production. Present the table or figure directly, then discuss the data, result, comparison, and implication.

For a chart or plot with axes, make the axis language match the confirmed report-body language. When axis titles or textual category labels use another language, create a translated derivative without overwriting the source image. Preserve the underlying plot pixels, data, scale, numeric ticks, units, series, and geometry; translate only the axis titles and textual axis-category labels. Prefer precise text replacement or overlay over generative redrawing. If a technical translation is ambiguous, ask one question before editing. Visually compare the derivative with the original and fail the edit if any data-bearing element changed or became obscured.

- Do not silently drop items to satisfy a template length.
- Preserve axes, units, legends, labels, and meaningful annotations.
- Add a template-consistent figure caption and table title/caption to every figure and table. Inspect caption typography independently from body text and headings. If the applicable template contains figure/table captions, match their font, size, weight, alignment, spacing, numbering, and placement exactly. If it does not contain an applicable caption style, use a restrained default one typographic size step smaller than the body text; this fallback never overrides a template or higher-priority instruction.
- Discuss every figure and table in the surrounding text and state only conclusions it supports.
- If all items cause the report to exceed template length, keep them unless the user authorizes selection or removal.

Do not create an appendix unless the user requests one or an applicable template already contains one. When an appendix is allowed, follow the confirmed template and user requirements; do not move items there merely for convenience without disclosing the choice in the preview.

## Mandatory style preview

After the recipient profile and report style profile are ready and before drafting the complete report, provide a preview containing the following items. Present the recipient-profile items as user-facing confirmation material outside the proposed weekly-report structure:

- a compact recipient-profile summary covering the recipient's primary goals, evaluation criteria, evidence preference, risk/failure preference, decision horizon, and the confidence/source of consequential rules;
- a recipient-fit plan showing which recipient concern or evaluation criterion each substantive section serves and how that changes emphasis or depth;
- proposed title and reporting period;
- proposed section structure;
- a compact typography map for the document title, each heading level that will be used, body text, figure captions, and table titles/captions, including any fallback-derived level; for body text, show the line-spacing mode/value and paragraph spacing before/after;
- when formulas will appear, the formula/equation-number size and whether it comes from the template or the default rule that matches body-text size;
- the number of content units in each semantic section, the target range per unit, and the resulting section length or slide allocation;
- one representative sample passage based only on supplied evidence or clearly marked placeholders;
- one sample figure/table caption when applicable;
- intended placement of all supplied figures and tables;
- the confirmed reconstruction decision for each table screenshot, and whether a native/editable table makes the screenshot redundant and therefore evidence-only;
- the axis-translation plan and body language for each chart whose axis language differs;
- consequential template conflicts or assumptions.
- for each literature-review paper, the selected partition system and language-routing reason, plus the planned `English original title（journal information）` presentation and current verification status of the routed partition, Journal Impact Factor, and corresponding-author country/institution metadata, including any source-access limitation; state that translated titles and DOI are omitted from the report.
- for each literature-review paper, planned coverage of necessary formulas, experimental settings including the dataset or case-study introduction, and experimental results; identify in the preview any genuinely inapplicable item or consequential source gap rather than silently omitting it.
- a compact language-style map covering sentence density, conclusion/process order, voice, technical depth, progress/result phrasing, and prohibited or disliked patterns; the representative passage must demonstrate this language style and must not contain internal audit commentary.
- a plain-language check showing how the template style was adapted for a smart non-specialist reader, including any necessary technical terms and their first-use explanations.

Show unresolved person-identity fields as `xxx` and other unresolved assignment fields as explicit placeholders, never as template-derived values.

At this point, ask whether the user has temporary requirements for this report. Ask one question and explain why it matters. If requirements change, revise the preview. Wait for explicit confirmation; silence or lack of objection is not confirmation.

## Draft and deliver

After both gates pass:

1. Draft the report in the confirmed format and language.
2. Order and emphasize content according to the confirmed recipient profile and recipient-fit map.
3. Keep completed work, ongoing work, blocked work, and planned work distinct.
4. Explain why each research or workplace result matters to the recipient.
5. Preserve decision-relevant negative results, failures, and risks in the recipient's learned language style, but do not append internal evidence-audit explanations, lists of missing experimental metadata, or statements about what the report is not allowed to claim.
6. Use exact values and traceable wording from the evidence ledger.
7. Run a plain-language pass: remove unexplained jargon, internal slang, buzzwords, translation-like phrasing, and abstract padding; confirm that the core point and logic remain complete.
8. Render and visually inspect layout-sensitive outputs. Iterate until text, images, and tables are legible and no element is clipped or misplaced.
9. Run [references/quality-checklist.md](references/quality-checklist.md).

## Recipient feedback loop

After delivering each weekly report, tell the user in one concise sentence that they may send the advisor's or manager's comments, annotations, requested revisions, or verbal feedback on this report. Explain that the feedback can be used to improve the recipient profile for later reports. This invitation is separate from the report and must not be written into the report itself.

When feedback is supplied:

1. Preserve the feedback as a source linked to the report or reporting period it concerns.
2. Separate report-specific corrections from evidence about stable recipient preferences. A factual correction, one-off request, or project-specific decision does not automatically become a reusable profile rule.
3. Compare the feedback with the confirmed recipient profile and prepare a compact proposed change set: rule added, changed, weakened, or removed; source; interpretation; confidence; and scope.
4. Show the proposed profile changes to the user and ask whether the interpretation is correct. Apply corrections before confirmation.
5. Update the reusable recipient profile only after the user confirms the proposed changes. Retain unresolved or weakly supported observations as unconfirmed evidence rather than permanent rules.
6. If the feedback also requires changes to the current weekly report, revise the report when the user requests or clearly expects that revision; do not make profile maintenance a condition for correcting the report.

Do not claim that the recipient personally holds an inferred preference merely because one report received a particular edit. Prefer narrow rules tied to observed feedback, and broaden them only after confirmation or repeated supporting evidence.

Default delivery policy:

- Final weekly report: always deliver.
- Recipient profile: deliver only when first established or updated.
- Report style profile: deliver only when first established or updated.
- Evidence ledger: do not deliver unless the user requests it.
- Post-delivery feedback invitation: provide after every completed weekly report, outside the report artifact.

## Privacy and publication boundary

This Skill may be published publicly, but runtime user data must remain separate. Never add recipient templates, peer templates, recipient preferences, recipient profiles, report style profiles, weekly materials, evidence ledgers, or generated reports to the Skill package or upload them to GitHub unless the user explicitly requests that exact action after reviewing the files.
