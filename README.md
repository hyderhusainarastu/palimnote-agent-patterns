# Palimnote Agent Patterns

Guides and patterns for multi-agent AI work: an orchestration playbook, subagent definition files, cross-session handoff prompts, review lifecycles and an always-loaded project memory file (AGENTS.md or CLAUDE.md). Tool-neutral: Claude Code, Codex, Cursor, Gemini, ChatGPT and local models.

## Start here

[multi-agent-orchestration-playbook](https://github.com/hyderhusainarastu/multi-agent-orchestration-playbook) is the umbrella. It is a short playbook of twelve rules (moderator only, tier by task, no self-approval, one owner per file, guard silent drops and more), an `AGENTS.md` template and small tested helper scripts for the rules code can enforce. The patterns below plug into it.

## Patterns

| Layer | Repository | What it is |
| --- | --- | --- |
| umbrella | [multi-agent-orchestration-playbook](https://github.com/hyderhusainarastu/multi-agent-orchestration-playbook) | Twelve rules for running teams of AI agents, an `AGENTS.md` template, and Python and Node helper scripts (shard coverage check, silent-drop guards). |
| per-role | [claude-subagent-definition-pattern](https://github.com/hyderhusainarastu/claude-subagent-definition-pattern) | Guide and worked examples for writing Claude Code `.claude/agents/*.md` subagent definitions: description-as-router, model-tier selection by work shape, the skill/agent content split, restating critical rules inline, and the follow-report-never-override rule for standing decisions. |
| per-role | [agent-brief-schema-for-specialist-roles](https://github.com/hyderhusainarastu/agent-brief-schema-for-specialist-roles) | A fixed briefing schema for task instructions to specialist agents: scope, exact inputs, permitted tools, prohibited actions, model routing, output contract and acceptance tests. |
| per-role | [adversarial-peer-review-role](https://github.com/hyderhusainarastu/adversarial-peer-review-role) | A reusable reviewer persona whose job is to find defects in a piece of work rather than confirm its author's hopes. |
| per-task | [cross-session-agent-handoff-prompt-template](https://github.com/hyderhusainarastu/cross-session-agent-handoff-prompt-template) | A fill-in template for the handoff prompt that transfers work between AI-agent sessions: provenance header, de-authorization directive, verbatim machine values with per-value source provenance, reverted-attempt disclosure, and an explicit integration gate. |
| per-project | [project-memory-file-scaffold](https://github.com/hyderhusainarastu/project-memory-file-scaffold) | A blank scaffold for the always-loaded memory file of a long-running project: a closed status-label taxonomy, numbered standing directives, supersede-in-place archival, named phases with gate verdicts, a known-problems section, and one always-current state block. |
| per-project | [evidence-ledger-and-phase-handoff-convention](https://github.com/hyderhusainarastu/evidence-ledger-and-phase-handoff-convention) | A documentation convention for workflows where agents, sessions or people build on each other's work: what the last phase actually checked, recorded for the next. |
| per-project | [governance-records-ledger-conventions](https://github.com/hyderhusainarastu/governance-records-ledger-conventions) | Append-only conventions for decision logs, task ledgers and open-question files in long-running or multi-agent projects. |
| per-review | [gated-multi-agent-review-lifecycle](https://github.com/hyderhusainarastu/gated-multi-agent-review-lifecycle) | A methodology where a later stage depends on an earlier stage's output only after independent verification: structured pass/fail verdicts, failure routing and escalation, no self-approval, an auditable evidence trail. |

## Tools and skills that support these patterns

These live in other catalogs. They enforce or extend the patterns above.

| Repository | What it does | Catalog |
| --- | --- | --- |
| [ai-coding-agent-guardrail-hooks](https://github.com/hyderhusainarastu/ai-coding-agent-guardrail-hooks) | Tool-neutral `guardrails check` CLI, a Claude Code hook adapter and git hooks that keep `.env` values and protected-directory symlinks out of commits. Advisory, not a sandbox. | [palimnote-tools](https://github.com/hyderhusainarastu/palimnote-tools) |
| [agent-report-evidence-gate](https://github.com/hyderhusainarastu/agent-report-evidence-gate) | Checks an agent's "done" report for evidence completeness: cited files exist, success claims sit next to evidence, structured claims re-verify against the repo. | [palimnote-tools](https://github.com/hyderhusainarastu/palimnote-tools) |
| [release-privacy-scanner](https://github.com/hyderhusainarastu/release-privacy-scanner) | `leakscan` scans a repository, its git history and release archives for local paths, personal identifiers, private hostnames and secret-shaped strings before a public push. | [palimnote-tools](https://github.com/hyderhusainarastu/palimnote-tools) |
| [safe-mcp-server-template](https://github.com/hyderhusainarastu/safe-mcp-server-template) | Python template for an MCP server that treats tool output as untrusted: closed tool list, nonce-fenced output, size caps, rate limits, propose-then-confirm for risky actions. | [palimnote-tools](https://github.com/hyderhusainarastu/palimnote-tools) |
| [local-first-llm-router](https://github.com/hyderhusainarastu/local-first-llm-router) | Policy layer that tries a script, then a local model, and escalates to a cloud model only when checks fail and the data's privacy tier allows it. | [palimnote-tools](https://github.com/hyderhusainarastu/palimnote-tools) |
| [ollama-memory-governor](https://github.com/hyderhusainarastu/ollama-memory-governor) | Keeps free RAM above a floor on a machine running several Ollama models: pins the primary model and unloads secondary ones by priority. | [palimnote-tools](https://github.com/hyderhusainarastu/palimnote-tools) |
| [hallucinated-citation-checker](https://github.com/hyderhusainarastu/hallucinated-citation-checker) | Checks every BibTeX entry against Crossref, OpenAlex, arXiv, Open Library and doi.org to catch fabricated references from AI drafting. | [palimnote-tools](https://github.com/hyderhusainarastu/palimnote-tools) |
| [scholarly-citation-resolver](https://github.com/hyderhusainarastu/scholarly-citation-resolver) | Resolves a free-text citation to verified metadata from six open scholarly sources and refuses a match that does not fit. | [palimnote-tools](https://github.com/hyderhusainarastu/palimnote-tools) |
| [deep-research-skill](https://github.com/hyderhusainarastu/deep-research-skill) | Agent skill for auditable research: a saturation stop rule, explicit verification levels and bounded negative findings. | [palimnote-skills](https://github.com/hyderhusainarastu/palimnote-skills) |
| [cross-model-second-opinion](https://github.com/hyderhusainarastu/cross-model-second-opinion) | Agent skill for a budgeted second opinion from a different AI model: when to ask, read-only CLI recipes, a call cap. | [palimnote-skills](https://github.com/hyderhusainarastu/palimnote-skills) |

## Works with

Status describes this catalog only: whether the index and its prompt were exercised on that surface. Each pattern repo has its own capability table.

| Surface | How | Status |
| --- | --- | --- |
| Claude Code | `CLAUDE.md` imports `AGENTS.md` | not tested |
| Codex | reads `AGENTS.md` | not tested |
| Cursor | reads `AGENTS.md` | not tested |
| Copilot | `.github/copilot-instructions.md` points to `AGENTS.md` | not tested |
| Gemini CLI | `GEMINI.md` imports `AGENTS.md` | not tested |
| ChatGPT / Claude.ai / Gemini (chat) | paste `PROMPT.md` | not tested |
| Local models | paste `PROMPT.md` | not tested |

## How to use

Each repo is self-contained. Clone the one you need, then drop its agent or template files into your project (for example `.claude/agents/`, or your tool's equivalent) or adapt the templates to your own roles, task shapes and memory conventions. In a chat window, paste `PROMPT.md` from this repo and answer its questions.

## Related

- [palimnote-skills](https://github.com/hyderhusainarastu/palimnote-skills): portable agent skills following the SKILL.md convention
- [palimnote-tools](https://github.com/hyderhusainarastu/palimnote-tools): runnable CLIs, libraries, hooks and MCP servers
- [palimnote-templates](https://github.com/hyderhusainarastu/palimnote-templates): fill-in document and config templates

## License

CC BY 4.0, canonical legal code in `LICENSE`. Each repo in this catalog carries its own LICENSE file.

Part of palimnote-agent-patterns - more at https://github.com/hyderhusainarastu
