# Day 12 — Responding to Code Review Comments

## 🎯 Goal

Code review is not just about accepting or rejecting feedback. It is an engineering conversation where you understand the concern, decide what action is appropriate, make the change when needed, and clearly communicate what you changed.

---

## 🔄 The 4-Step Code Review Response Flow

### 1. Understand

Before replying, understand exactly what the reviewer is pointing out.

Ask yourself:

- What problem did the reviewer notice?
- Which file or line is affected?
- Is the comment about correctness, readability, security, performance, testing, or maintainability?
- Can I reproduce or verify the concern?

**Example:**

> Reviewer: "Consider validating that email is not blank before saving."

The actual concern is that invalid input could reach the save operation.

---

### 2. Decide

After understanding the comment, choose an appropriate response.

You can:

- **Agree** → Make the requested change.
- **Ask for clarification** → When the requirement is unclear.
- **Explain a trade-off** → When there is a technical reason not to make the change exactly as suggested.
- **Propose an alternative** → When another solution addresses the same concern better.

A good response should focus on the technical issue rather than becoming defensive.

---

### 3. Respond

A strong review response should tell the reviewer what happened.

Instead of:

> "Fixed."

Use something like:

> "Good catch. I added a non-empty validation check and added a test for blank email input. Valid email behavior remains unchanged."

This gives the reviewer useful evidence without making them guess what changed.

---

### 4. Close

Resolve the conversation only after the concern has actually been addressed.

A useful sequence is:

```text
Comment → Change → Test → Reply → Resolve