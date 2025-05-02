# Noah's Cursor Guide to AI Software Engineering & Product Development

**Author:** Noah Peden
**Creation Date:** May 2, 2025

---

## Getting Started

To begin productive AI-driven software development, you'll primarily need:

* **Gemini 2.5 Pro Thinking**
* **Cursor with Claude Sonnet 3.7 Thinking**

*(Note: While earlier versions used Grok 3, we've transitioned to **Gemini 2.5 Pro** due to its superior 1M token context window and strong software architecture capabilities, essential for complex development projects.)*

Setting up everything correctly is critical. For scalable, maintainable codebases, take the time upfront to structure your project's foundational documents.

**Key Principle:** *Planning is essential.* Avoid autonomous AI-driven planning or risk an unmanageable codebase.

---

## Project Setup

### 1. Product Requirements Document (PRD)

* Outline your product vision and ask **Gemini 2.5 Pro Thinking** to generate a clear **Product Requirements Document (PRD)** in Markdown format (`prd.md`).
* Review and refine it thoroughly. The goal is clarity around structure, purpose, and requirements.

### 2. Tech Stack and `.cursor/rules`

* Have **Gemini 2.5 Pro Thinking** recommend the optimal tech stack for your product (e.g., Next.js, PostgreSQL, Vercel for an e-commerce app). Save as `tech-stack.md`. OR go with what you know, like Next.js.

  * Aim for simplicity and robustness.
* In Cursor, open the command palette (`Cmd + Shift + P`), type "rules", and select "Configure Rules for '.cursor'".
* Use the `/Generate Cursor Rules` command within Cursor chat, ensuring:

  * Emphasis on modularity (multiple files) over monolithic structures.
  * Add essential "Always" rules such as:

```
# IMPORTANT:
# Always read memory-bank/@architecture.md before writing any code. Include complete database schema.
# Always read memory-bank/@prd.md before writing any code.
# After adding significant features or milestones, update memory-bank/@architecture.md.
```

* Adjust rules to guide AI towards best practices (architecture, state management, scalability).

### 3. Implementation Plan

* Provide **Gemini 2.5 Pro Thinking** with:

  * PRD (`prd.md`)
  * Tech stack (`tech-stack.md`)
  * Cursor rules (`.cursor/rules`)
* Request a detailed **Implementation Plan** (`implementation-plan.md`) with:

  * Precise, small steps.
  * Specific tests for each step.
  * No initial code, just structured instructions.

### 4. Memory Bank

* Set up your project in Cursor:
* Create a folder named `memory-bank` with these files:

  * `prd.md`
  * `tech-stack.md`
  * `implementation-plan.md`
  * `progress.md` (initially empty)
  * `architecture.md` (initially empty)
* *(The `.cursor/rules` file is auto-created by Cursor.)*

---

## Developing the Core Product

### Clarifying Instructions

* Use **Claude Sonnet 3.7 Thinking** in Cursor.
* Prompt: *Read `/memory-bank`. Is `implementation-plan.md` clear? What clarifications do you need?*
* Answer any queries and update the implementation plan accordingly.

### Initial Implementation Step

* Prompt: *Read all `/memory-bank` documents and proceed with Step 1 from `implementation-plan.md`. Pause for test validation before Step 2. Upon validation, update `progress.md` and document file purposes in `architecture.md`.*

### Iterative Workflow

* After completing each step:

  * Commit changes to Git.
  * Prompt Claude: *Review progress in memory-bank, proceed with the next step upon validation.*
* Repeat until the entire `implementation-plan.md` is executed.

---

## Enhancing the Product

With the foundational product complete, incrementally enhance features:

* For each major feature, create a new `feature-implementation.md` with detailed steps and tests.
* Proceed iteratively, validating and documenting progress.

---

## Troubleshooting and Debugging

* If code breaks or a feature doesn't work:

  * Restore previous state in Cursor and refine prompts.
* For errors:

  * Copy errors from the console (JavaScript) or provide visual evidence (screenshots).
  * Optionally use tools like [BrowserTools](https://browsertools.agentdesk.ai/installation) to streamline this.
* If stuck:

  * Revert to last stable Git commit (`git reset`).
  * If deeply stuck, use [RepoPrompt](https://repoprompt.com/) or [uithub](https://uithub.com/) for holistic codebase review with Gemini.

---

## Additional Tools and Tips

* **Minor Code Edits:** Claude Sonnet 3.7 or GPT-4.1 (non thinking versions)
* **Marketing Copy:** GPT-4.5
* **Visual Assets:** ChatGPT-4o
* **Effective Prompts:** Add “take your time to ensure accuracy, ask for clarity if needed.”


