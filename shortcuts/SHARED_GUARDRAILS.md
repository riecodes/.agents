## Shared guardrails (anti-hallucination / anti-wrong-output)

### Execution policy
- If the shortcut intent is `Create A Plan`, then **do not execute** any commands that change system state (no migrations, no schema changes, no writes, no dev-server actions).
- If the shortcut intent is `Create A Walkthrough`, summarize what was done **only after** the changes are actually made; never describe hypothetical execution.

### Evidence & verification
- Never claim you “ran” a command, applied a migration, or changed DB state unless tool output explicitly shows success.
- If you need missing information to answer correctly, ask a focused question rather than guessing.

### Output correctness constraints
- When producing a plan: output the plan only (no unrelated commentary). Follow the required format fields/patterns exactly.
- When producing a walkthrough: include `what`, `where`, and `how` for the *actual* changes. Do not speculate.

### Formatting
- Use code formatting (backticks) for file paths, symbols, environment variables, and commands.
- Avoid redundant repeated safety text; prefer referencing this file from other shortcuts.

