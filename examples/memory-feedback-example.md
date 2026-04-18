---
name: Delegate routine work to cheaper subagents
description: When a task decomposes into independent units, dispatch them to a smaller/cheaper model running in parallel; keep the larger model focused on coordination and synthesis
type: feedback
---

When a user request decomposes into two or more independent units of work, dispatch the routine ones to a smaller/cheaper model running in parallel. The larger coordinator model keeps its context window free for synthesis, cross-cutting decisions, and conversation with the user.

**Why:** A strong coordinator model is valuable for reasoning, reviewing, and reconciling. Routine file edits, repo scaffolds, single-function renders, and deterministic transforms do not exercise those strengths — they just burn the coordinator's context. Parallel subagents finish faster and cost less, and the coordinator's remaining context stays available for the parts of the task that actually need judgment.

**How to apply:**

1. Decomposition check: can the task be split into two or more units that do not share state and do not depend on each other's intermediate output? If yes, dispatch in parallel.
2. Keep the coordinator for: planning, reviewing subagent outputs, reconciling conflicts, user conversation, multi-file architectural changes, PhD-level academic writing.
3. Send to subagents: single-file edits, template rendering, repository scaffolding, PDF/DOCX export, routine refactors, script generation, test runs, data cleaning passes.
4. Self-contained prompts: subagents do not inherit conversation context. Each dispatch must specify exactly what to read, where to write, what format, and how to report back.
5. Stateful work stays in the coordinator: browser sessions, chat threads, interactive prompts, anything that depends on prior tool state.
6. Exception — high-stakes prose: peer-reviewed manuscripts, rebuttals, grant applications stay with the coordinator even if they look routine.

## Format notes

Each feedback memory follows this shape:

- **Frontmatter**: `name`, `description` (one-line hook for the index), `type: feedback`.
- **Body opens with the rule** — one or two sentences a future reader can act on without context.
- **Why:** the reason the rule exists. Usually a past incident, a measured cost, or an explicit preference. This is what lets the reader decide whether an edge case counts.
- **How to apply:** when and where the rule kicks in. Scope the rule so it does not accidentally govern unrelated situations.

The corresponding `MEMORY.md` entry is exactly one line:

```markdown
- [Delegate routine work to cheaper subagents](memory-feedback-example.md) — parallel Sonnet for routine units; coordinator keeps coordination + high-stakes prose.
```

One line per memory keeps the index scannable at load time. Detail lives in the individual file.
