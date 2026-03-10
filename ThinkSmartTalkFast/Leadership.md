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

### Reframing : How we think about how we doing
I apply mindset and reframing to drive clarity and effectiveness in my work. In design reviews, I focus on distilling key decisions and trade-offs to align the team quickly. 
In code reviews, I provide feedback that emphasizes intent and system impact, helping reduce rework and improve code quality.

### Storytelling
Clearly articulating where we’re going (the concrete outcome), why it’s achievable (assumptions, constraints, and evidence), and how we’ll evaluate progress (signals of success, failure, and learning). 
Framing discussions this way aligns mental models early, reduces rework during execution, and helps teams adapt to uncertainty without thrashing.

### Communicate for alignment, not completeness.
Effective communication is not about sharing everything I know, but about sharing what others need to hear to move forward. 
Apply curiosity to understand my audience’s context and empathy to adapt my message. 
Prioritize clarity, anticipate resistance, and anchor decisions in outcomes that matter—especially in complex or uncertain systems

### Make belief - 270
On the other end of the spectrum is faith. Faith is a conviction that does not require evidence. In between fact and faith is a belief.
A belief is a strongly held conviction open to new evidence. So a belief doesn't have to be true, it just has to be useful. So beliefs are tools, not truths.
Beliefs are tools, not truth. So what that means is that I can try on an alternative perspective if it serves me. So as opposed to thinking I'm bad at presenting, maybe I can do a turnaround on that and say, I'm not bad at presenting.
Is there any chance, even a 1% minuscule little chance, that might also be true. Yes, of course it could be. The fact that I'm getting up on stage.

### Bring clarity to Complicated Conversation
So I think the bottom line here, Florian, is if you can buy yourself just a little bit of time, you can think a little bit more, react rather than respond. I make a difference between those two. React is to act again, meaning you think about it and then you act, respond is just to immediately do something.
What I'm hearing is that you respond quickly and maybe buying yourself some time to react will help.
**Impromptu Speaking**
A structure provides a roadmap like a GPS. It is hard to get lost if you have a structure. So by knowing my structure well, let's say I want to use problem, solution, benefit.
I'm trying to persuade people. I know the problem well, I've thought about it. I've done research, whatever.
I know the problem well. The solution is something I really believe in, so I also know that well, and I've thought about how I and others benefit. So by having those different parts of the structure known well, because I've thought about, spent time doing it, when I'm in the process of delivering the communication, and if for some reason I feel a little lost or concerned, I simply have to say, okay, I just talked about the problem, I know solution always follows.
So that's how a structure provides a roadmap. Now, if you go from memorizing or using a technique like the memory palace to just relying on structure, it can feel like a big leap. And that's why practice in low stake situations is important

Do you suggest I use the basic trainings I got with memory palace and how to adjust that so that I can actually speak coherently, but also not be so fixated on that cognitive load, which is exactly my stumbling blocks.?
How can we feel more comfortable getting through material spontaneously? 
I really believe the answer is structure and practice. Structure as we were just talking about.

What, so what, now what, is an example of structure. There are many problem, solution, benefit, past, present, future, comparison, contrast, conclusion. Lots of different structures.

A structure provides a roadmap like a GPS. It is hard to get lost if you have a structure. So by knowing my structure well, let's say I want to use problem, solution, benefit.

I'm trying to persuade people. I know the problem well, I've thought about it. I've done research, whatever.

I know the problem well. The solution is something I really believe in, so I also know that well, and I've thought about how I and others benefit. So by having those different parts of the structure known well, because I've thought about, spent time doing it, when I'm in the process of delivering the communication, and if for some reason I feel a little lost or concerned, I simply have to say, okay, I just talked about the problem, I know solution always follows.
