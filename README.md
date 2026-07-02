# Feynman Learning

> **"If you can't explain it simply, you don't understand it well enough."** — Richard Feynman

A Claude skill that turns the classic Feynman Technique into an AI-powered iterative learning loop. Learn any topic 10x faster through analogies, gap detection, and adaptive depth dialing.

## Quick Install

```bash
npx skills add carlos/feynman-learning
```

## What It Does

Instead of one-shot Q&A, this skill runs a **learning loop**:

1. Claude explains a concept with everyday analogies
2. You explain it back in your own words
3. Claude finds the gaps in your understanding
4. You choose where to go deeper — and the loop repeats

## Usage

```
/feynman [topic]            → Start learning (Rung 1)
/feynman [topic] --ladder   → Show a Learning Ladder first
/feynman [topic] --depth    → Full deep-dive with analogies
/feynman [topic] --quiz     → Test your understanding
/feynman [topic] --map      → Map what you know vs don't know
```

## Features

- **Learning Ladder** — 5-level progression from Novice to Expert
- **3-Question Diagnostic** — never talks over or under your level
- **Adaptive Depth Dial** — you choose what to dive into next
- **Feynman Gap Analysis** — identifies exactly what you missed
- **Analogies + Breakdowns** — every analogy comes with its limitations
- **Advanced Drills** — Blind Spot Drill, Rubber Duck Prompt, Chain Learning, 20-Minute Sprint

## Requirements

- Claude Code, Claude Desktop, Cursor, or any AI agent supporting SKILL.md

## License

MIT
