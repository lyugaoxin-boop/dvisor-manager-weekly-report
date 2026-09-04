# Style Profile Schema

Use this schema when establishing or updating a reusable recipient style profile. Record only information supported by a user statement or a supplied template. Mark inferences explicitly.

## Profile metadata

- Recipient role: advisor / manager / other
- Profile version:
- First confirmed date:
- Last updated date:
- Status: draft / confirmed
- Available sources:
  - user-described preferences;
  - recipient template;
  - unlabeled reference template, classified as recipient template by default;
  - peer template.
- Reason for update:

## Authority and conflicts

- Current-report temporary requirements: never persist here unless the user says they are permanent.
- User-described recipient preferences:
- Recipient-template rules:
- Unlabeled-template classification record: file/template identifier, default recipient classification, and any later user correction;
- Peer-template rules:
- Conflicts found:
- Selected rule and reason:

## Communication preferences

- Primary concerns:
- Conclusion-first or process-first:
- Formality:
- Preferred person and voice:
- Preferred concision/detail:
- Sentence and paragraph style:
- Expected quantitative evidence:
- Treatment of failures and uncertainty:
- Treatment of risks and blockers:
- Expected specificity of next steps:
- Preferred terminology:
- Disliked expressions or patterns:

## Recipient-facing language style

- Plain-language baseline: smart reader with no assumed topic background; simple, direct wording; core point and logic understandable on first read.
- Evidence passages inspected:
- Typical sentence length and information density:
- Conclusion-first / process-first pattern:
- Paragraph organization and transition pattern:
- Preferred verbs and degree of certainty:
- First person / passive voice / impersonal phrasing:
- Bullet-versus-prose balance:
- Technical terminology density:
- Necessary technical terms and first-use plain-language explanations:
- Jargon, internal shorthand, buzzwords, opaque abstractions, and translation-like phrases to rewrite rather than imitate:
- Progress-status phrasing:
- Result-and-comparison phrasing:
- Failure, risk, and next-step phrasing:
- Internal evidence constraints that must remain out of the report:
- Prohibited audit-style patterns: do not list missing thresholds, random seeds, repeat statistics, incomplete planned epochs, or similar evidence gaps and then explain what cannot be concluded or claimed.
- Preferred evidence compression: state the strongest supported current result directly; move any necessary follow-up into a concise next action.
- Confidence and source for each rule:

Record template-derived language rules only after applying the plain-language baseline. The template may change tone, rhythm, sentence length, order, and detail, but it does not authorize unexplained jargon or hard-to-follow prose. A current explicit user instruction for a specialist audience may change how much standard terminology needs explanation; record that instruction and its scope.

## Document structure

- Default output format:
- Date format:
- Title format:
- Section order:
- Required sections:
- Conditional sections:
- Document-title style:
- Heading hierarchy: record level 1, level 2, level 3, and deeper levels separately; for each include font family, size, weight, color, alignment, numbering, indentation, line spacing, spacing before/after, and keep/page-break behavior.
- Body-paragraph style: font attributes, alignment and indentation; effective line-spacing mode (`single`, `multiple`, `exact`, or `at least`) and value with units; spacing before/after; evidence samples; and any stable variants for ordinary prose, lists, or table-cell text.
- Header/footer and numbering:
- Identity/assignment field labels and placement (labels only, never prior values):

## Non-reusable template content

- Person names or roles tied to a specific person (reporter, presenter, respondent, author):
- Student/employee IDs, class, team, department, and contact details:
- Prior project, client, product, course, defense topic, and reporting period values:
- Other instance-specific values excluded from the reusable profile:

Record only the exclusion rule or field label/placement. Never store the old concrete value as a reusable preference.

The literal `xxx` fallback for a missing reporter, presenter, respondent, or author is a Skill execution default. Do not record it as a recipient-specific preference.

## Section-level length model

For each observed semantic section, record a range rather than one brittle exact value.

| Semantic section | Source | Typical length/slides | Information density | Figure/table density | Confidence |
|---|---|---:|---|---|---|
| Overview | | | | | |
| Literature/research | | | | | |
| Experiment/results | | | | | |
| Project/work progress | | | | | |
| Risks/problems | | | | | |
| Next steps | | | | | |

## Visual system

- Page or slide size:
- Fonts and hierarchy: distinguish document title, every observed heading level, body text, figure caption, and table title/caption; never collapse them into one generic typography note.
- Colors:
- Margins and spacing: include page margins plus the confirmed body-paragraph line spacing and paragraph spacing; do not collapse these into a vague “comfortable” or “compact” note.
- Figure placement:
- Table style:
- Figure-caption style: source, font, size, weight, alignment, spacing, numbering, and placement.
- Table-title/caption style: source, font, size, weight, alignment, spacing, numbering, and placement.
- Caption fallback when the template has no applicable example: one typographic size step smaller than body text, unless a higher-priority instruction says otherwise.
- Formula/equation style: source, font, point size, line spacing, alignment, equation-number style and placement. If neither the user nor an applicable template establishes a size, record the Skill fallback `same point size as body text`; label it as an execution fallback, not a recipient preference.
- Image-to-text balance:
- Appendix behavior:

## Evidence and claim style

- Citation style:
- Number formatting:
- Comparison phrasing:
- Accepted inference language:
- Required caveats:
- Recipient-visible caveat policy: keep ordinary evidence limitations in the internal ledger; do not turn them into report prose. If a status must be narrowed, write only the supported status.

## Confirmation record

- Preview shown:
- User corrections:
- User confirmation:
- Items still uncertain but non-blocking:

## Persistence rules

- Reuse a confirmed profile in later weeks.
- Update only for new templates, new permanent preferences, or explicit reanalysis.
- Do not convert a one-week temporary requirement into a permanent preference without consent.
- Store the profile with user runtime data, never inside the public Skill package.
