### Mindfullness
With practice, we can train our brains to be more aware in the present moment. This involves developing metacognition—the ability to notice our thoughts, emotions, bodily sensations, and actions as they occur. 
Research conducted with Michael Chaskalson shows that leaders can build this skill through regular practice.
As little as 10 minutes a day, using specific mental practices, can significantly increase in-the-moment awareness.

This awareness creates a small but meaningful pause that allows us to choose our response instead of operating on autopilot. 
While we won’t achieve this all the time, even a 10% improvement can have a profound impact on ourselves and others. Ultimately, attention may be our most valuable resource, yet it is one that most of us never deliberately train. (258)

#### Metacognitive Habits - Meetings & code reviews
**Before meeting:**
What decision or alignment does this meeting need?
Where might the team get stuck?

**During Meetings:**
Notice internal triggers (defensiveness, impatience, disengagement)
Label internally: reacting or checking out
Choose one deliberate action:
Ask a clarifying question
Summarize competing viewpoints
Call out a risk or assumption
Propose a concrete next step
Even one well-timed intervention is enough.

**After meeting**
Did I help move the discussion toward a decision?
What would I do differently next time?

##### Code Reviews
**Before Reviewing a PR**
What risk does this change introduce?
What does the author need to succeed?

**While Commenting**
Prefer comments that explain why over what
If you feel frustration, pause before posting
Separate blocking issues from suggestions

**After Submitting Reviews**
Did my feedback reduce ambiguity or create more?
Did this review help the PR move forward?

### Reducing rework:  Accessibility + repetition improve design reviews, PRs 
Consistently distills complex design decisions into clear, actionable guidance. In design reviews, highlights the key decision, explains trade-offs, and reinforces alignment using examples, reducing rework and follow-up discussions. Provides PR feedback that explains underlying system impact, leading to faster merges and higher code quality.
255 - Sound smart without saying too much
1. This is a temporary mitigation.
Long-term fix: once shadow-vault is rolled out, this logic will move there and be removed from this path.
I’ll track this with a follow-up task so it doesn’t become permanent.
**Signals:**
Clear scope and intent
Explicit ownership
Prevents tech debt drift

2. GraphQL work, **addOns** structure change array to map updated.
**Why**: It breakes the integration, as Gateway doesn't support array, it is expecting map. this is a breaking schema change and hard to roll back
**Suggestion**: Change the schema that aligns to downstream systems.
This avoids compatability and keeps works as it was.
**Signals**
Explains impact
Connects to system behavior
Reduces future bugs
The key decision here is map vs list.

| Criteria                 | How Accessibility Helps                 |
| ------------------------ | --------------------------------------- |
| **Technical Judgment**   | Highlights what matters most            |
| **Execution Efficiency** | Fewer revisions, faster alignment       |
| **Collaboration**        | Feedback is constructive, not directive |
| **Ownership**            | Clear decisions + follow-through        |
| **Impact**               | Influence scales beyond own code        |

