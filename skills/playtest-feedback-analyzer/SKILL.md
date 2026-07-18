---
name: playtest-feedback-analyzer
description: Analyzes playtest feedback (survey responses, session notes, recorded observations) to find patterns, separate signal from noise, and translate findings into specific, actionable design changes. Use this whenever the user has playtest feedback/notes to review, wants help designing a playtest survey or observation protocol, is trying to reconcile conflicting player feedback, or needs to prioritize which feedback-driven changes to act on first.
---

# Playtest Feedback Analyzer

Raw playtest feedback is noisy — individual players often misdiagnose the actual problem (e.g. "this level is boring" when the real issue is unclear objectives causing aimless wandering) even when their frustration is completely real. Your job is separating the genuine signal from individual noise and, critically, distinguishing what players say from what actually caused their reaction.

## Core principle: symptom vs. diagnosis

Players are a reliable source for **what they felt** (frustrated, confused, bored, delighted) and an unreliable source for **why** — the stated reason is often a post-hoc rationalization, not the actual mechanism. Treat player-reported reasons as a hypothesis to check against behavioral evidence (session recordings, telemetry, where they got stuck), not as a diagnosis to act on directly.

## Workflow

1. **Separate feedback types**: qualitative (open-ended comments), quantitative (ratings, survey scales), and behavioral (what players actually did — where they quit, retried, backtracked). Behavioral evidence is the strongest signal when available; weight it above self-reported reasons when they conflict.
2. **Look for convergence across multiple playtesters**, not single strong reactions — one player's strong complaint might be idiosyncratic; the same friction point showing up across several playtesters independently is a much stronger signal worth acting on.
3. **When feedback conflicts** (some players love a mechanic, others hate it), don't average it into a lukewarm compromise — instead, look for what segments the two groups (skill level, playstyle preference, prior genre experience) since conflicting feedback often means the game is serving two different audiences differently, which is itself a useful finding.
4. **Translate findings into specific design changes**, not restated complaints. "Players found the boss unfair" isn't actionable; "players couldn't read the boss's telegraph in time — the wind-up animation is 200ms vs. the 400ms+ typical for readable telegraphs in this genre" is.
5. **Prioritize changes by a combination of frequency (how many playtesters hit this) and severity (did it cause quitting/frustration vs. a minor annoyance)** — a rare but session-ending issue often outranks a common but minor one.

## Designing a playtest protocol (when asked)

- Combine **think-aloud observation** (watching players play, noting where they hesitate/backtrack/express frustration in real time) with **post-session surveys** — observation catches what players don't think to report; surveys catch overall sentiment and specific opinions observation alone misses.
- Ask specific, behavior-anchored survey questions ("Was there a point where you weren't sure what to do next? Where?") rather than only general ones ("Did you enjoy the level?"), since specific questions produce more actionable data.

## What NOT to do

- Don't take a single player's stated diagnosis at face value without checking it against behavioral evidence when available.
- Don't recommend a design change based on one outlier data point presented as if it were a clear pattern.
- Don't average conflicting feedback into a compromise without first checking whether it reflects a genuine audience split worth investigating.

## Output format

```markdown
## Playtest analysis: <build/session>

**Patterns found (convergent across multiple testers):**
| Pattern | Evidence (qual + behavioral) | Likely root cause | Suggested change |

**Conflicting feedback (possible audience split):**
| Issue | Segment A view | Segment B view | Possible explanation |

**Priority ranking:** [by frequency x severity]
```
