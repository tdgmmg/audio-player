````markdown
# AGENTS.md (Audio Player)

This document defines the agent roles, prompt scaffolds, and operating conventions for the Standalone Timer project. It ensures consistent AI- and human-driven development, documentation, and reporting.

---

## Purpose

Provide clear guidance for:
- Generating and maintaining code, UI, and docs via Codex
- Structuring prompts for predictable, testable output
- Logging, metrics, and traceability of AI-driven edits

---
````
## Setup

````bash
# Clone and prepare environment
git clone <repo-url>
cd standalone-timer
npm install               # if node dependencies exist
````

---

## Folder Structure Overview

````
/
├── scripts/               # Core timer logic (GS or JS)
├── ui/                    # HTML/CSS for web UI
├── config/                # Environment/configuration files
├── docs/                  # Documentation and diagrams
└── codex/                 # AI scaffolds, agents, self-eval logs
````

---

## Codex Prompt Scaffold

Use this template for every Codex invocation:

```text
// >>> [zoneName]             ← zone marker start
// ROLE:
//   e.g. “Timer Logic Agent”

// TASK:
//   One-line summary of the change (e.g. “Implement start/stop button handlers in scripts/timer.js”).

// CONTEXT:
//   - Project type: Standalone Timer (GAS or plain JS Web App)  
//   - Relevant files: scripts/timer.js, ui/index.html  
//   - Helpers available: logStep(), metrics.log(), render()  
//   - Constraints: no external libraries, ES5 syntax for GAS, 80-char line limit.

// EXAMPLE:
//   Input: user clicks “Start”  
//   Output: timer begins counting, UI updates every second.

// INSTRUCTIONS:
//   1. Modify only within the `// >>> [zoneName]` … `// <<< [zoneName]` block.  
//   2. Add JSDoc comments (`@param`, `@returns`, `@sideEffect`).  
//   3. Insert `logStep('timer', 'start', { time: timestamp })`.  
//   4. Append an “Explanation:” comment block listing assumptions.  
//   5. Update docs/READMETIMER.md “Usage” section with any new UI behaviors.  
//   6. Append entry to docs/PromptLog.md with today’s date and full prompt text.  
//   7. Commit to branch: `codex/feature-<short-description>`.
//
// <<< [zoneName]             ← zone marker end
```

---

## Agent Roles

### Software Architect Agent

* Defines high-level design and breaks features into prompts
* Reviews and sequences Codex tasks
* Maintains project roadmap and architecture docs

### Codex Agent

* Executes scoped prompts within zone markers
* Generates or modifies code, UI, and docs
* Emits “Explanation” comments and follows prompt scaffold

### QA Agent (future)

* Runs unit/UI tests (e.g. `runAllTests()`, headless UI checks)
* Validates behavior matches spec
* Reports pass/fail back to PromptLog

### Notes Composer

* Assembles change summaries and updates CHANGELOG.md
* Maintains docs/PromptLog.md and docs/README.docs index
* Prepares release notes

### Logging Agent

* Ensures all code paths emit structured logs
* Updates LOGGING\_STRATEGY.md with new events
* Aggregates metrics via metrics.log()

---

## Documentation Expectations

Whenever code or UI changes, update:

* **docs/ARCHITECTURE.md** – module & data flow overview
* **docs/READMETIMER.md** – user instructions and UI reference
* **docs/FUNCTION\_INDEX.md** – list of all public functions + one-line purpose
* **docs/CALL\_MAP.md** – function-to-function call relationships
* **docs/LOGGING\_STRATEGY.md** – events, payload formats, sample logs
* **docs/CODING\_CONVENTIONS.md** – naming, style, zone markers
* **docs/CODEX\_USAGE.md** – prompt scaffolds and agent workflows
* **docs/PromptLog.md** – append each prompt run with date and text
* **CHANGELOG.md** (root) – record all changes under `## [Unreleased]`

---

## Pull Request Protocol

Before opening a PR:

* [ ] All manual tests or `runAllTests()` pass
* [ ] JSDoc and inline comments are complete
* [ ] Zone markers correctly scoped
* [ ] Relevant docs updated and PromptLog entry created
* [ ] Descriptive PR title, one feature/fix per PR

---

*This AGENTS.md is the authoritative reference for all AI- and human-driven contributions to the Standalone Timer project.*

```
```
