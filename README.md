# Sakshi — the tooling family root

Sakshi (साक्षी, "the witness") is the coordination layer for the AI Factory tooling: the skills package that defines how agents plan and work, and the orchestrator that executes a finished roadmap task by task. This root holds no runnable code — it exists so that every session and every doc can reference the sub-repositories by one guaranteed layout.

## Setup

Paste the following prompt into Claude Code — it will clone the repositories into the correct layout automatically:

```
Clone the Sakshi tooling root and its sub-projects into the correct directory structure.

Run these commands in order:
1. git clone https://github.com/sakshi-systems/sakshi-public.git sakshi
2. cd sakshi
3. git clone https://github.com/sakshi-systems/skills-public.git skills
4. git clone https://github.com/sakshi-systems/orchestrator-public.git orchestrator

Directory structure must be preserved exactly — the docs reference the sibling repos by paths from this root, such as `orchestrator/...`, so the clone directories are named `sakshi`, `skills` and `orchestrator`, whatever the GitHub repositories are called.

After cloning, for each repository (root, skills, orchestrator) check out `main`.

Then raise each sub-repo's environment by following its own README — interactively, never silently: skills/README.md § "Setup — activating the package (one-time, per machine)" to activate the package for Claude Code, and orchestrator/README.md § Install to install its dependencies, then § Configure to create the local configuration.
```

## Sub-repositories

| Directory | GitHub | Stack | Purpose |
|-----------|--------|-------|---------|
| `skills/` | [skills-public](https://github.com/sakshi-systems/skills-public) | Markdown skill, command and agent packages | The skills that define how agents plan and work, and the global agent discipline |
| `orchestrator/` | [orchestrator-public](https://github.com/sakshi-systems/orchestrator-public) | Python | The command-line tool that executes a finished roadmap task by task: plan → plan review → implement → review → commit |

Each sub-repo's README is self-sufficient: check one out on its own and its README walks the agent through raising that environment.

## License

MIT — see [LICENSE](LICENSE).
