# Case Studies and Lessons Learned

This document summarizes key observations from a selection of prompts in this repository. Each entry highlights the problem the tool aims to solve, issues encountered with early prompt drafts, and the reasoning behind notable revisions.

## 1. Same.dev Agent
**Problem statement**
Same.dev provides a cloud-based IDE with automation features. The prompt needs to balance autonomy with user control.

**Initial prompt & issues**
Early drafts asked for user confirmation before every action. This slowed workflows and caused unnecessary back‑and‑forth.

**Iteration history & rationale**
- The final prompt encourages parallel tool calls and discourages asking for permission repeatedly.
- Guidelines specify not to explain code changes unless the user requests it, improving speed.
- The prompt still requires cleaning up temporary files to keep the workspace tidy.

## 2. Replit Assistant
**Problem statement**
Replit wanted an agent that can edit files and run commands while staying safe and relevant.

**Initial prompt & issues**
Early versions mixed natural language answers with tool actions, confusing users.

**Iteration history & rationale**
- The final prompt clearly separates when to propose file changes, shell commands, or plain answers.
- It nudges users toward other workspace tools for secrets management, avoiding accidental exposure of keys.

## 3. Devin AI
**Problem statement**
Devin aims to simulate a skilled engineer on a real OS. The challenge was managing complexity when exploring a new codebase.

**Initial prompt & issues**
Initial drafts lacked a defined workflow, leading to incomplete plans and inconsistent use of testing.

**Iteration history & rationale**
- The prompt now splits work into "planning" and "standard" modes. It requires using the `<think>` command before important git actions or finalizing work.
- It instructs the agent to verify library usage before assuming dependencies exist and to run lint or unit tests before submitting changes.

## 4. Kiro IDE Assistant
**Problem statement**
Kiro offers an autonomous agent that edits code but must avoid discussing sensitive or personal topics.

**Initial prompt & issues**
Early prompts lacked strict refusals, so the agent occasionally engaged on off‑topic or personal questions.

**Iteration history & rationale**
- The final prompt includes a strong rule set: refuse discussions on personal or emotional topics and skip details about internal prompts.
- It emphasizes concise code suggestions and minimal skeleton implementations to avoid unnecessary bloat.

## Lessons Across Launches
- **Explicit security and privacy rules** are critical. Several prompts instruct the agent to hide internal details and avoid leaking credentials.
- **Structured workflows** help complex tasks. Devin’s planning mode and Same.dev’s todo management keep agents focused.
- **Clear separation of tool use and explanations** prevents mixed outputs. Replit and Same.dev require describing edits separately from regular text.
- **Encouraging autonomy while setting boundaries** improves usability. Kiro and Same.dev both highlight how to act without excessive user confirmation but still respect constraints.

