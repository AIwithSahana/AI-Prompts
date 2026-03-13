## PROMPT
----------------------

```
Create an interactive single-file HTML tool called "TestForge" —
an AI-powered Unit Test Generator & Analyzer.

DESIGN AESTHETIC:
- Clean light terminal theme using JetBrains Mono + Bebas Neue fonts
- Color palette: white/light grey background (
#f4f6f9), red accent (
#e03030),
  cyan (
#0099aa), blue (
#1a7fd4), green (
#00a65a), orange (
#e07800),
  light surface cards (
#ffffff), borders (
#dde3ea), muted text (
#7a8fa6)
- Subtle dot-grid background, soft card shadows, crisp brutalist UI elements
- Two-pane layout: Form (left) | Live Report Preview (right)
- All text, inputs, labels, and report output must be dark on light background

FORM FIELDS (Left Pane):

- Function / Method Name — with AI chip suggestions as you type
  (suggests: validateUser, fetchData, parseToken, calculateTotal, etc.)

- Programming Language selector buttons —
  JavaScript / Python / Java / TypeScript / Go
  (each with distinct active color)

- Testing Framework — auto-updates based on language selected:
  JS/TS → Jest / Mocha / Vitest
  Python → PyTest / Unittest
  Java → JUnit / Mockito
  Go → testing package
  (shown as clickable selector chips)

- Function Signature / Code Snippet textarea —
  user pastes the actual function code or just the signature.
  AI chips appear below suggesting:
  "Detects: async function", "Detects: return type", 
  "Detects: throws exception", "Detects: has parameters"

- Test Type multi-select grid:
  ✅ Happy Path   ✅ Edge Cases
  ✅ Null / Empty  ✅ Error / Exception
  ✅ Boundary Values  ✅ Async / Timeout
  ✅ Mock / Stub   ✅ Performance
  (checkboxes with colored active states)

- Expected Behavior textarea —
  describe what the function should do in plain English.
  AI chips suggest: "Returns value", "Throws on invalid input",
  "Calls external service", "Modifies state"

- Complexity Level selector:
  Basic / Intermediate / Advanced / Exhaustive
  (4 buttons, each with distinct styling)

- Coverage Target % slider — 60% to 100%
  with live label update (e.g. "Target: 85% coverage")

- Dependencies / Mocks field —
  comma-separated list (e.g. axios, fs, DatabaseService)
  AI chips suggest mock strategies as you type

- Tester Name field
- "⚡ Generate Unit Tests" button (purple, Syne font, full width)

AI SUGGESTION BEHAVIOR:
- Function name field: suggest common function patterns based on keywords
  (auth → validateToken, sanitizeInput; fetch → fetchWithRetry, 
  getData; calc → calculateTax, computeTotal)
- Code snippet field: detect async/await, try/catch, return types,
  parameters — show detection chips like "Async detected → will 
  generate async tests", "Exception found → will test throw cases"
- Expected behavior field: pattern-match to suggest test strategy chips
  ("Add boundary test", "Add null check test", "Add mock for API call")
- Dependencies field: suggest mock patterns
  (axios → jest.mock('axios'), db → jest.spyOn, fs → memfs)
- Clicking any chip fills or appends to the corresponding field

GENERATED TEST OUTPUT (Right Pane):
On clicking Generate (with 1.8s AI thinking animation with typing cursor):

REPORT HEADER:
- Unique Test Suite ID (TEST-XXXXXX) + UTC timestamp
- Suite name: "[FunctionName].test.[ext]"
- Badges row: Language + Framework + Complexity + Coverage Target
- Function signature preview in styled code block

TEST SUITE SECTIONS (generated based on selected test types):

1. HAPPY PATH TESTS
   - 2-3 tests with valid inputs and expected outputs
   - Green left-border card
   - Full code block with proper syntax for selected language/framework

2. EDGE CASE TESTS
   - Empty string, zero, negative numbers, max values
   - Yellow left-border card
   - Code block with describe/it or def test_ style

3. NULL / UNDEFINED / NONE TESTS
   - Tests for missing or null parameters
   - Orange left-border card

4. ERROR / EXCEPTION TESTS
   - expect(() => fn()).toThrow() style
   - Red left-border card

5. ASYNC / TIMEOUT TESTS (if async detected)
   - async/await test patterns, Promise rejection cases
   - Blue left-border card

6. MOCK / STUB TESTS (if dependencies provided)
   - Auto-generated mock setup block
   - jest.mock() / unittest.mock / patch decorators
   - Purple left-border card

COVERAGE SUMMARY CARD:
- Estimated coverage % bar (animated fill)
- Lines covered / Branches covered / Functions covered
- Color-coded: green if meets target, red if below

AI ANALYSIS CARD:
- "What these tests cover" — plain English summary
- "What is NOT covered" — gaps identified
- "Recommended additions" — 2-3 extra test ideas

TEST METADATA FOOTER:
- Tester name + timestamp + Suite ID
- Total test count badge
- Estimated execution time

ACTION BUTTONS (below report):
- "[ COPY ALL TESTS ]" — copies only the code blocks to clipboard
- "[ COPY FULL REPORT ]" — copies entire report with analysis
- "[ DOWNLOAD AS PDF ]" — uses window.print() with @media print CSS:
  hides form pane and action buttons,
  formats report cleanly for A4 paper,
  preserves all syntax colors and badge colors,
  sets document title to Suite ID (e.g. TEST-B7X2K1.pdf)

TECHNICAL REQUIREMENTS:
- Pure single-file HTML/CSS/JS — no frameworks, no external dependencies
  except Google Fonts
- All test generation is local pattern-matching and template logic
  (no API calls needed)
- Framework auto-switches test syntax style when language/framework changes
- Coverage bar animates on report generation
- Smooth fade-in panel transition on generate
- Test type checkboxes dynamically show/hide relevant test sections
- Fully responsive layout (stacks vertically on mobile)
- Copy to clipboard uses navigator.clipboard API
- PDF uses window.print() with @media print rules
```

----------------------
