# Pragmatic Engineering Guide (Self-Review + PR + System Design)

---

## 🔹 1. Self-Review (Backend / GraphQL)

### Core Checks

**Ownership** 📘  
- Verified end-to-end behavior?

→ Did I verify or assume?

---

**Understanding** 📘  
- Do I know *why* this works?

→ What assumption exists?

---

**End-to-End** 📘  
- Flow complete (GraphQL → downstream)?
- Real scenarios tested?

→ Behavior proven or just wired?

---

**Contract** 📘  
- Backward compatible?
- Clear optional field behavior?

→ What if field is missing?

---

**Edge Cases** 📘  
- Invalid / null / omitted handled?
- Partial update safe?

→ Am I overwriting state?

---

**Integration** 📘  
- Downstream contract verified?

→ What if it’s ignored?

---

**Failure & Safety** 📘  
- Errors clear?
- Retry/idempotency safe?
- Concurrency handled?

→ What breaks in production?

---

**Observability & Tests** 📘  
- Logs + traceability?
- Edge + failure tested?

→ What bug can survive?

---

**Simplicity** 📘  
- Clear, minimal, maintainable?

→ Can I explain in 3 sentences?

---

## ⚡ 2-Min Review
1. Verify behavior  
2. Check assumptions  
3. Validate edge cases  
4. Think failures  
5. Keep it simple  

---

## 🔹 2. PR Review (Reviewer Mindset)

### Focus = Find Blind Spots

- What changed?  
- What assumption exists?  
- What can break?  
- What is missing?  
- Is it simple and clear?  

---

### Key Areas

- **Behavior** → Is it truly working end-to-end?  
- **Contract** → Any API/schema risk?  
- **Failure** → What happens on error/retry?  
- **Concurrency** → Any race conditions?  
- **Integration** → Any downstream mismatch?  
- **Tests** → What is not covered?  

---

### Comment Pattern
**Observation + Risk + Question**

Example:
“I see X implemented, but Y assumption is unclear. If Z happens, behavior may break. Can we validate?”

---

## 🔹 3. System Design (Interview)

### Approach

1. Clarify requirements  
2. State assumptions  
3. Start simple  
4. Scale step-by-step  
5. Handle failures  
6. Address concurrency  
7. Discuss tradeoffs  

---

### Key Thinking

- **Clarity** → Explain *why*, not just *what*  
- **Simplicity** → Avoid over-engineering  
- **Failure** → Design for retries, errors  
- **Data** → Clear source of truth + flow  
- **Observability** → Debuggable system  

---

## 🔑 Core Principle

**Don’t assume it works — know why it works.**

---

## 🧠 Final Self-Talk

- What assumption am I making?
- What breaks in production first?
- Did I prove behavior end-to-end?
- What would a senior engineer challenge?
