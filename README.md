# Alfred — AI Concierge Bot

> Multi-platform AI concierge for a Parisian bistronomique restaurant, running on a locally-hosted LLM.

[![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![Ollama](https://img.shields.io/badge/Ollama-Llama%203.2-black?style=flat)](https://ollama.com/)
[![Telegram](https://img.shields.io/badge/Telegram-bot-26A5E4?style=flat&logo=telegram&logoColor=white)](https://t.me/alfred_maisonnoir_bot)
[![Discord](https://img.shields.io/badge/Discord-bot-5865F2?style=flat&logo=discord&logoColor=white)](https://discord.gg/wXxMjcCKtr)

## What it is

Alfred is the virtual concierge of **Maison Noir**, a Parisian bistro. He answers customer questions 24/7 across Telegram and Discord — menu, opening hours, allergens, current promotions, chef's recommendations. The brain is **Llama 3.2 running locally via Ollama**, so no cloud cost, no data leaving the premises, full ownership.

## Stack

| Layer        | Technology                                              |
| ------------ | ------------------------------------------------------- |
| **LLM**      | Llama 3.2 via [Ollama](https://ollama.com) — 100% local |
| **Telegram** | `python-telegram-bot` 22.7 (async)                      |
| **Discord**  | `discord.py` 2.7.1                                      |
| **Data**     | JSON + CSV (menu of 33 items, FAQ, promos)              |
| **Config**   | `python-dotenv`                                         |

## Features

- Answers questions about menu, hours, address, promotions
- **Allergen lookup** per dish, from real menu data
- **Personalized dish recommendations** based on customer preferences
- Redirects to phone for reservations
- **Per-user conversation memory** (6 messages, volatile)
- 7 commands: `/start`, `/carte`, `/formules`, `/offres`, `/infos`, `/aide`, `/reset`

## Architecture

```
├── llm.py             # Alfred's brain — LLM, context, history
├── restaurant.json    # Restaurant info (hours, address, chef)
├── data/
│   ├── menu.csv       # Full menu (33 items, allergens, prices)
│   ├── faq.csv        # 18 FAQ entries
│   └── promos.csv     # Active promotions
├── telegram/          # Async Telegram bot
├── discord/           # Discord bot (DM-only)
└── documentation/     # Strategy report + technical doc
```

## What I learned

- **Local LLM integration** — running Llama 3.2 via Ollama, prompt engineering for a constrained domain (restaurant FAQ vs. general chat)
- **Multi-platform bot design** — handling async patterns in `python-telegram-bot` while keeping the Discord version clean
- **Context windowing** — implementing per-user volatile memory without a database
- **Business framing** — wrote a full strategic report (marketing KPIs, ROI, ethics analysis) alongside the technical doc

## Project context

- **Year** : 2025–2026
- **School** : Epitech Bachelor, Mulhouse
- **Team** : 2 members
- **Course** : AI / Algorithm (B-AIA-210)

## Note

This is a portfolio summary. The full source code is private per Epitech academic policy. Available on request for recruiters.

---

[Imran Nogueira](https://github.com/imrannnn30) · MMXXVI
