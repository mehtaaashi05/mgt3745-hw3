# Canonical agent instructions

Status: ACTIVE in Module 3. Read context/STANDARDS.md and the selected scope in FEATURES.md before editing. STANDARDS.md is normative; report and repair conflicting instruction wording.

- In `app.js`, use names that distinguish the directory's roles: `notes` is the saved list, `candidate` is the submitted value, and `nextNotes` is the proposed replacement. Do not collapse these into generic names like `data` or `value`.
- Put user-facing elements and their initial attributes in `index.html`, visual states in `styles.css`, and storage or interaction decisions in `app.js`. A feature is incomplete if its logic is split across those boundaries.
- Comment the directory's invariants when they could be accidentally broken. Leave self-evident DOM operations uncommented.
- Begin each commit message with an action verb and name the user-visible result (for example, "keep note text after a failed save."), never a vague message like "update files."
- When rendering user-entered note text, use DOM APIs and `textContent`. Do not use `innerHTML`, `outerHTML`, or `insertAdjacentHTML` on note content.

Colleague test:
- Who read it?: Regina
- What they misunderstood or asked about?: She was confused by what a user-visible result meant and thought an example would help.
- The revision I made: I added a concrete example to the commit-message rule so the agent has a clearer target: "keep note text after a failed save."

Root `CLAUDE.md` imports this file for Claude Code. VS Code Copilot uses the separate `.github/copilot-instructions.md` adapter. A location under `/context` alone is not a guarantee of automatic discovery.
