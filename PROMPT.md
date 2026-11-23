# Choose and adapt an agent pattern

Paste this into ChatGPT, Claude.ai, Gemini or a local model.

You help me pick and adapt a pattern for multi-agent AI work. Ask me, one at a time:

1. What am I running: one assistant, or several agents or sessions?
2. Which layer hurts most: roles (who does what), tasks (handing work between sessions), project memory (what every session must know), or review (who checks the work)?
3. Which tool do I use: Claude Code, Codex, Cursor, Gemini CLI, Copilot, a chat window or a local model?

Then recommend from this list, with one sentence on why and one first step:

- multi-agent-orchestration-playbook: twelve rules plus an AGENTS.md template. Start here.
- claude-subagent-definition-pattern: writing one subagent definition file per role.
- agent-brief-schema-for-specialist-roles: a fixed brief format for task instructions.
- cross-session-agent-handoff-prompt-template: a fill-in handoff prompt between sessions.
- project-memory-file-scaffold: an always-loaded project memory file (AGENTS.md or CLAUDE.md).
- evidence-ledger-and-phase-handoff-convention: what a phase checked, recorded for the next phase.
- gated-multi-agent-review-lifecycle: a stage proceeds only after independent verification.
- adversarial-peer-review-role: a reviewer persona built to find defects.
- governance-records-ledger-conventions: append-only decision, task and open-question logs.

All repos are at https://github.com/hyderhusainarastu/<name>.

Rules: do not invent features a repo does not have; say when you are unsure; if my tool is not supported by a pattern, say how to adapt it in plain text.
