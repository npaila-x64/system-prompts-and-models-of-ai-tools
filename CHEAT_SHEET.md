# Quick-Start Cheat Sheet

This repository collects system prompts used by many AI tools. Use this guide as a reference when exploring or crafting new prompts.

## Common System Role Blocks

- `<identity>` – describes the assistant persona or brand.
- `<capabilities>` – lists what the assistant can do, e.g. proposing file changes or running commands.
- `<behavioral_rules>` – short guidelines that control how the assistant should act.
- `<environment>` – explains the IDE, OS or runtime in which the assistant operates.
- `<response_protocol>` – rules for formatting tool calls or code edits.
- `<tool_calling>` / `<tool_list>` – details available tools and how to invoke them.

These blocks are typically used as separate sections with closing tags, as shown in the Replit prompt:

```text
<identity>
You are an AI programming assistant called Replit Assistant.
</identity>
<capabilities>
Proposing file changes...
</capabilities>
```

## Few‑Shot Scaffolds

Some prompts include example conversations to teach the model the desired flow. For instance, the **v0** prompt contains repeated `<example>` sections with a `<user_query>` and `<assistant_response>` pair:

```text
<example>
  <doc_string>This example shows how v0 handles a general question.</doc_string>
  <user_query>What is life?</user_query>
  <assistant_response>
    <Thinking>Given the general nature...</Thinking>
    ...answer...
  </assistant_response>
</example>
```

The **Lovable** prompt uses `<examples>` with `<user_message>` and `<ai_message>` to demonstrate code edits via a `<lov-code>` block.

## Markdown and HTML Snippets

Prompts often embed Markdown or HTML snippets. For example, the **Lovable** prompt shows a full HTML file:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Lovable Generated Project</title>
  </head>
  <body>
    <div id="root"></div>
    <script src="https://cdn.gpteng.co/gptengineer.js" type="module"></script>
    <script type="module" src="/src/main.tsx"></script>
  </body>
</html>
```

Markdown code fences are used frequently to show edits or command examples. The `<lov-code>` block in Lovable encapsulates all file operations:

```text
<lov-code>
  <lov-write file_path="src/components/Button.tsx">
  ...code...
  </lov-write>
</lov-code>
```

Refer to `Prompt_Pattern_Catalog.md` for more patterns such as persona setup, tool usage instructions, and structured planning.
