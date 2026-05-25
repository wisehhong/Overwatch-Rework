---
applyTo: "**/*.ow"
---

Use these rules when editing Overwatch Workshop script files.

1. Respect script structure
- Keep top-level structure valid for Workshop export/import.
- Preserve block structure and braces exactly.
- Keep indentation consistent with the file style.

2. Protect gameplay logic
- Do not silently change event scope, hero filter, or team filter.
- Keep existing status checks and lock checks unless intentionally redesigned.
- If changing movement or impulse logic, call out expected gameplay effects.

3. Variable discipline
- Reuse existing player variables when possible.
- If adding a variable, ensure it is declared in `variables.ow` and used consistently.
- Avoid temporary variables that can collide with existing meanings.

4. Timing and loops
- Be explicit with `Wait(...)` durations and condition behavior.
- Ensure every `Loop If(...)` remains bounded by a clear state transition.
- Avoid excessive per-tick work in ongoing rules when a narrower event can be used.

5. Balance and tuning
- Keep numeric tuning values easy to locate and adjust.
- When tuning damage, cooldown flow, or movement force, include a brief note about tradeoffs.
- Prefer incremental changes over full rewrites.

6. Suggested references
- Tutorials index: https://workshop.codes/wiki/categories/tutorials
- Useful topics: status detection, loops, vectors, and server stability.
