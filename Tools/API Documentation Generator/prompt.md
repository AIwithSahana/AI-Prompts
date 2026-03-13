## Prompt
----------------------

```

Create an interactive single-file HTML tool called "DocForge" — an AI-powered API Documentation Generator with charts and diagrams.

DESIGN AESTHETIC

Clean, editorial white background (#ffffff) with crisp ink-black typography
Font pairing: Bebas Neue for all headings/labels + JetBrains Mono for code/body text
Accent palette: deep navy (#0f1f3d), electric blue (#1a7fd4), emerald (#00a65a), amber (#e07800), crimson (#e03030)
Subtle fine-line grid background (1px lines, 40px grid, opacity: 0.04) on white
Two-pane layout: Form (left, 460px) | Live Doc Preview (right, scrollable)
Thin 2px borders, sharp corners, no rounded pill shapes — crisp brutalist editorial feel
All text dark on white — zero dark backgrounds except code blocks (#f8f9fa tinted)
Thin colored left-border accents on section cards instead of heavy backgrounds


FORM FIELDS (Left Pane)

API Name — with AI chip suggestions as you type (e.g. "User Service API", "Payment Gateway API")
Base URL — smart suggestions (e.g. https://api.example.com/v1)
API Version — input with format hint (e.g. v1.2.0)
Authentication Type — toggle button group: None / API Key / Bearer JWT / OAuth 2.0
Endpoint Builder — dynamic list where each row has:

Method selector (GET/POST/PUT/PATCH/DELETE — color coded)
Path input (e.g. /users/:id)
Short description input
Add / Delete row buttons


Response Format — JSON / XML / GraphQL toggle buttons
Environment — Production / Staging / Sandbox selector
Rate Limiting — input for requests/minute (e.g. 1000 req/min)
Tags / Categories — comma-separated input (e.g. auth, users, billing)
Description — textarea for overall API description
"⚡ Generate Documentation" button — navy blue, Bebas Neue, full width


AI SUGGESTION BEHAVIOR

API Name field: suggest based on keywords — "payment" → "Payment Gateway API", "user" → "User Management Service", "auth" → "Authentication & Identity API"
Base URL: auto-suggest REST patterns based on API name
Endpoint path: suggest common REST paths based on method + keywords typed
Description field: show "tone chips" — Technical, Developer-Friendly, Enterprise, Minimal — clicking sets a writing tone for generation


GENERATED DOCUMENTATION (Right Pane)
On clicking Generate (with 1.8s AI thinking animation):
Header Block

Large API name in Bebas Neue (48px)
Version badge + Environment badge + Auth type badge in a row
Base URL in a styled code block with a copy button
One-paragraph AI-generated description

Quick Stats Bar — 4 inline metric cards:

Total Endpoints | Auth Method | Rate Limit | Response Format

Architecture Diagram — pure SVG/Canvas drawn inline:

Shows a flow: Client → API Gateway → Auth Layer → [Endpoints] → Database
Each node is a labeled box with connecting arrows
Color-coded by layer (client=blue, gateway=navy, auth=amber, db=green)
Animated dashed lines showing request flow direction

Endpoint Reference Table

Full-width table with columns: Method badge | Path | Description | Auth Required | Response Code
Alternating row shading (#f8f9fa)
Each row expandable (click to reveal) showing a mock request/response JSON block

Request Flow Diagram — SVG sequence diagram style:

Shows the lifecycle of one example request end-to-end
Swimlanes: Client / Gateway / Auth / Service / Database
Labeled arrows with HTTP method + status codes

Rate Limit Gauge Chart — SVG arc/donut gauge:

Shows current rate limit visually as a semi-circle gauge
Colored zones: green (0–60%), amber (60–85%), red (85–100%)
Animated fill on load

Endpoint Distribution Chart — SVG horizontal bar chart:

Bars per HTTP method (GET/POST/PUT/DELETE) showing count
Each bar colored by method, animated width on load
Clean axis labels in JetBrains Mono

Authentication Flow Diagram — SVG flowchart:

Varies based on selected auth type
API Key: simple header injection flow
Bearer JWT: token request → validate → access flow
OAuth 2.0: full authorization code flow diagram

Error Code Reference — table of standard HTTP error codes with descriptions, auto-populated based on endpoint methods used
Copy & Download buttons — fixed at bottom of right pane (outside scroll), always visible:

[ COPY AS MARKDOWN ] — formats entire doc as clean Markdown
[ DOWNLOAD AS PDF ] — uses window.print() with print CSS


TECHNICAL REQUIREMENTS

Pure single-file HTML/CSS/JS — no frameworks, no external dependencies except Google Fonts
All charts and diagrams are hand-drawn SVG — no Chart.js, no D3, no external libraries
SVG elements animate on load using CSS stroke-dashoffset and transform animations
Diagrams re-generate fresh each time based on actual form input data
Endpoint table rows expand/collapse with smooth CSS max-height transitions
Status code auto-colors (2xx green, 4xx orange, 5xx red) everywhere they appear
html, body set to overflow: hidden — only the two panes scroll internally with min-height: 0 on grid children
Copy uses navigator.clipboard API with visual confirmation

```

----------------------
PDF uses window.print() with @media print CSS that hides the left form pane and all action buttons
Fully responsive — stacks vertically on mobile
Reset button in header clears all fields and hides the doc panel
