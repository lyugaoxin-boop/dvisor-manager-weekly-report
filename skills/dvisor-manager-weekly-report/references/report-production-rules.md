# Report Production Rules

Read this reference before calculating section targets, building the evidence ledger, or producing a format-specific preview.

## Classify the reporting scenario

Use the materials, not the user's job title alone.

### Research scenario

Possible inputs include papers, research notes, experiment logs, code changes, datasets, figures, and result tables.

For each paper, capture:

- title, authors, venue/year when available;
- latest verifiable language-routed journal partition and its edition/year;
- latest verifiable Journal Impact Factor and its JCR/JIF year;
- every corresponding author's name, country, and normalized top-level institution;
- research problem;
- main method;
- necessary formulas, symbol definitions, and source equation numbers;
- experimental settings, including the dataset introduction or simulation/case-study setup;
- concrete experimental results, metrics, comparison conditions, and relevant findings;
- relationship to the user's work;
- limitations;
- source file and page/section.

### Default per-paper coverage

Every literature-review unit should explain the paper's core method and how it was evaluated, not just summarize its abstract. By default include the following, using the paper and any explicitly linked supplementary material as evidence:

1. **Necessary formulas.** Select formulas essential to understanding the main mechanism, optimization objective/loss, or central evaluation metric. Do not copy every equation or impose a fixed formula count. Explain the key symbols, relevant units/conditions, and what the formula does in plain language. Verify signs, subscripts, summation bounds, and constraints against the source; record the original equation number/page internally. Use editable equations where the format supports them, follow confirmed numbering, and keep the existing body-size default. Do not insert unrelated textbook formulas merely to satisfy this rule.
2. **Experimental settings, including a dataset introduction.** Introduce the data's name/source, task and data type, relevant sample or class scale, and train/validation/test split or evaluation protocol when the paper provides them. Summarize preprocessing, baselines, evaluation metrics, and the training parameters, hardware, or operating conditions needed to interpret the selected results; omit irrelevant implementation trivia. For simulation, physical experiments, or case studies without a named dataset, describe the actual test system, scenario, scale, and operating conditions instead of inventing a dataset.
3. **Experimental results.** Give the central measured results with metric names, values, units, dataset/scenario, and a clear comparison baseline. Include key ablation or sensitivity findings when needed to explain the contribution. Preserve relevant negative or mixed results and distinguish absolute differences, percentage points, and relative percentages. Use a compact table when it improves comparison, with nearby plain-language interpretation. Do not replace available concrete results with only “效果更好” or “性能提升”; do not copy every result table from the paper by default.

Keep the settings and results from the same experiment together; never combine one dataset's setup with another dataset's scores. Introduce findings as the paper's experiments or simulations, not as work performed by the user. Map equations, settings, dataset facts, and results to source locations in the internal ledger.

These coverage requirements apply per paper and must be included in its length budget. Match the template's per-paper detail without dropping necessary evaluation evidence merely to retain an old page count; the user may explicitly request a shorter treatment. If a paper genuinely has no relevant formula or no experiments (for example, a survey or theoretical paper), summarize its actual contribution and identify the inapplicable item in the preview rather than inventing a formula or experiment. If the source is incomplete and a consequential required item cannot be verified, ask for the missing material one question at a time, or obtain confirmation of the narrower coverage at the preview gate. Keep routine missing-setting notes internal, in line with the no-audit-commentary rule.

### Current journal metrics and corresponding-author metadata

Run this enrichment for every paper included in a literature-review unit unless the user explicitly disables it for the current report.

#### Source and date rules

These fields change over time. Verify them during the current run and record the retrieval date. Do not carry a partition or impact factor forward from an earlier report without checking that it is still the latest available value.

Select the default partition system from the confirmed deliverable, not from the user's chat language:

1. If both the applicable template and the confirmed report body are Chinese, use the latest **新锐期刊分区表（新锐分区）** edition. Record the edition/year, displayed subject category, zone, and any `Top` or `under review` status shown by the source. The official source is https://www.xr-scholar.com/. 新锐分区 is an independent third-party system published by 新锐学术; never describe or label it as a Chinese Academy of Sciences partition.
2. If both the applicable template and the confirmed report body are English, use the latest **Journal Citation Reports quartile**. Record the JCR year, every applicable Web of Science category, and the quartile for each category. Do not select only the most favorable category.
3. If the template and body languages differ, either language is ambiguous, or the report uses another language, ask one question before the mandatory preview and explain that the answer determines which partition system and labels will appear.
4. A current explicit user instruction can select another partition system and overrides this default routing.

After routing, use this source order:

