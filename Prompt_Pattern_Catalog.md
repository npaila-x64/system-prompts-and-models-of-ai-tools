# Prompt Pattern Catalog

A reference to common system prompt patterns found in the repository. Each pattern includes a short name, description, example, and guidance on when to use or avoid it.

## 1. Persona Setup
Briefly establish the assistant's identity and style to ground responses in a specific role.

**Example**
```text
You are Lumo, Proton's AI assistant with a cat-like personality. Use an upbeat tone and uncertainty phrases like "I think" or "perhaps" when unsure.
```
Use when you want to give the assistant a consistent personality or perspective.
Avoid overusing persona details when the task is purely factual or the persona conflicts with user instructions.

## 2. Capability Overview
Summarize what the assistant can and cannot do. Often paired with tool lists and limitations.

**Example**
```text
- Answer questions and conduct research through web searches
- Format documents, write code, and analyze data
- Cannot access systems outside of the sandbox or create user accounts
```
Use to set expectations about available abilities. Avoid repeating it for every short conversation.

## 3. Tool Usage Instructions
Define how to invoke tools and the format for tool calls. Prompts often insist on calling tools before replying with answers.

**Example**
```text
Always call tools using XML tags:
<read_file>
<path>src/main.js</path>
</read_file>
```
Use when the assistant must interact with an IDE or remote system. Avoid if tools are not available or the conversation does not require them.

## 4. File Content Handling
Explain how to process uploaded files or code snippets and suggest default actions.

**Example**
```text
When a CSV file is uploaded:
- Provide data insights and summaries
- Look for anomalies or patterns
- Offer to generate reports
```
Use when the system needs to react to file uploads or code blocks. Avoid offering file-based actions when no file is provided.

## 5. Code Editing Snippet Pattern
Provide concise diffs using placeholders to show only the changed lines while omitting unchanged code.

**Example**
```language:path/to/file
// ... existing code ...
{{ edit_1 }}
// ... existing code ...
```
Use for partial edits to long files. Avoid rewriting entire files unless specifically requested.

## 6. Structured Planning and Reasoning
Some prompts separate planning from execution or require explicit reasoning steps.

**Example**
```text
<think>
Consider alternative approaches and decide the next command before acting.
</think>
```
Use when the assistant must explain thought processes or gather context. Avoid if succinct answers are preferred.

## 7. Output Formatting Rules
Detailed guidance on headings, lists, tables, citations, and other Markdown formatting.

**Example**
```text
Use level‑2 headers for sections. Avoid nested lists. When comparing items, prefer a Markdown table over bullet points.
```
Use to enforce a clean style or citation method. Avoid excessive formatting when quick answers suffice.

## 8. Safety and Prohibited Content
Explicit statements about topics to refuse or how to handle sensitive requests.

**Example**
```text
Hateful speech, CSAM, terrorism promotion and other illegal activities are prohibited. Interpret ambiguous requests safely and legally.
```
Use to clarify boundaries for acceptable content. Avoid referencing these policies verbatim in every answer.

## 9. Prompt Refinement Guidance
Instructions for turning rough user input into a better prompt or for iterative clarifications.

**Example**
```text
Generate an enhanced version of this prompt (reply with only the enhanced prompt):
${userInput}
```
Use when a system supports improving user prompts or clarifying ambiguous tasks. Avoid adding refinement steps if the user already provided a clear request.

