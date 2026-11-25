---
name: style-review
description: Checks pasted content against GOV.UK style and standards and returns a review table of specific issues, proposed changes and citations to guidance. Use for a formal style check, proofread, or a "2i review" - not for a general discussion of the content.
---

## What I do

Output a markdown table with exactly these columns, in this order, and nothing else - no introductory sentence, no summary paragraph, no sign-off. If something doesn't fit neatly into a row (like a pattern that repeats many times through the piece), add one short line after the table, not before it.

| Original content | Proposed change | Reason for the change | URL of guidance | Section of guidance | Confused / Uncertain? |

Column by column:
- **Original content** - the exact verbatim wording that needs to change, quoted
- **Proposed change** - the fix based on content design best practice, quoted
- **Reason for the change** - 1 to 2 sentences, not a paragraph. Bold the name of the principle where you introduce it (like "**Passive voice** makes this stiffer" or "**Brackets for plurals** aren't standard style here"), then explain the effect on the user in clear terms - not just naming the rule
- **URL of guidance** - a direct link from the primary reference sources in your main instructions. Add the page's anchor (#) only if you're confident it exists; if you're not sure of the exact anchor, link to the page itself without one rather than guessing a fragment that might be wrong
- **Section of guidance** - the name of the relevant style guide or writing guideline entry, so I can find it if I need to check
- **Confused / Uncertain?** - for every row, actively check before you leave it blank: am I fully confident in this fix and this citation? Use the column when you're not - either because you're genuinely unsure a fix is right, because you're not confident the "Section of guidance" or "URL of guidance" is the correct one, or to flag something outside pure style that I should check myself (like source formatting, page-extraction artefacts, or a term that might be a defined legal term rather than a style choice). Blank means checked and confident, not skipped.

## When to use me

Use me when I paste content and clearly ask for a formal check against the guidance, including when I ask for a "2i review" - that specifically means this table (typos, grammar and GOV.UK style together, in the same pass), not a discussion, even though the term itself sounds conversational.

Don't trigger just because content has been pasted - most of the time, pasted content means I want to think it through with you instead (use the discuss skill). Check what's actually being asked for.

If the draft-content or draft-presentation skills are running, this same check happens automatically as part of self-review before a draft is shown to me, so I don't need to ask for it separately there.

## Output approach

Only add a row where there's an actual proposed change - don't pad the table with rows confirming something's already fine, unless I ask for a full audit trail. If nothing needs to change, say so in a single line instead of an empty table.

Example of the format (illustrative only - never reuse this example's wording, always generate real rows from what I've actually given you):

| Original content | Proposed change | Reason for the change | URL of guidance | Section of guidance | Confused / Uncertain? |
|---|---|---|---|---|---|
| "You must ensure that the form is completed by no later than the deadline date." | "You must complete the form by the deadline." | **Passive voice and wordiness** - "ensure that" and "no later than" add words without adding meaning, and bury the actual instruction behind them. | https://guidance.publishing.service.gov.uk/writing-to-gov-uk-standards/style-guides/a-to-z-style-guide/ | Active voice | |
| "Applicants (s)" | "Applicants" | **Brackets for plurals** aren't standard GOV.UK style - use the plural form instead so it reads cleanly either way. | https://guidance.publishing.service.gov.uk/writing-to-gov-uk-standards/style-guides/a-to-z-style-guide/ | Brackets | Not sure if "Applicants" loses a distinction the original text needed (singular vs joint applications) - worth checking against the source before using this fix. |