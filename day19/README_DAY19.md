# Day 19 — CODEOWNERS
<p>
  <img src="./day19.png" width="100%" alt="Open Source Etiquette">
</p>
## Automatically Connect Code Changes With the Right Reviewers

---

## 1. What is CODEOWNERS?

`CODEOWNERS` is a special file supported by GitHub that defines which people or teams are responsible for reviewing changes to specific parts of a repository.

In simple words:

> **CODEOWNERS tells GitHub: "When someone changes this code, ask these people to review it."**

For example, imagine you have a project like this:

```text
my-project/
│
├── backend/
│   ├── api.py
│   ├── database.py
│   └── auth.py
│
├── frontend/
│   ├── app.js
│   └── dashboard.js
│
├── docs/
│   └── README.md
│
└── .github/
    └── CODEOWNERS