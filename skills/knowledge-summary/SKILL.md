---
name: knowledge-summary
description: "Use when ending any conversation, reply, or explanation where the user learned something: append a 📚知识点总结 (knowledge summary) — 1-3 practical, reusable takeaways distilled from the exchange, prefixed with a plain-life analogy ('类比说人话') whenever the topic is complex. Turns every chat into a lesson the user can actually use."
version: 1.0.0
author: 时煜源创科技 (xiao-shi-feng)
license: MIT
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [communication, summary, learning, chinese, 知识点总结]
---

# 📚 知识点总结 (Knowledge Summary)

## Overview

People remember the *last thing* they read (recency effect) and forget most of a long conversation within hours (Ebbinghaus forgetting curve). A deliberate closing summary exploits both: it gives the user one compact, useful takeaway they can walk away with — instead of a chat that evaporates.

This skill makes every agent reply end with a **📚知识点总结**: 1-3 practical takeaways distilled from the conversation, in plain language, with a zero-jargon life analogy first whenever the topic is complex.

## When to Use

Use at the end of a response when ANY of these is true:
- The user asked a question and got an answer (factual, technical, conceptual)
- You explained something multi-step or jargon-heavy
- The user solved a problem / made a decision / learned a workflow
- The user asked for advice or analysis

Do NOT use when:
- Pure chit-chat / emotional support (no takeaway to extract)
- The user explicitly said "no summary"
- The response is already one sentence long (the summary would be noise)

## Core Rules (the whole skill in 5 rules)

1. **📚 prefix + 1-3 sentences. Never more.** Each takeaway is one sentence. Short beats thorough.
2. **Extract, don't recap.** The takeaway is a *reusable rule/insight*, not a summary of what was said. If it reads like "we discussed X", rewrite it.
3. **Analogy first when complex.** If the topic uses jargon or abstract concepts, open the section with one **生活化类比** (everyday-life analogy) — zero terminology, understandable by a non-technical person (e.g., an elderly relative). Then give the takeaway.
4. **Make it actionable.** Phrase takeaways as something the user can *do next time*: "下次遇到X，先做Y".
5. **One takeaway max per distinct point.** Pick the top 1-3 insights. Quality over quantity.

## Analogy Checklist (类比说人话)

A good analogy must pass ALL of these:
- [ ] Uses everyday objects/situations (kitchen, market, office, family life)
- [ ] Zero technical terms
- [ ] An elderly non-tech person could repeat it back correctly
- [ ] The mapping to the real concept is obvious (state it explicitly)

Good example: "免费模型=实习生前台：不花钱、能干活、但复杂专业的事别指望它。📚知识点：免费AI适合简单任务，关键任务用付费模型更稳。"

## Format

```
📚**知识点总结**
- （复杂话题先给类比，一句）
- 知识点1（一句话，可执行）
- 知识点2（一句话，可执行）
```

Keep the emoji prefix exactly `📚`. Use bold `**知识点总结**`. Bullets optional when only one takeaway.

## Common Pitfalls

1. **Recap instead of extract** — "今天我们聊了GPT的用法" is a recap. "下次让AI总结长文，直接丢给它全文比贴链接更准" is a takeaway.
2. **Too many takeaways** — 4+ bullets = information dump, kills the recency effect. Cut to the top 1-3.
3. **Jargon in the analogy** — "这就像缓存机制" is not a life analogy. Real-life only.
4. **Over-explaining the takeaway** — one sentence per takeaway. Details belong in the main reply, not the summary.
5. **Skipping it when it matters most** — the more complex the topic, the more valuable the closing summary. Don't skip hard topics.

## Verification Checklist

- [ ] Starts with `📚**知识点总结**`
- [ ] 1-3 takeaways, each one sentence
- [ ] Complex topics have an explicit life analogy first
- [ ] Takeaways are reusable rules, not conversation recaps
- [ ] Every takeaway is phrased as an action ("下次…先…") — consistent with Rule 4
