# AI-Managed Trading Second Brain

This repository is designed to be managed by an AI file/coding agent, not manually organized by the trader.

Compatible examples include OpenAI Codex, Claude Code, Gemini CLI/agents, Kimi, Grok-based agents/bots, and other multimodal agents that can read and write files in a workspace. Capabilities differ; the requirement is access to this repository plus support for the source formats being processed.

## Human job

1. Give the agent access to this repository/workspace, not your whole computer.
2. Drop raw trading material into `inbox/`.
3. Ask the agent to process the inbox.
4. Trade, capture evidence, repeat.

**Do not manually classify every file.** The folder structure is primarily for the agent's long-term organization.

## Recommended permission boundary

Give read/write permission to the repository root only. Avoid unnecessary access to broker credentials, password stores, home directories, or unrelated projects.

## Autonomous pipeline

```text
Human → inbox/ → AI scans → understands content → searches existing brain
                                           ↓
                               update topic OR create topic
                                           ↓
                                  archive original source
                                           ↓
                           link journal ↔ trade ↔ screenshot
                                           ↓
                           detect patterns → daily review
```

## Content-aware classification

Never classify only by extension. A PNG can be a chart, GEX dashboard, broker fill, X research screenshot, or handwritten note.

For every inbox item determine source type, content type, instrument, date/time, timeframe, topics, strategy relationship, related existing knowledge, and archive destination when available.

## File-system rules

1. Inspect every unprocessed item.
2. Identify content before destination.
3. Preserve the original source.
4. Archive originals into appropriate long-term folders.
5. Search existing knowledge before creating Markdown.
6. Prefer updating existing topics.
7. Use lowercase hyphenated filenames for new topics.
8. Link derived notes to sources.
9. Never delete original evidence unless explicitly requested.
10. Never move files outside the repository.
11. Never expose secrets/private account information.
12. Never silently change hard risk rules.
13. Never promote one observation directly into durable memory.
14. Preserve contradictory evidence.
15. Produce a processing report after each run.

## Multimodal contract

```text
SOURCE FACTS → TRANSCRIPTION/EXTRACTION → INTERPRETATION
      → CROSS-CHECK EXISTING KNOWLEDGE → ARCHIVE + LINK
```

Mark uncertainty explicitly.

## Knowledge promotion

```text
Raw source → Journal/Knowledge → Repeated evidence → LEARNINGS.md
→ explicit rule decision → decisions.md → durable rule/context → MEMORY.md
```

## Universal command

> Process everything in inbox. Organize the original files, update existing knowledge, link today's trades and screenshots, identify repeated mistakes, and give me a daily review. Follow AGENT_WORKFLOW.md and CLAUDE.md.

## Agent portability

The architecture is vendor-neutral. If an agent does not automatically read `CLAUDE.md`, tell it to read `AGENT_WORKFLOW.md`, `CLAUDE.md`, and `MEMORY.md` before processing.

Automatic organization is encouraged. Automatic trading is not the purpose of this repository.