1. **Chinese route—新锐分区:** the official 新锐期刊分区表 platform. Record the exact edition/year and use the platform's own category and status labels.
2. **English route—JCR quartile:** the latest Clarivate Journal Citation Reports. Record the JCR year and all applicable category/quartile pairs.
3. **Journal Impact Factor:** the latest Clarivate Journal Citation Reports value. Record the JCR/JIF year, which may differ from the current calendar year and from the partition edition.
4. **Supporting official evidence:** the journal or publisher's official page when it identifies the metric and year.
5. **Secondary lookup:** use only when the applicable primary source cannot be accessed. Name the secondary source, record the retrieval date, and label the result as secondary-source verification rather than official verification.

Search snippets alone are not sufficient evidence when the underlying page can be opened. Do not combine a number from one year with a label from another. Do not substitute CiteScore, SJR, an old CAS partition, an unrelated institutional ranking, or a guessed quartile for the routed partition metric or Journal Impact Factor. If no current value can be verified, use a language-appropriate marker such as `[待核验：最新新锐分区]`, `[To verify: latest JCR quartile]`, or `[待核验：最新影响因子]` and state the access or evidence limitation; never guess.

#### Corresponding-author rules

1. Identify corresponding authors only from explicit paper evidence: correspondence symbols, author notes, a “Correspondence” section, or publisher metadata.
2. When there are multiple corresponding authors, list all of them in paper order.
3. Map each corresponding author to every explicitly linked affiliation. Do not assign an affiliation merely because it appears elsewhere in the author list.
4. Derive country from the linked affiliation or postal address. Do not infer nationality or country from a personal name, email domain, language, or presumed background.
5. Normalize the institution for report display:
   - if the affiliation contains a university, output the university name only and omit its school, college, faculty, department, institute, center, laboratory, and address;
   - otherwise output the top-level organization named by the paper, such as a company, hospital, research institute, academy, government agency, or national laboratory;
   - for multiple distinct affiliations, list each normalized `country — institution` pair once.
6. If the paper does not resolve an author, country, or institution, retain an explicit unresolved marker rather than inventing or web-matching a person with the same name.

#### Evidence ledger and report placement

For each metric, record the value, metric name, edition/year, source URL or user-provided source, retrieval date, and verification tier (`official`, `supporting official`, or `secondary`). For corresponding-author metadata, record the paper page/section or publisher location that establishes the correspondence marker and affiliation mapping.

Fit the information into the applicable template without displacing analysis. Use the paper's exact English original title, do not translate it, and place one compact parenthetical journal-information block immediately after the title. Default representations are:

- Chinese route: `英文论文题目（期刊名称；年份；最新新锐分区；影响因子；通讯作者；国家单位）`
  - Field-filled pattern: `Exact English Paper Title（Journal；发表年份；新锐分区：YYYY版，X学科Y区〔Top/under review，如适用〕；影响因子：N〔YYYY JIF〕；通讯作者：姓名；国家—单位）`.
- English route (preserving the existing JCR default): `Exact English Paper Title (Journal; Publication year; JCR quartile: Category A—Qx, Category B—Qy, YYYY JCR; Journal Impact Factor: N, YYYY JIF; Corresponding author: Name; Country—Institution)`

Keep all six fields in the stated order in the same parenthetical block. In Chinese, use full-width parentheses and semicolons; do not merge journal name with publication year using a comma or merge corresponding author with country/institution. The publication-year field must not be confused with the partition edition or JIF year. For multiple corresponding authors or affiliations, preserve their mappings using matching markers within the author and country/institution fields. Unverified values retain an explicit marker in their own field; do not silently drop or reorder fields. Unless a higher-priority explicit instruction overrides this presentation, do not split metadata into a separate paragraph, put it after the analysis, or repeat a standalone “期刊信息” line. Allow natural wrapping without shrinking the text to force one physical line.

Do not show a translated paper title or DOI in the recipient-facing report. Keep DOI and any alternate-language title only in the internal evidence ledger when useful for verification. Treat the parenthetical journal information as supporting metadata outside the per-paper analytical length target; do not shorten the paper's problem, method, findings, relevance, or limitations merely to make room for it.

For each experiment, capture:

- objective and hypothesis;
- setup, dataset, baseline, and metrics;
- exact results;
- interpretation;
- negative results and uncertainty;
- source image, table, log, or file location.

### Workplace scenario

Possible inputs include task lists, project notes, milestone records, business metrics, charts, meeting notes, risks, and next-week plans.

For each work item, capture:

