# Senior Self-Review + System Design (Pragmatic Style)

---

## 🔹 Self-Review (Backend / GraphQL)

### 1. Ownership  
📘 Cat Ate My Source Code  
- Did I verify end-to-end behavior?
- Am I assuming anything?

→ Did I verify or just trust?

---

### 2. No Coincidence  
📘 Programming by Coincidence  
- Do I know *why* this works?
- Any hidden assumptions (input/downstream)?

→ What assumption makes this pass?

---

### 3. End-to-End Validation  
📘 Tracer Bullets  
- Flow verified: GraphQL → downstream?
- Real scenarios tested (create/update/edge)?

→ Did I prove behavior or just wire it?

---

### 4. Cleanliness  
📘 Software Entropy  
- Any partial mapping / unclear logic / duplication?

→ Would I accept this in others’ PR?

---

### 5. Contract (GraphQL)  
📘 Communicate  
- Backward compatible?
- Clear behavior for optional fields?

→ What happens if field is missing?

---

### 6. Edge Cases  
📘 Programming by Coincidence  
- Null / missing / invalid handled?

→ What bad input breaks this?

---

### 7. Partial Updates  
📘 Programming by Coincidence  
- Omitted vs false vs null handled?

→ Am I overwriting existing state?

---

### 8. Integration  
📘 Tracer Bullets  
- Downstream contract verified?

→ What if downstream ignores this?

---

### 9. Failure  
📘 Pragmatic Thinking  
- Clear error handling?

→ If this fails, can we debug fast?

---

### 10. Retry / Idempotency  
📘 Design for Reality  
- Safe under retry / duplicates?

→ What happens if this runs twice?

---

### 11. Concurrency  
📘 Design for Reality  
- Race conditions / stale updates?

→ What if two updates collide?

---

### 12. Observability  
📘 Communicate  
- Logs + traceability?

→ Can I debug this in prod?

---

### 13. Tests  
📘 Tracer Bullets  
- Edge + failure scenarios covered?

→ What bug can survive?

---

### 14. Readability  
📘 Software Entropy  
- Simple, clear, maintainable?

→ Can I explain in 3 sentences?

---

### 15. Diff  
📘 Software Entropy  
- Any unintended changes?

→ What would I question here?

---

## ⚡ 3-Minute Review
1. Verify (ownership)  
2. Understand (no coincidence)  
3. Validate (real scenarios)  
4. Clean (entropy)  
5. Failures (reality)

---

## 🔹 System Design (Interview)

### 1. Assumptions  
📘 Ownership  
- State assumptions clearly  

→ Am I guessing anything?

---

### 2. Clarity  
📘 No Coincidence  
- Explain *why*, not just *what*  

→ Do I understand this component?

---

### 3. Start Simple  
📘 Tracer Bullets  
- Build baseline → evolve  

→ Am I overcomplicating early?

---

### 4. Avoid Over-Engineering  
📘 Software Entropy  
- Add only when needed  

→ Is this the simplest design?

---

### 5. Communication  
📘 Communicate  
- Structured explanation  

→ Can interviewer follow easily?

---

### 6. Failure Handling  
📘 Design for Reality  
- Cover failures, retries  

→ What happens when this fails?

---

### 7. Idempotency  
📘 Design for Reality  
- Handle duplicates  

→ Safe under retry?

---

### 8. Concurrency  
📘 No Coincidence  
- Race conditions / consistency  

→ What if updates collide?

---

### 9. Data Thinking  
📘 No Coincidence  
- Source of truth, flow  

→ Do I understand data movement?

---

### 10. Observability  
📘 Communicate  
- Logs, metrics, tracing  

→ Can we debug this?

---

### 11. Tradeoffs  
📘 Pragmatic Thinking  
- Explain decisions  

→ Why this vs alternatives?

---

## ⚡ Interview Flow
1. Clarify  
2. Assumptions  
3. Simple design  
4. Scale  
5. Failures  
6. Concurrency  
7. Tradeoffs  

---

## 🔑 Core Principle
**Don’t assume it works — know why it works.**

---

## 🧠 Final Self-Talk
- Did I verify or assume?
- What breaks in production first?
- What would a senior reviewer challenge?

# PR Review Thinking (Mapped to *The Pragmatic Programmer*)

---

## 🔹 Ownership  
📘 Cat Ate My Source Code  
- Are we safe to merge to production?
- Is behavior truly verified?

→ What can break in prod?

---

## 🔹 No Coincidence  
📘 Programming by Coincidence  
- Are we assuming something?
- Do we know *why* this works?

→ What hidden assumption exists?

---

## 🔹 End-to-End Validation  
📘 Tracer Bullets  
- Does this work across all layers?
- Is behavior actually changing?

→ Is this real behavior or just wiring?

---

## 🔹 Clarity & Contract  
📘 Communicate  
- Is API/schema behavior clear?
- Is backward compatibility preserved?

→ Will clients understand and remain unaffected?

---

## 🔹 Failure Thinking  
📘 Design for Reality  
- What happens on failure?
- Is retry safe?

→ How does this fail in production?

---

## 🔹 Concurrency  
📘 Design for Reality  
- Any race conditions?
- Any ordering assumptions?

→ What if two updates collide?

---

## 🔹 Integration  
📘 Tracer Bullets  
- Are downstream assumptions validated?

→ What if downstream behaves differently?

---

## 🔹 Simplicity  
📘 Software Entropy  
- Is this unnecessarily complex?
- Will this degrade over time?

→ Can this be simpler?

---

## 🔹 Tests  
📘 Tracer Bullets  
- Do tests prove behavior (not just execution)?

→ What bug is not covered?

---

## ⚡ Reviewer Flow

1. What changed?  
2. What assumption exists?  
3. What can break?  
4. What is missing?  
5. Is this clear and simple?  

---

## 🧠 Comment Pattern

**Observation + Risk + Question**

Example:
- “I see X implemented, but Y assumption is unclear. If Z happens, behavior may break. Can we validate or add coverage?”

---

## 🔑 Core Principle

**“A reviewer doesn’t confirm correctness—they expose blind spots.”**
