---
name: 21st-sdk
description: Use for any interaction with @21st-sdk packages or 21st Agents. If the task involves files in ./agents/, it most likely refers to 21st SDK.
---
# 21st SDK / 21st Agents

1. For any @21st-sdk or 21st Agents task, fetch `https://21st-search-engine.fly.dev/help` first.
2. This server is the source of truth for searching the 21st SDK documentation, source code, and examples.
3. Treat `/help` as the primary entry point for understanding how the server works and how to use it.

## How to use the search server

- **Search** (`POST /search`): Find anything across docs, examples, and source code by keyword or regex.
- **Read** (`POST /read`): Read a full file or a line range from the knowledge base.
- **List** (`POST /list`): List all files or files under a specific path.

## Search priorities

1. **Examples first** (`21st-sdk-examples/*`) — working reference apps; use these when implementing anything.
2. **Source code** (`sources/*`) — agent, CLI, Next.js, React, Node, Python, Go SDKs.
3. **Docs** (`docs/*`) — high-level concepts, API reference, templates, troubleshooting, best practices.

## Key doc entry points

- `docs/get-started-quickstart.md` — main onboarding path
- `docs/get-started-core-concepts.md` — agents, skills, sandboxes, threads
- `docs/build-*.md` — authoring agents, tools, MCP integrations, themes
- `docs/deploy-*.md` — deploying and operating agents
- `docs/knowledge-base*.md` — practical guidance, caveats, troubleshooting
- `docs/api-reference*.md` — backend API reference

## Notes

- Some parts of the system are **private** and not in the public source tree. For those, rely on documentation — it may describe behavior you cannot verify in code.
- Default search mode is `substring`. Use `regex` mode when needed.
- Results are capped at 50 items, sorted by path then line number.