- objective and stakeholder;
- completed action and observable result;
- metric and comparison basis;
- current status: completed / ongoing / blocked / planned;
- dependency or risk;
- next action and owner/date when supplied;
- source file or note location.

### Mixed scenario

Keep research and operational work in separate semantic sections unless the applicable template deliberately combines them.

## Internal evidence ledger

Create an internal table with these fields:

| Claim or report element | Raw source | Exact location | Classification | Allowed wording | Constraint or missing information |
|---|---|---|---|---|---|

Classification values:

- verified fact;
- user interpretation;
- model inference;
- missing information.

Examples of constraints:

- write “提升 2.1 个百分点”, not “提升 2.1%”;
- write “基本收敛”, not “完全收敛”;
- write “开发完成，待测试”, not “全部交付完成”.

The ledger is an internal QA artifact. Deliver it only on request.

## Project evidence into recipient-facing language

The evidence ledger may contain missing settings, unsupported stronger interpretations, and completion constraints. These are control information for drafting, not default report content.

1. Learn language style from multiple representative passages in the highest-authority style sources. Record sentence density, conclusion/process order, paragraph pattern, voice, terminology density, status verbs, comparison phrasing, and treatment of failures, risks, and next steps. Apply those observations only after the plain-language baseline: write for a smart reader with no assumed topic background.
2. Convert each ledger constraint into an allowed positive or neutral statement of current status. State what is supported; do not explain the stronger claim that was rejected.
3. Never insert an evidence-audit paragraph that lists absent thresholds, random seeds, repeated-run statistics, uncompleted planned epochs, unavailable baselines, or similar omissions and then discusses statistical significance, reliability, or what cannot be claimed.
4. Do not write phrases such as “不能据此判断……”“不能声称……” or “由于未提供……因此只能……” as routine report commentary. These may appear in the private ledger but not in the weekly report.
5. If a gap determines future work, write the action directly in the appropriate next-step section, such as `补充多随机种子重复实验` or `继续完成后续训练与验证`, only when that action is supported by the user's materials or confirmed plan.
6. Keep status categories accurate without narrating the audit logic. For example, write `已恢复训练并完成首轮验证`; do not add a paragraph explaining that the planned 100 epochs were not proven complete.
7. Do not hide an actual reported failure, blocker, or decision-relevant risk. Express it in the template's normal concise style and connect it to an action or decision, without surrounding it with methodological self-critique.

This rule changes presentation, not evidence standards: never invent a stronger result merely to make the prose cleaner.

## Plain-language drafting pass

The report should preserve professional substance while removing avoidable difficulty.

1. State the core point early. Make the chain `what was done → what changed or was found → why it matters → next action` visible without requiring the reader to reconstruct it.
2. Prefer familiar words, concrete subjects, and active verbs. Use shorter sentences when a sentence contains several logical turns. Keep one main point per sentence or tightly connected sentence group.
3. Remove internal shorthand, company or laboratory slang, fashionable management terms, empty abstractions, nominalization-heavy phrasing, and literal translation patterns. Do not imitate them merely because they appear in a template.
4. Keep an exact technical term when it is required for scientific accuracy, metric identity, method identification, or source traceability. Explain its practical meaning in plain language at first use. Retain an official English term in parentheses when useful; do not invent a forced translation.
5. Do not oversimplify away conditions that change the meaning of a result. Simplify the wording and sentence structure, not the evidence or logic.
6. Keep professional research, source checking, structural planning, and logical analysis internal. The report should contain the resulting explanation and evidence chain, not a narration of how the draft was constructed or how the reasoning unfolded.
7. Read the final prose as a smart non-specialist. Rewrite any sentence that requires unexplained background knowledge, contains several abstract nouns in a row, or sounds translated rather than naturally written in the report language.

## Separate reusable template rules from instance data

Templates can support reusable observations about labels, placement, typography, hierarchy, captions, section order, and other presentation rules. They do not support reusing the concrete value of an identity- or assignment-specific field.

Do not carry forward values such as:

- reporter, presenter, respondent, author, or other person names;
- student number, employee number, class, team, department, or contact details;
- project, client, product, course, defense topic, or reporting period specific to the old document.

Use the template to reproduce the field label and visual position only. Obtain the current value from the user's present request or materials. When a person-identity field such as reporter, presenter, respondent, or author remains unknown, fill it with the literal value `xxx` without asking. A current value supplied by the user overrides `xxx`. Do not store this fallback as a recipient preference. For a missing project, client, topic, team, period, or other required assignment-specific value, ask one question at a time; keep an explicit `[待补充：...]` placeholder only when the user chooses to proceed without it.

## Match content-unit length

