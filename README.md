# Palimnote Agent Patterns

Patterns for the persistent layer of agent-assisted work: how to write Claude Code subagent definitions (per-role), how to hand work between sessions (per-task), and how to keep an always-loaded project memory file honest (per-project).

| Layer | Repository | Description |
| --- | --- | --- |
| per-role | [claude-subagent-definition-pattern](https://github.com/hyderhusainarastu/claude-subagent-definition-pattern) | Educational guide and worked examples for writing Claude Code `.claude/agents/*.md` subagent definition files: description-as-router, model-tier selection by work shape, the skill/agent content split, restating critical rules inline, and the follow-report-never-override rule for standing decisions. |
| per-task | [cross-session-agent-handoff-prompt-template](https://github.com/hyderhusainarastu/cross-session-agent-handoff-prompt-template) | A fill-in template for the handoff prompt that transfers work between AI-agent sessions: provenance header, de-authorization directive, verbatim machine values with per-value source provenance, reverted-attempt disclosure, and an explicit integration gate. |
| per-project | [project-memory-file-scaffold](https://github.com/hyderhusainarastu/project-memory-file-scaffold) | A blank, fill-in scaffold for the always-loaded memory file of a long-running project, encoding six mechanisms: a closed status-label taxonomy, numbered standing directives, supersede-in-place archival, named phases with gate verdicts, a known-problems section, and one always-current state block. |

**Related:** for the agent roles that consume these patterns, see [agent-brief-schema-for-specialist-roles](https://github.com/hyderhusainarastu/agent-brief-schema-for-specialist-roles) and [adversarial-peer-review-role](https://github.com/hyderhusainarastu/adversarial-peer-review-role) in the [Palimnote Skills](https://github.com/hyderhusainarastu/palimnote-skills) catalog.

## How to use

Each repo is self-contained. Clone it, then either drop its agent/template files directly into `.claude/agents/` (or your runtime's equivalent) or adapt the templates to your own project's roles, task shapes, and memory conventions.

## Related catalogs

| Catalog | Description |
| --- | --- |
| [palimnote-skills](https://github.com/hyderhusainarastu/palimnote-skills) | Portable agent skills following the SKILL.md convention |
| [palimnote-tools](https://github.com/hyderhusainarastu/palimnote-tools) | Standalone scripts and utilities |
| [palimnote-templates](https://github.com/hyderhusainarastu/palimnote-templates) | Fill-in document and config templates |

## License

CC BY 4.0. Each repo in this catalog carries its own LICENSE file.
