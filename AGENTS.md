# palimnote-agent-patterns

A catalog of guides and conventions for multi-agent AI work. It holds an index (README.md), not code.

## Using this in your project

- Start at README.md. Open `multi-agent-orchestration-playbook` first: it is the umbrella; the other patterns plug into it.
- Pick the pattern that matches the layer you need (per-role, per-task, per-project, per-review) and clone that repo, not this one.
- Link to a pattern repo by its URL. Do not copy its files into this catalog.
- Never present a "not tested" row in the compatibility table as verified.
- Paste PROMPT.md into a chat assistant to get help choosing a pattern and adapting it to your project.

## Working on this repo

- Setup: none. Plain Markdown.
- Check: `grep -n "github.com/hyderhusainarastu" README.md` and confirm each linked repo exists before editing a link.
- Do not edit LICENSE (canonical CC BY 4.0 legal code).
- Add a new pattern as one row in the matching README table, with a one-line description taken from that repo's own README.
