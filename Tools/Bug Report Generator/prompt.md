## Prompt
----------------------

```
Create an interactive single-file HTML tool called "BugForge" — an AI-powered API/Backend Bug Report Generator.
DESIGN AESTHETIC:
* Clean light terminal theme using JetBrains Mono + Bebas Neue fonts
* Color palette: white/light grey background (#f4f6f9), red accent (#e03030), cyan (#0099aa), blue (#1a7fd4), green (#00a65a), orange (#e07800), light surface cards (#ffffff), borders (#dde3ea), muted text (#7a8fa6)
* Subtle dot-grid background, soft card shadows, crisp brutalist UI elements
* Two-pane layout: Form (left) | Live Report Preview (right)
* All text, inputs, labels, and report output must be dark on light background
FORM FIELDS (Left Pane):
* Bug Title — with AI chip suggestions that appear as you type (suggests patterns: auth errors, DB failures, timeouts, null refs)
* API Endpoint — with smart REST path suggestions as you type
* HTTP Method selector buttons — GET / POST / PUT / PATCH / DELETE (each with its own color when active)
* Status Code input — auto-detects and labels the code (e.g. 500 → Internal Server Error, colored red/orange/green)
* Expected Response textarea
* Actual Response textarea — AI analyzes the text and shows root cause category chips as you type
* Environment dropdown — Production / Staging / Development / QA
* Severity grid — Critical 🔴 / High 🟠 / Medium 🟡 / Low 🟢 (each with distinct active color styling)
* Priority row buttons — P1 Immediate / P2 High / P3 Normal / P4 Low
* Steps to Reproduce — dynamic list, add/delete steps
* Request Payload / Headers — optional textarea
* Reporter email field
* "⚡ Generate Bug Report" button (red, Bebas Neue font)
AI SUGGESTION BEHAVIOR:
* Title field: pattern-match keywords (auth, jwt, db, timeout, null, 500) and show 3 clickable suggestion chips below the field
* Endpoint field: suggest REST paths based on keywords (users → /api/v1/users/:id, auth → /api/v1/auth/login, etc.)
* Actual response field: detect error patterns and show "Root cause: DB conn failure" style chips
* Clicking any chip fills the corresponding field instantly
GENERATED REPORT (Right Pane): On clicking Generate (with 1.6s AI thinking animation + dots):
* Unique Bug ID (BUG-XXXXXX format) + UTC timestamp
* Report title in large Bebas Neue font
* Colored badge row: Severity + Priority + HTTP Method + Status Code + Environment
* Endpoint block — styled code block showing METHOD + path + status
* Expected vs Actual — side-by-side green/red code blocks
* Steps to Reproduce — numbered list
* Request Payload block (if provided)
* Impact Assessment grid (2×2): Affected Users / Data Risk / Service Uptime / SLA Status — auto-filled based on severity
* AI Root Cause Analysis — blue left-border card with generated explanation
* AI Fix Suggestions — 3–4 actionable bullet points tailored to error type
* Reporter + timestamp footer
* "[ COPY REPORT TO CLIPBOARD ]" button that confirms on click
* "[ DOWNLOAD AS PDF ]" button placed next to the copy button — uses window.print() with a print-specific CSS stylesheet that: hides the form pane, header buttons, and both action buttons, formats the report cleanly for A4 paper with proper margins, preserves all badge colors, code block backgrounds, and section labels, sets the document title to the Bug ID so the saved PDF filename matches the report (e.g. BUG-A3F9K2.pdf)
TECHNICAL REQUIREMENTS:
* Pure single-file HTML/CSS/JS — no frameworks, no external dependencies except Google Fonts
* All AI suggestions are local pattern-matching (no API calls needed)
* Animated score bars, smooth fade-in transitions on report generation
* Status code auto-labels and colors update in real time as user types
* Fully responsive layout (stacks vertically on mobile)
* Copy to clipboard uses navigator.clipboard API
* PDF download uses window.print() with @media print CSS rules
```

----------------------