Do not start from a total word/page/slide target or give a semantic section a fixed length independent of its contents. Estimate at the smallest meaningful content-unit level and then aggregate upward.

1. Identify the current units before calculating length:
   - literature review: one unit per paper;
   - experiments: one unit per distinct experiment, result set, or independently supported conclusion;
   - code/project work: one unit per independently reportable implementation, module, issue, milestone, or conclusion;
   - workplace work: one unit per work item, metric/result group, risk, or decision-relevant conclusion.
2. Map each unit type to comparable units in the templates. Do not assume that a template heading equals one unit; split sections that discuss several papers, experiments, or work items.
3. Measure comparable units:
   - text documents: words, paragraphs, heading depth, and figure/table density per unit;
   - presentations: content blocks, bullet density, visual density, and slides or slide fractions per unit;
   - spreadsheets: table blocks, annotations, and summary areas per unit.
4. Derive a per-unit range, preferably from several comparable units. Use the median or a representative range so one unusually long or short item does not control the target. With one example, mark the estimate as low confidence.
5. Calculate the section allocation from the current unit count and the per-unit range, plus only the shared introduction/summary overhead actually needed. For example, a ten-paper review should not receive the same total allocation as a one-paper review merely because the template's review section has a fixed historical length.
6. Adjust each unit for its actual evidence volume, complexity, importance, and recipient priorities. Similar target depth does not require identical word counts or identical slide counts.
7. If a semantic type is absent, exclude cover, contents, references, appendices, and decorative slides, then average identifiable substantive units rather than whole sections. If the templates contain no identifiable comparable units, disclose a low-confidence density assumption and preserve complete evidence without repetition.
8. In the mandatory preview, show the unit count, per-unit target range, and resulting aggregate target for every semantic section. For presentations, units may share a slide when legible; do not force either one unit per slide or all units onto one slide.

All non-redundant supplied figures and result tables remain in the main report by default. Their presence may legitimately make a section longer than the template. Redundant table screenshots stay in the evidence set by default; any other omission or selection requires a user instruction.

## Match typography by role and level

Do not treat “heading style” as one reusable value. Inspect the document title, body text, figure captions, table titles/captions, and every heading level that appears in the applicable templates.

For each heading level, capture and reproduce:

- font family and script-specific fonts;
- font size, weight, italic/underline, and color;
- alignment, numbering pattern, and indentation;
- line spacing and spacing before/after;
- keep-with-next, keep-together, and page-break behavior where present.

Use the heading level's full style as a unit: do not keep its numbering while accidentally applying body text size, and do not make level 1, level 2, and level 3 visually identical. Inspect several examples when available because one paragraph may contain a local override rather than the reusable rule.

If the current report needs a heading level not demonstrated by the applicable template, derive it from the nearest observed levels with a clear, monotonic hierarchy. Mark this as a fallback in the preview instead of presenting it as template evidence.

Treat figure captions and table titles/captions as separate typography roles. When the applicable template demonstrates them, follow the template even if their size equals or exceeds body text. When no applicable caption example exists, default to one conventional typographic size step smaller than body text, preserve readable contrast, and follow the selected format's normal placement convention unless another style source establishes placement.

Treat formulas and equation numbers as another independent typography role. If a current user instruction or a confirmed applicable-template equation style gives a size, use it. Otherwise set formula text and equation numbers to the same point size as body text. Do not reduce formula size solely to avoid reflow; break or reflow long equations without changing their meaning.

Treat body-paragraph spacing as its own template-derived role. Inspect several representative prose paragraphs across substantive sections and capture the effective line-spacing rule—not merely a visual approximation—including its mode (`single`, `multiple`, `exact`, or `at least`), numeric value and units, plus spacing before and after. Separate stable variants for ordinary prose, bulleted or numbered body text, and table-cell text when the template consistently distinguishes them. Ignore isolated local overrides unless repeated evidence shows they are intentional. Never derive body line spacing from a title, heading, caption, equation, or table row alone.

Apply the confirmed body-paragraph rule to newly generated body paragraphs. If the applicable template contains no reliable body-paragraph sample, select a restrained default appropriate to the confirmed output format and body font size, label it as a fallback in the preview, and keep it subordinate to any higher-priority user instruction.

## Format-specific rules

### PPT/PPTX

- Invoke `$ppt-master`.
- Match the selected template's master, layouts, slide size, typography, colors, and recurring elements.
- Keep slides editable.
- Avoid shrinking text to force all items onto fewer slides; add slides within the relevant semantic section when needed.
- Render and inspect every slide.

### DOCX or document output

