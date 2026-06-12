# agent-toolbox

This repo contains a set of files intended for use with LLMs.

The information here is _heavily_ opinionated and is not intended to be applied to all projects; this is not a "make your LLM write code correctly" toolbox but rather a "make your LLM write code that follows my personal conventions."

## Codex Plugin

This repo is also a Codex plugin marketplace. The marketplace lives at `.agents/plugins/marketplace.json` and exposes the `agent-toolbox` plugin from `plugins/agent-toolbox`.

Install it with:

```bash
codex plugin marketplace add JosephDuffy/agent-toolbox
codex plugin add agent-toolbox@agent-toolbox
```

After installing or updating the plugin, start a new Codex thread so the bundled skills are picked up.
