# Trading Second Brain

A multimodal, agent-friendly trading knowledge base for turning screenshots, PDFs, PPTs, handwritten notes, trade logs, and daily journals into reusable trading memory.

## What this repo is

This public-template-style repository is designed to be forked and customized. Keep the structure and prompts here, but store private account data, broker statements, API keys, raw PnL, and sensitive trade history in a private clone or private companion repository.

The core idea is simple:

> Every trade should make the next trade smarter.

## Core loop

```text
Screenshots / PDFs / PPT / Handwriting / CSV / Notes
                       ↓
                     inbox/
                       ↓
                AI recognition
                       ↓
         classify / extract / cross-check
                       ↓
   knowledge/  strategies/  journal/  trades/
          \          |          /
               LEARNINGS.md
                    ↓
               decisions.md
                    ↓
                 MEMORY.md
                    ↓
                 AI Agent
                    ↓
              Next trading day
```

## Repository map

```text
trading-second-brain/
├── CLAUDE.md
├── MEMORY.md
├── LEARNINGS.md
├── decisions.md
├── knowledge/
├── strategies/
├── journal/
├── trades/
├── screenshots/
├── research/
├── inbox/
├── templates/
└── prompts/
```

## Quick start

1. Fork or clone this repository.
2. Fill in `MEMORY.md` with your stable trader profile and recurring weaknesses.
3. Put raw material into `inbox/`.
4. Ask your multimodal AI agent to process the inbox using `prompts/inbox-triage.md`.
5. Use `templates/daily-journal.md` for each trading day.
6. Run `prompts/daily-review.md` after the close and `prompts/weekly-review.md` each weekend.
7. Promote repeated observations into `LEARNINGS.md`; only promote robust, durable facts into `MEMORY.md`.

## Multimodal workflow

Modern multimodal models can inspect more than Markdown. Feed them:

- TradingView or broker screenshots
- GEX / dealer positioning charts
- PDF research
- PPT decks
- handwritten notes photographed by phone
- CSV trade exports
- chart annotations

Keep the original source file whenever possible. AI extraction is a derivative, not a replacement for the source.

## One topic = one file

Prefer one independently understandable, independently maintainable knowledge unit per file. Do not mechanically split a topic into tiny fragments. If `put-wall.md` can hold the definition, behavior, failure modes, and examples coherently, keep it together until it becomes too large.

## Privacy

Never commit credentials, account numbers, broker statements, personally identifying information, or private trading data to a public repo. See `.gitignore`.

## Disclaimer

This repository is a knowledge-management framework, not financial advice or an automated trading recommendation system.