- Preserve page geometry, styles, the distinct typography and paragraph behavior of every used heading level, the confirmed body-paragraph line-spacing mode/value and spacing before/after, headers/footers, numbering, caption roles, and table formatting.
- Keep figures legible and anchored near their analysis.
- Render the result and inspect pagination, clipping, orphan headings, and broken tables.

### PDF template

- Infer the underlying layout from the PDF.
- Prefer an editable source format when possible; confirm the final deliverable if the expected editable format is unclear.
- Export PDF only after visual verification.

### Markdown

- Preserve heading hierarchy and use relative links or embedded images that remain valid in the user's workspace.
- Do not treat Markdown as a substitute when a template clearly requires a designed PPTX or DOCX.

## Figures, tables, and appendices

- Include every non-redundant supplied figure and result table unless the user says full inclusion is unnecessary. A screenshot duplicating a genuine native/editable table or an approved editable reconstruction is evidence-only by default.
- Preserve original data and legibility; do not redraw or alter results without consent.
- Provide a caption and nearby analysis for every item.
- Do not invent an appendix.
- An appendix is allowed only when the user requests it or an applicable template contains one.

### Table screenshots

Detect images whose primary content is a table. Before drafting, ask whether each detected table screenshot should be reconstructed as an editable table. When several screenshots share the same decision, list them in one question rather than asking repeatedly.

If the same result is already supplied as a genuine native/editable table, use the native table and omit the duplicate screenshot from the report. Do not ask a reconstruction question unless the screenshot contains additional information absent from the native table.

If reconstruction is approved:

1. Transcribe every visible header, row, cell, unit, footnote, merged region, and emphasis cue.
2. Compare the native table cell by cell with the source image.
3. Never infer cropped, blurred, or hidden values; use an explicit unreadable marker and disclose it.
4. Preserve the source image in the evidence set. By default, place the editable table rather than a duplicate screenshot in the report; include both only when requested.

If reconstruction is declined, keep the table as an image and treat it like any other figure.

Do not narrate document-production mechanics in the weekly report. Phrases such as `将原始截图还原为可编辑表格`, `逐单元格转录`, `已嵌入原图`, or `已翻译坐标轴` belong in the private evidence/QA record, not in the table discussion. Recipient-facing text should start from the result shown and explain its meaning.

### Charts with axes

Compare the language of x/y-axis titles and textual category labels with the confirmed body language. If they differ, create a new translated derivative and keep the original unchanged.

- Preserve chart data, plotted geometry, scale, numeric ticks, units, colors, series, and non-axis annotations.
- Translate x/y-axis titles and textual axis-category labels into the body language; do not translate numbers or standard units unnecessarily.
- Use exact text replacement or overlay when possible. Do not regenerate or redraw a scientific result chart merely to change its axis language.
- Ask one question if a domain term has multiple plausible translations that would change interpretation.
- Compare original and derivative at high resolution; translated text must not cover data, ticks, legends, or labels.

## Mandatory preview

The preview must make the final report predictable. Include:

- title and date/period;
- chosen output format and template source;
- section order;
- typography map for document title, every used heading level, body text, figure captions, and table titles/captions, with fallback-derived roles labeled; the body-text entry must state line-spacing mode/value and paragraph spacing before/after;
- when formulas are planned, formula/equation-number size and whether it comes from template evidence or the body-size default;
- language-style map covering sentence density, conclusion/process order, voice, technical depth, status/result phrasing, and prohibited audit-style patterns;
- plain-language adaptation showing which template traits will be retained, which opaque terms or translation-like patterns will be rewritten, and how necessary technical terms will be explained at first use;
- content-unit counts, per-unit length/slide-density targets, and resulting section allocations;
- representative prose;
- per-paper coverage of necessary formulas, experimental settings including dataset or case-study introductions, and concrete experimental results, with any inapplicable item or consequential source gap disclosed for confirmation;
- for every literature-review paper, the selected partition system and routing reason, the planned `English original title（journal information）` presentation, and the verification status of the latest routed partition, Journal Impact Factor, and corresponding-author country/institution fields; translated titles and DOI must be marked as omitted from the report;
- sample caption;
- placement plan for every supplied figure and table;
- table-screenshot reconstruction decisions, including whether an existing or reconstructed native table makes a screenshot evidence-only;
- axis-translation targets and final body language;
- known conflicts and assumptions.

Identity- and assignment-specific values must never be inferred from old template values. Use current user/material values when available, `xxx` for missing person-identity fields, and explicit placeholders for other unresolved assignment-specific fields.

Ask about temporary requirements after presenting the preview. Revise as needed and obtain explicit confirmation before producing the full report.
