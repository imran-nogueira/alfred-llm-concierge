# Alfred — Local-LLM Concierge Bot

> A restaurant concierge that answers customers on Telegram and Discord, powered by an LLM running 100% locally and grounded on the restaurant's real data.

**Epitech Bachelor · Year 1 · AI module (B-AIA-210) · Apr 2026**
Source code is private under Epitech's academic policy. Happy to walk you through it or demo it live → **imran.nogueira@gmail.com**

## Overview

Alfred is the virtual concierge of *Maison Noir*, a fictional Parisian bistro. He answers customer questions around the clock — menu, opening hours, allergens, set menus, current promotions, dish recommendations — and redirects reservations to the phone. The model runs locally through Ollama: no API cost and no customer data leaving the machine.

## Stack

| Layer | Tech |
|---|---|
| LLM | Llama 3.2 via Ollama, running locally |
| Bots | `python-telegram-bot` 22.7 (async), `discord.py` 2.7.1 |
| Data | JSON + CSV — 33 menu items with allergens and prices, 18 FAQ entries, promotions |
| Language | Python, `python-dotenv` |

## How it works

```
Telegram / Discord ──▶ bot handlers ──▶ llm.py ──▶ Ollama (Llama 3.2, local)
                                          ▲
                        restaurant.json + menu / FAQ / promos CSV
```

Every request is answered from the restaurant data injected into the prompt, plus the last 6 messages of that user's conversation. Commands give direct access to the menu, set menus, offers and practical info, and `/reset` clears the memory.

## Key decisions

- **Local model over a cloud API** — zero running cost and full data ownership, at the price of a smaller model that needs a tighter prompt.
- **Grounded on real data** — the real menu, allergens and FAQ go into the context, so an allergen answer comes from the data, not from the model's imagination.
- **Volatile, bounded memory** — 6 messages per user, in memory: enough for follow-up questions, nothing stored about customers.

## Contact

Code walkthrough or live demo on request → **imran.nogueira@gmail.com** · [Portfolio](https://imran-nogueira.github.io)
