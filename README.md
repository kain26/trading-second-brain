<div align="center">

# 🧠 Trading Second Brain

### Turn every chart, trade, mistake, PDF, slide, and handwritten note into reusable trading memory.

A multimodal, agent-friendly knowledge system for traders.

**English** · [简体中文](./README.zh-CN.md) · [日本語](./README.ja.md) · [한국어](./README.ko.md)

![Multimodal](https://img.shields.io/badge/Multimodal-Images%20%7C%20PDF%20%7C%20PPT%20%7C%20CSV-111111)
![Agent Ready](https://img.shields.io/badge/Agent--Ready-Claude%20%7C%20Codex%20%7C%20GPT-111111)
![Forkable](https://img.shields.io/badge/Forkable-Template-111111)

**Fork it. Feed it your trading history. Let your past trades participate in your next decision.**

</div>

---

## Why this exists

Most traders already have a second brain — it is just broken into pieces.

TradingView screenshots live in Photos. Broker fills live in CSV files. Research is trapped inside PDFs. Notes sit in Notion, Telegram, X bookmarks, PowerPoint decks, and handwritten notebooks. Daily reviews are written once and almost never retrieved again.

Then the next trading day begins, and the trader effectively starts from zero.

**Trading Second Brain turns those scattered artifacts into a structured memory layer that an AI agent can actually search, compare, update, and reason over.**

> The goal is not to save more information.  
> The goal is to make old information useful at the exact moment you need it.

---

## What makes it different

| Traditional journal | Trading Second Brain |
|---|---|
| Records what happened | Connects what happened to future decisions |
| Mostly text | Text + screenshots + charts + PDF + PPT + handwriting + CSV |
| One-day review | Cross-day pattern detection |
| Notes get duplicated | Existing topic files are updated |
| Rules are easy to forget | Rule changes have a dated decision log |
| AI sees today's prompt | AI can retrieve your trading history |

---

## The core loop

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

Every trade should make the next trade smarter.

---

## Multimodal by design

Modern AI models can work with much more than Markdown. This repository is designed around that fact.

Drop in:

- 📈 TradingView / broker screenshots
- 🧱 GEX, dealer positioning, option-wall charts
- 📄 PDF research papers and reports
- 🖥️ PowerPoint / slide decks
- ✍️ handwritten trading notes photographed by phone
- 📊 CSV trade exports
- 📝 daily journals and strategy notes

The agent should extract **facts first**, then interpretation, preserve the original source, and route the useful information into the correct long-term file.

---

## Repository structure

```text
trading-second-brain/
│
├── CLAUDE.md              # Agent operating instructions
├── MEMORY.md              # Durable trader context + hard rules
├── LEARNINGS.md           # Repeated lessons supported by evidence
├── decisions.md           # Why a rule/process changed
│
├── knowledge/             # One market topic per maintainable file
├── strategies/            # Executable trading playbooks
├── journal/               # Daily market context + reviews
├── trades/                # Structured trade records / CSV
├── screenshots/           # Chart and execution evidence
├── research/              # Original PDF / PPT / reports
├── inbox/                 # Unprocessed multimodal material
│
├── templates/             # Copy-paste templates
└── prompts/               # Ready-to-use AI workflows
```

---

## 5-minute quick start

### 1. Fork this repository

Use this repo as the operating system, then customize it for your own trading process.

### 2. Fill in `MEMORY.md`

Add only durable information:

```md
Primary market: SPX / ES
Trading style: Intraday / 0DTE
Maximum daily loss: ...
Maximum trades per day: ...
Known weakness: revenge trading
Known weakness: moving stops
```

Do **not** dump every daily observation into memory.

### 3. Put raw material into `inbox/`

```text
inbox/
├── gex-screenshot.png
├── trade-entry.png
├── handwritten-note.jpg
├── cboe-0dte-study.pdf
├── options-positioning.pptx
└── trades.csv
```

### 4. Run the inbox triage prompt

Use:

```text
prompts/inbox-triage.md
```

The agent will:

```text
Recognize → Extract → Classify → Search existing knowledge
                               ↓
                    Update or create topic
                               ↓
                       Preserve source
```

### 5. Review after the close

Use:

```text
prompts/daily-review.md
```

At the end of the week:

```text
prompts/weekly-review.md
```

---

## One topic = one maintainable file

Avoid this:

```text
notes.md
important-notes.md
new-strategy-final.md
new-strategy-final-v2.md
```

Prefer this:

```text
knowledge/
├── dealer-gamma.md
├── gamma-flip.md
├── put-wall.md
├── call-wall.md
├── vwap.md
└── 0dte-gamma.md
```

The rule is **not** “make every idea a tiny file.”

The better rule is:

> One independently understandable, independently maintainable knowledge unit = one file.

If `put-wall.md` can coherently hold the definition, expected behavior, failure modes, and historical examples, keep it together.

---

## Memory hierarchy

Not every observation deserves to become a rule.

```text
raw source
   ↓
journal / knowledge
   ↓
repeated evidence
   ↓
LEARNINGS.md
   ↓
explicit decision
   ↓
decisions.md
   ↓
durable context / hard rule
   ↓
MEMORY.md
```

This prevents one emotional trade from becoming a permanent system rule.

---

## The four files that matter most

### `CLAUDE.md`

The map for your AI agent.

It tells the agent where information lives, what to read first, how to process screenshots and documents, when to update existing notes, and what it must never invent.

### `MEMORY.md`

Stable trader context.

Think: markets, style, hard risk limits, recurring behavioral weaknesses, and durable rules.

### `LEARNINGS.md`

Lessons supported by repeated evidence but still open to revision.

Example:

```text
Observation:
After two profitable trades, setup quality often declines.

Evidence:
2026-08-11, 2026-08-18, 2026-08-21

Status:
Repeated pattern — keep monitoring.
```

### `decisions.md`

The audit trail traders usually do not have.

```text
Decision:
Exit 0DTE short-premium positions earlier.

Reason:
Repeated late-session gamma expansion erased open profit.

Evidence:
journal/...
trades/...

Status:
ACTIVE
```

Six months later, you do not just remember the rule — you remember **why the rule exists**.

---

## Ready-to-use AI workflows

The `prompts/` folder currently includes:

| Prompt | What it does |
|---|---|
| `inbox-triage.md` | Routes mixed multimodal material into the right place |
| `screenshot-analysis.md` | Extracts visible facts before chart interpretation |
| `research-extraction.md` | Turns PDF/PPT research into sourced knowledge |
| `handwritten-notes.md` | Transcribes and classifies handwritten notes |
| `daily-review.md` | Separates market outcome from execution quality |
| `weekly-review.md` | Detects repeated patterns and strategy-level performance |

---

## Example questions your agent should eventually answer

Once your repository contains enough history, ask questions like:

- Which time of day produces most of my losses?
- What happens to my next trade after two consecutive wins?
- Which setups work best in positive vs negative gamma?
- Show every time I violated the same stop-loss rule.
- Compare my losing screenshots and find repeated price-action patterns.
- Which strategy has the best expectancy after transaction costs?
- When did I first create this rule, and what loss caused it?
- Which lessons are supported by evidence, and which are still stories?

That is the point of the system.

---

## Public repo vs private brain

A useful pattern is:

```text
Public repo  = operating system / templates / prompts
Private repo = your actual brain
```

Keep these private:

- broker statements
- account numbers
- API keys
- private PnL
- sensitive trade exports
- personally identifying information

The included `.gitignore` provides a starting point, but **you are responsible for checking what you commit**.

---

## Suggested workflow

```text
Before market  → read MEMORY + relevant strategy
During market  → capture screenshots + trade evidence
After market   → daily journal + daily review
Weekend        → weekly review + update learnings
When rules move → append a dated decision
Anytime        → drop new research into inbox
```

Keep the system boring enough that you actually use it.

---

## Roadmap

- [ ] Example SPX / 0DTE knowledge files
- [ ] Example daily journal with screenshots
- [ ] Example trade CSV + analysis workflow
- [ ] Automated inbox routing
- [ ] Local semantic search / embeddings
- [ ] Broker-export adapters
- [ ] More agent instruction files
- [ ] Community-contributed templates

---

## Contributing

Ideas, templates, prompts, and workflow improvements are welcome.

Good contributions are practical: something another trader can fork, copy, and use immediately.

---

## Disclaimer

This project is a trading knowledge-management framework. It is not financial advice, investment advice, or an automated trading recommendation system. Markets involve substantial risk.

---

<div align="center">

**Your screenshots are data. Your mistakes are data. Your rules are data.**

**Make them searchable. Make them reusable.**

</div>
