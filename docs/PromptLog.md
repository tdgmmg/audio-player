# Prompt Log

## 2025-07-14
// >>> [scaffoldDocsAndCodex]             ← zone marker start
// ROLE:
//   Project Documentation Agent

// TASK:
//   Scaffold the core documentation and Codex directories for the Standalone Timer project.

// CONTEXT:
//   - Project type: Standalone Timer (GAS or plain JS web app)  
//   - Desired structure:  
//       /docs/  
//         ARCHITECTURE.md  
//         READMETIMER.md  
//         FUNCTION_INDEX.md  
//         CALL_MAP.md  
//         LOGGING_STRATEGY.md  
//         CODING_CONVENTIONS.md  
//         CODEX_USAGE.md  
//         PromptLog.md  
//       /codex/  
//         AGENTS.md  
//         SCAFFOLD_TEMPLATES.md  
//         SelfEval/ (.gitkeep)  
//       Root:  
//         CHANGELOG.md (stub if missing)

// EXAMPLE:
//   After execution, `docs/ARCHITECTURE.md` should begin with:
//   ```markdown
//   # Architecture Overview
//   ```  
//   and `codex/AGENTS.md` should begin with:
//   ```markdown
//   # AGENTS.md (Standalone Timer Project)
//   ```

// INSTRUCTIONS:
//   1. In the repo root, ensure `CHANGELOG.md` exists. If not, create it with:
//        ```markdown
//        # Changelog
//        ## [Unreleased]
//        ```  
//   2. Create (or update) the `docs/` folder with empty files named:
//        - ARCHITECTURE.md (`# Architecture Overview` header)  
//        - READMETIMER.md (`# User Guide & UI Reference` header)  
//        - FUNCTION_INDEX.md (`# Function Index` header)  
//        - CALL_MAP.md (`# Call Map` header)  
//        - LOGGING_STRATEGY.md (`# Logging Strategy` header)  
//        - CODING_CONVENTIONS.md (`# Coding Conventions` header)  
//        - CODEX_USAGE.md (`# Codex Usage Guide` header)  
//        - PromptLog.md (`# Prompt Log` header)  
//   3. Create (or update) the `codex/` folder with:
//        - AGENTS.md (`# AGENTS.md (Standalone Timer Project)` header)  
//        - SCAFFOLD_TEMPLATES.md (`# Prompt Scaffold Templates` header)  
//        - `SelfEval/` directory containing an empty `.gitkeep`  
//   4. In each new file, insert only the top-level heading matching its purpose (no additional content).  
//   5. Append an entry to `docs/PromptLog.md` with today’s date and this full prompt text (from `// TASK:` through here).  
//   6. Add an entry to `CHANGELOG.md` under `## [Unreleased]`:
//        - “Scaffolded docs/ and codex/ directories with core files”  
//   7. Commit all changes to branch: `codex/feature-scaffold-docs-codex`.
//
// <<< [scaffoldDocsAndCodex]             ← zone marker end
