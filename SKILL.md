---
name: feynman-learning
description: Apply the Feynman Technique with Claude to learn any topic 10x faster. Uses a Learning Ladder framework, analogy-driven simplification, and targeted feedback loops. Use when user wants to learn a new topic, understand a complex concept, prepare for an exam, master a skill, or says "learn faster", "Feynman technique", "explain simply", or "teach me [topic]".
license: MIT
compatibility: Claude Code, Claude Desktop, Cursor, any AI agent supporting SKILL.md
metadata:
  author: carlos
  version: "1.0"
  tags: learning education feynman technique study teaching
---

# Feynman Learning — Learn Anything 10x Faster Using Claude

Based on the article by Rahul (@sairahul1) — combining the classic Feynman Technique with an AI-powered iterative learning loop.

## Core Philosophy

**If you can't explain it simply, you don't understand it well enough.**

Learning is an adaptive loop, not a one-shot Q&A. Claude simplifies → you test your understanding → Claude finds your gaps → you go deeper → repeat.

## Quick Start

```
/feynman [topic]            → Start learning loop (Rung 1)
/feynman [topic] --ladder   → Show a Learning Ladder first
/feynman [topic] --depth    → Full deep-dive with analogies
/feynman [topic] --quiz     → Test your understanding
/feynman [topic] --map      → Map what you know vs don't know
```

## The Learning Loop (This Is the Core)

The entire skill is one loop. Every response from Claude should end by asking **"What's next?"** — the user either asks for more depth, or says "I've got it, move on."

```
┌─────────────────────────────────────────┐
│  1. Claude explains + analogies         │
│     (at your current level)             │
└─────────────┬───────────────────────────┘
              ▼
┌─────────────────────────────────────────┐
│  2. You explain it back                 │
│     ("Here's what I understood...")     │
└─────────────┬───────────────────────────┘
              ▼
┌─────────────────────────────────────────┐
│  3. Claude identifies your gaps         │
│     ("You got X right, Y is off...")    │
└─────────────┬───────────────────────────┘
              ▼
┌─────────────────────────────────────────┐
│  4. Choose your next move:              │
│     → "Go deeper on [gap]"              │
│     → "Connect to [related concept]"    │
│     → "Give me edge cases"              │
│     → "I'm satisfied, next rung"        │
└─────────────┬───────────────────────────┘
              ▼
       (back to step 1, level up)
```

## The 3-Question Diagnostic

When the user says a topic is "too simple" or "not what I meant", don't guess — ask:

1. **"What's your current level?"** — Novice / Beginner / Competent / Proficient / Expert
2. **"What specifically do you want to understand?"** — The concept itself / How to build with it / Edge cases / How it relates to X
3. **"What's missing from my explanation?"** — Detail / Depth / Practicality / Connections

This respects the user's time and avoids talking down or over their head.

## The Learning Ladder Framework

Before diving deep, build a Learning Ladder — a structured roadmap.

**Prompt Template:**
```
I want to learn [topic]. I know [current level].
Build a Learning Ladder with steps from my current level to advanced.
For each rung: what I should know, what I should be able to do, and what next concept unlocks.
```

### Ladder Rungs

| Rung | Level | What you can do |
|------|-------|----------------|
| 1 | Novice | Use the concept with a guide |
| 2 | Beginner | Explain the basics to someone |
| 3 | Competent | Apply it without help |
| 4 | Proficient | Teach it to others |
| 5 | Expert | Identify edge cases and trade-offs |

## The 3-Step Learning Loop

### Step 1: Learn & Simplify

```
Explain [concept] like I'm 12. Use 2 analogies from everyday life.
After each analogy, explicitly highlight where the analogy breaks down.
Then give me the formal definition in one sentence.
Then ask me: "What part was unclear? Should I go deeper or move on?"
```

### Step 2: Identify Gaps (The Feynman Gap)

```
Here's my explanation of [concept]: [your explanation].
1. What did I get right?
2. What did I get wrong or oversimplify?
3. What did I miss entirely?
4. Give me 3 edge cases or counterexamples that would test my understanding.
5. Ask me: "Which gap should we fix first?"
```

### Step 3: Deepen & Connect

```
Connect [concept] to [related concept] using an analogy.
Explain how a change in one would affect the other.
Then show me a real-world scenario where both concepts interact.
End by asking: "Now you try — explain the connection back to me."
```

## Advanced Techniques

### 1. The 20-Minute Sprint

```
- Minutes 0-5: Big picture + Learning Ladder
- Minutes 5-10: Deep dive on first rung with analogies
- Minutes 10-15: You explain back, find gaps
- Minutes 15-20: Fill gaps, connect to next rung
```

### 2. Chain Learning

Build sequential understanding by chaining concepts. Each concept's "what unlocks next" becomes the next learning target. Always end by asking: "Ready for the next chain link?"

### 3. The Blind Spot Drill

```
What are the 5 most common misconceptions about [topic]?
For each: why it's wrong, what's actually true.
After each one, ask: "Did any of these surprise you? Want me to elaborate on one?"
```

### 4. The Rubber Duck Prompt

```
Pretend you're a curious 10-year-old. Ask me 5 questions about [concept]
that test whether I truly understand it. Then evaluate my answers.
After each answer: "You got [part] right, but [part] needs work. Try again?"
```

## Claude-Specific Interaction Pattern

### The Adaptive Depth Dial

```
User: /feynman MCP
Claude: Let me start. MCP is a protocol that... [1 paragraph].
        Does this make sense? Do you want:
        (a) Deeper explanation of the protocol itself
        (b) How to build an MCP server
        (c) How it compares to alternatives
        (d) Real examples from your setup

User: [chooses c]
Claude: [Compares MCP to Function Calling, LangChain tools, etc.]
        Any part of this comparison you want me to elaborate?
```

### The "Not Yet" Handler

When the user says "I don't get it" or "still not clicking":

```
1. "Let me try a different analogy entirely."
2. "Which word/sentence lost you? Point to the exact spot."
3. "Let me break it into smaller pieces. Here's just part 1..."
4. "Can you tell me what you DO understand about this topic? I'll build from there."
```

## Complete Learning Session Example

```
User: /feynman MCP
Claude: [1-paragraph summary → asks for depth direction]
User: That's too simple.
Claude: [3-Question Diagnostic]
        "What's your current level? What specifically do you want to understand?"
User: I've heard of MCP, know it's a protocol, but don't know why it exists.
Claude: [Explains pre-MCP world — Function Calling fragmentation]
        [Analogy: Unicode before i18n standardization]
        [Analogy: USB-C for AI tools]
        [Asks: "Which part should I go deeper on?"]
User: Go deeper on how it actually works.
Claude: [Explains JSON-RPC, Client/Server lifecycle]
        [Asks: "You try — explain it back to me."]
User: [Explains] MCP is like a waiter taking orders...
Claude: [Finds gaps: user missed capability negotiation]
        [Fills gap: "Let me explain what capability negotiation is..."]
        [Asks: "Ready to go deeper, or move to next rung?"]
```

## See Also

For code-level understanding of systems, use the `tdd` or `diagnose` skills for hands-on learning-by-building.
