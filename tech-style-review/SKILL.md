---
name: tech-style-review
description: Checks pasted technical content against technical writing style and standards - specifically the GOV.UK Technical A to Z style guide, the GOV.UK writing guidelines, and the Google developer documentation style guide - and returns a review table of specific issues, proposed changes and citations to guidance. Use for a formal style check, proofread, or "2i review" of API documentation, developer guides, installation instructions, terminal/command-line content, or any content aimed at a technical practitioner audience.
---

## What I do

Output a markdown table with exactly these columns, in this order, and nothing else - no introductory sentence, no summary paragraph, no sign-off. If something doesn't fit neatly into a row (like a pattern that repeats many times through the piece), add one short line after the table, not before it.

| Original content | Proposed change | Reason for the change | URL of guidance | Section of guidance | Confused / Uncertain? |

Column by column:
- **Original content** - the exact verbatim wording that needs to change, quoted
- **Proposed change** - the fix based on technical writing best practice, quoted
- **Reason for the change** - 1 to 2 sentences, not a paragraph. Bold the name of the principle where you introduce it (like "**Passive voice** makes this harder to follow" or "**UI label formatting** should use bold, not quotes"), then explain the effect on the reader in clear terms - not just naming the rule
- **URL of guidance** - a direct link from the primary reference sources below. Add the page's anchor (#) only if you're confident it exists; if you're not sure of the exact anchor, link to the page itself without one rather than guessing a fragment that might be wrong
- **Section of guidance** - the name of the relevant style guide entry, so I can find it if I need to check
- **Confused / Uncertain?** - for every row, actively check before you leave it blank: am I fully confident in this fix and this citation? Use the column when you're not - either because you're genuinely unsure a fix is right, because you'm not confident the "Section of guidance" or "URL of guidance" is the correct one, or to flag something outside pure style that I should check myself (like source formatting, page-extraction artefacts, or a term that might be a defined technical term rather than a style choice). Blank means checked and confident, not skipped.

## Primary reference sources

Two separate tracks depending on the type of issue:

**For technical terminology and style rules** (how to name things, format code, write procedures, refer to UI elements):
1. **GOV.UK Technical A to Z style guide** - https://guidance.publishing.service.gov.uk/writing-to-gov-uk-standards/style-guides/technical-a-to-z/
2. If not covered there: **Google developer documentation style guide** - https://developers.google.com/style

**For content design and writing approach** (plain English, active voice, sentence structure, tone, requirements language):
1. **GOV.UK writing guidelines** - https://guidance.publishing.service.gov.uk/writing-to-gov-uk-standards/writing-guidelines/
2. If not covered there: **GOV.UK A to Z style guide** (formatting and style conventions) - https://guidance.publishing.service.gov.uk/writing-to-gov-uk-standards/style-guides/a-to-z-style-guide/

## Core principles to check against

### Clear language (GOV.UK)
- **Plain English** - use short, familiar words. 'buy' not 'purchase', 'help' not 'assist', 'about' not 'approximately', 'fix' not 'address'
- **Sentence length** - flag sentences over 25 words; flag paragraphs over 5 sentences
- **Active voice** - flag passive constructions; make the actor and action explicit
- **Requirements language** - 'must' for legal/hard requirements; 'should' for recommendations; 'can' for options. Flag 'may', 'you may want to', 'it may be possible to', 'where possible you'
- **Negative contractions** - avoid 'can't', 'don't'; use 'cannot', 'do not'
- **Words to avoid** - flag GOV.UK's banned list: 'action' (verb), 'allow' (use 'let'), 'assets' (use 'files' or 'documents'), 'consult' (use 'check'), 'detail' (verb, use 'explain' or 'tell'), 'easy'/'easily', 'enable' (use 'help' in running text, or 'turn on' for a setting), 'ensure' (use 'make sure'), 'examine' (use 'check'), 'fulfil' (use 'meet'), 'in order to' (use 'so you can'), 'inform' (use 'show' or 'tell'), 'periodically'/'regularly' (be specific), 'quick'/'simple', 'refer to' (use 'read more about' or 'find out how to'), 'requires' (use 'needs'), 'should the' (use 'if the'), 'take place' (use 'happen'), 'underlying'

### Technical terminology (GOV.UK Technical A to Z)
- **Specific spellings**: backend (not 'back-end' or 'back end'), frontend (not 'front-end'), filename (not 'file name'), microservices (not 'micro-services'), downtime/uptime (one word), onscreen (one word), data type (not 'datatype')
- **Preferred terms**: folder (not 'directory'), fix (not 'address'), get (not 'receive'), get started (not 'quickstart'/'quick start'), set up (not 'spin up'/'stand up'/'instantiate'), Terminal (for Mac-specific audience; not 'the command-line' or 'CLI'), run a test or command (not 'conduct'/'execute'/'perform'/'type'), problems (not 'issues' or 'defects'), third party (not 'third-party organisation')- **'choose' vs 'select'**: 'choose' for genuine user choice; 'select' when indicating the correct/appropriate response
- **Turn on/turn off**: not 'enable'/'disable'

### Capitalisation of product and technology names (GOV.UK Technical A to Z)
- JavaScript, GitHub, Git (capital G, except `git` command in code), macOS (lower case m), iOS (lower case i), HTTPS, REST, GraphQL, Python, Ruby, JAWS, NVDA, Mozilla Firefox, Google Chrome (not just 'Chrome'), GOV.UK Design System, GOV.UK Pay, GOV.UK One Login

