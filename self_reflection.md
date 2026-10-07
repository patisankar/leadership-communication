# Core Patterns & Solutions

---
## PR Review: Pause-and-Think Checklist

Before sending a PR review, pause for 2–5 minutes.

## Understand the change

1. What problem is this PR solving?
2. What is the complete execution flow?
3. Which services, classes, APIs, databases, or events are affected?
4. What assumptions and invariants must remain true?
5. What happens on success, failure, retry, timeout, and duplicate requests?

## Review the design

Ask:

- Is this the simplest safe design?
- Are responsibilities in the right place?
- Does it preserve backward compatibility?
- Are concurrency, ordering, idempotency, and thread-safety handled?
- Could this create a regression, data inconsistency, or performance problem?
- Are observability and rollback covered?

## Review the implementation

Check:

- Correctness
- Edge cases
- Error handling
- Tests
- Security
- Performance
- Naming and readability
- Configuration and deployment impact

## Before writing a comment

Ask:

1. Is this a real defect, risk, or required improvement?
2. Can I explain the impact clearly?
3. Do I have enough context to make this comment?
4. Is the comment specific and actionable?
5. Is this a blocking issue or an optional suggestion?

## Comment format

```text
Observation:
I noticed that ...

Risk:
This could cause ...

Recommendation:
Could we ...?

Reason:
This would ensure ...
```

## 1. Emotional thinking : 5 whys to control
**High-stake situation: How to pause your thinking**

### The Surface Story
I came in questioning whether I actually have real problem-solving skills—whether I can go deep and find optimized solutions. On the surface, it felt like a capability gap.

### Why 1: The Pattern
I tend to stay at the surface layer of problems. Why? Because when I *do* research deeply, people dismiss it as overthinking rather than valuing the rigor. So I learned: going deep gets punished.

### Why 2: The Real Constraint
I want to close issues early because my manager doesn't like problems that linger. Speed is rewarded; depth is seen as inefficiency. So I escalate fast, before I've really investigated.

### Why 3: The Internal Conflict
I have both speeds available—the careful investigator and the quick responder—but fast thinking is overriding the slow thinker. I'm not lacking skills; I'm being dominated by urgency and fear of judgment.

### Why 4: The Missing Move
The PWR deployment issue showed this clearly. I escalated without doing due diligence—no logs, no isolated testing—because I assumed it needed to be closed immediately. I never paused to ask: "What does this problem actually need from me?"

### Why 5: The Real Issue
I don't have a problem-solving skills problem. I have a *discernment* problem. I'm not choosing which speed to use based on what the situation calls for; I'm defaulting to fast because I'm afraid staying with a problem will be judged as slow or inefficient.

### The Breakthrough
The answer isn't to go faster or slower. It's to **pause** and ask one question: *"What does this problem actually need from me right now?"* That pause is the bridge between my fear and my actual capability. I have the depth. I just need permission to use it—and that permission has to come from me first.

### The Practice
**Before I escalate or commit to a fix:**
1. Pause for 30 seconds
2. Ask: "What does this problem actually need from me right now?"
3. Then act

---

## 3. My ML Capstone: From Autopilot to Real Understanding
**Learning pattern: How to go deep in a fast-track course**

### The Problem
I'm in a fast-track ML course doing my capstone project. I'm going through activities on autopilot—checking them off without really understanding what I'm building or why. Speed over depth, again.

### The Pattern (Again)
It's the same issue as DSA and problem-solving at work. I rush through material, memorize the *what*, skip the *why*, and end up without real understanding.

### The Solution: The Five Questions Framework
Before I implement any ML concept (decision tree, neural networks, etc.), I answer these five questions:

1. **What is it?** — Definition and core concept
2. **Why does it exist?** — What problem does it solve?
3. **When to use it?** — What scenarios call for this approach?
4. **How to use it?** — Implementation and practical application
5. **How to optimize it?** — Trade-offs, tuning, performance considerations

### Making It Stick
I can't rely on memory or willpower. So I make it a hard rule: **Before I write any code for the capstone, I document these five answers.**

No shortcuts. No autopilot.

### The Practice
For each ML concept in my capstone:
1. Answer the five questions (write them down)
2. Then implement the code
3. Then optimize based on what I learned

---

## 4. My Communication Under Pressure: From Frozen to Confident
**Communication pattern: How to ask for help effectively**

### The Problem
When I have less instinct, time is running out, and I need to ask my lead or architect for help, I freeze up. My spoken English breaks. I'm not confident in how to ask a great question or get their help effectively.

### Why It Happens
It's not just language or confidence. I don't have a *structure* for how to ask in a way that actually gets me help. Without structure, I either:
- Ask too vaguely (they don't understand what I need)
- Ask too much at once (it feels like I'm demanding)
- Either way, I don't get what I need

### The Real Issue
I'm uncertain about *how* to ask, not just *whether* to ask. That uncertainty makes me freeze or rush, which makes my English worse, which makes me less confident.

### The Solution: The Four-Part Ask Structure
Before I ask my lead or architect for help, I use this structure:

1. **Here's what I'm trying to do** — Context and goal
2. **Here's where I'm stuck** — Specific blocker (not vague)
3. **Here's what I've already tried** — Shows I've done legwork
4. **Here's what I need from you** — Clear, specific ask

### Why This Works
- It's simple and repeatable
- It shows I've thought it through
- It makes my ask clear, even under pressure
- It gives them exactly what they need to help

### Making It Stick
Before I ask for help:
1. Write down these four things (even just notes)
2. Then ask out loud

# Managing High-Pressure Interactions with My Manager

### Before the conversation
1. **Prepare core points** — Identify the 2–3 key facts/answers he's likely to ask
   about. Write them down if needed. This isn't scripting; it's anchoring in what I
   already know.
2. **Check posture** — Sit or stand upright, open chest, shoulders back. Signals
   readiness, not fear.
3. **Breathe** — Take three deep breaths before he arrives or before the call to
   calm the nervous system preemptively.

### During the conversation
4. **Speak clearly, normal pace** — Don't rush. Rushing signals panic; steady
   delivery signals control.
5. **Make eye contact** — Hold his gaze when answering. Non-negotiable.
6. **Cut filler words** — No "um," "like," "you know." Silence is better than
   filler — pause silently, then speak.
7. **Own what I don't know** — No hedging or apologizing. Say "I'll get back to you
   on that" or "Let me verify and send it over." No explanation needed.
8. **Match his intensity with steadiness, not aggression** — Stay calm and direct.
   Calm is the source of power here, not volume.

### After the conversation
9. **Review what worked** — Did holding eye contact shift his tone? Did clear,
   steady speech land better? Track what moves the dynamic over time.

## Note on "Pause Thinking"

Originally considered: pausing before responding to interrupt the fear response and
let actual competence surface ("Let me think about that for a second").

**Adjusted because** he watches closely while I think, so a visible pause can read as
doubt rather than composure. The adapted approach: arrive at the conversation already
prepared (per tactic #1), so there's less need to visibly think in front of him in the
moment.


No freezing. No rambling. Just structure.

### The Practice
High-pressure moment → Use the four-part structure → Ask with confidence