### Procedures
- **Introductory sentences**: introduce procedures with a sentence or imperative statement ending in a colon or period - not a partial sentence completed by the steps. 'To do X:' or 'Do the following:' - not 'To do X:' followed immediately by '1.' without a verb
- **Step structure**: each step starts with an imperative verb; state the location/context before the action ('In a terminal, run...'); state the goal before the action ('To start a document, click **File**'); keep one action per step
- **Step explanations**: steps do not need explanations inline. Only add one where the action is obscure or ambiguous — this is most likely with terminal commands, where it may not be obvious what a command does. When an explanation is needed, the format is: '[To do thing], run:' followed by the code block. Any explanation of the overall outcome of a series of steps belongs after the list, not inside each step
- **Lead-in lines**: numbered steps do not need a lead-in line that just restates the heading
- **'Please'**: do not use 'please' in instructions
- **'Run the following command'**: avoid this; instead, focus on what the command does. Use 'In a terminal, deploy the load generator:' or 'Define a firewall rule:' rather than 'Run the following command:'
- **Optional steps**: mark as 'Optional:' at the start of the step, not '(Optional)'
- **No directional language**: do not use 'above', 'below', 'on the left', 'to the right' to locate UI elements. If an element is hard to find, use a screenshot or include the icon/tooltip name (avoid location descriptions; they cause accessibility and maintenance problems)
- **Single-step procedures**: format as a bulleted item, not a numbered list

### Code blocks and inline code
- **Use code blocks for anything the user needs to copy or paste**: this includes terminal commands and any other interface where content must be entered exactly - for example, search fields in Slack or other tools. Format the lead-in as '[To do thing], run:' for terminal commands or '[Action]:' for other interfaces (for example, 'To start OpenCode in Terminal, run:' or 'Search:'). The code block follows immediately on the next line
- **Use inline code for references**: use inline code when referring to a specific parameter, flag, filename, value, or code element within a sentence (for example, 'the `--source` flag', 'the `mv` command moves a file')
- **Code font items** (Google): attribute names, class names, command output, data types, filenames and paths, HTML element names, HTTP status codes, HTTP methods, method/function names, placeholder variables, environment variable names, package names, query parameter names
- **No code font for**: product names, service names, domain names, URLs for browsing
- **Introduce code blocks**: before giving example code, describe what it does. 'Run the following code to...' or better, state what the step achieves as the step's lead text

### UI elements
- **Bold for UI labels**: use bold for all UI element names (buttons, menus, dialogs, field labels, checkboxes). Not quotes, not code font (unless the element is rendered from code). Example: select **OpenCode Zen** - not 'select "OpenCode Zen"' and not 'select `OpenCode Zen`'
- **Capitalisation**: follow the capitalisation as it appears in the UI (interface-consistent). If labels are all-caps in the UI, use sentence case in the documentation
- **'select' not 'click'** for menu items and options (GOV.UK Technical A to Z: 'select' when indicating the appropriate response); use 'click' only for buttons you physically click
- **'press' for keyboard keys**: 'press Return', not 'press the Return key' (unless clarification is needed)
- **No directional language**: do not describe where a button is on screen. Use the button's name or tooltip instead
- **Prepositions**: 'in' for dialogs, fields, menus, panes, windows; 'on' for pages, tabs, toolbars

### Voice, tone, and audience (Google)
- **Second person**: use 'you', not 'we', for instructions
- **Conversational but not casual**: avoid exclamation marks, slang, pop-culture references, 'simply', 'it's that easy', 'quickly'
- **Pronouns**: avoid ambiguous pronouns like 'it' when referring to a product. Use the product name. Example: 'OpenCode lets you...' not 'It lets you...'
- **Consistent product names**: capitalise consistently and match the official name throughout. 'OpenCode' not 'Opencode'

## When to use me

Use me when content is pasted and a formal check against technical writing guidance is clearly being asked for, including when a "2i review" is requested of technical content - API docs, developer guides, installation instructions, terminal/command-line guides, or how-tos for a technical audience.

Do not trigger just because technical content has been pasted - most of the time, pasted content in a discussion means the user wants to think it through, not get a formal check.

## Output approach

Only add a row where there's an actual proposed change - do not pad the table with rows confirming something is already fine, unless asked for a full audit trail. If nothing needs to change, say so in a single line instead of an empty table.

Example of the format (illustrative only - never reuse this example's wording, always generate real rows from what I've actually given you):

| Original content | Proposed change | Reason for the change | URL of guidance | Section of guidance | Confused / Uncertain? |
|---|---|---|---|---|---|
| "Open Terminal and run the following in the command line:" | "Open Terminal and run:" | **Redundant wording** - 'in the command line' is implicit once the user has opened Terminal; removing it keeps the instruction short. | https://guidance.publishing.service.gov.uk/writing-to-gov-uk-standards/writing-guidelines/clear-language/ | Use clear language | |
| "then click 'Download raw file'" | "then select **Download raw file**" | **UI label formatting** - UI labels should be bold, not in quotes. 'Select' is preferred over 'click' for choosing an item from an interface. | https://developers.google.com/style/ui-elements | UI elements and interaction | |
| `In Terminal, type: mv ~/Downloads/opencode.json ~/.config/opencode/opencode.json` | Change lead text to 'In Terminal, run:' and put the command in a fenced code block on the next line | **Command formatting and verb choice** - all commands the user needs to copy should be in a code block; 'run' is preferred over 'type' because typing alone does not execute a command. | https://developers.google.com/style/code-syntax | Document command-line syntax | |
