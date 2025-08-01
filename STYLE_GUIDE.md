# Style Guide & Quality Checklist

This repository contains a collection of system prompts and models from many AI tools. To keep future additions consistent and easy to understand, follow these guidelines when contributing new prompts or updating existing ones.

## Tone and Persona

- **Direct second person voice** – write instructions and capabilities as "You do..." or "You are...". Avoid passive language.
- **Professional but concise** – keep sentences short and informative. Remove filler words.
- **Respect existing personas** – if the agent has a defined identity (for example in an `<identity>` block), maintain that personality in new content.
- **No marketing fluff** – prompts should describe behavior and limitations, not hype the product.

## Formatting Conventions

- Use plain text files with the `.txt` extension for prompts.
- Separate logical sections with clear headings or XML‑style tags such as `<identity>`, `<capabilities>`, `<behavioral_rules>`, and `<response_protocol>`. Close every tag explicitly.
- Place tags on their own line and indent contents with two spaces for readability.
- When including code, enclose it in fenced code blocks using triple backticks (```). Specify the language when possible.
- Keep line length under 120 characters to improve diff readability.
- If listing tools or instructions, use bulleted lists (`- item`) or numbered lists.
- Do not embed external links directly in prompts unless they are required for functionality.

## Checklist Before Merging

Answer **YES** to each item before submitting a pull request:

1. **Consistent tone** – Does the prompt use direct, concise language and maintain the agent persona?
2. **Proper structure** – Are all tags or headings properly opened and closed? Are sections clearly separated?
3. **Formatting** – Are lists, code blocks, and line lengths formatted as described above?
4. **No placeholders** – Have all TODOs or filler text been removed?
5. **Licensing** – If copying content from elsewhere, is it appropriately attributed or permitted?
6. **File naming** – Does the prompt reside in the correct directory and use a descriptive name ending in `.txt`?
7. **Diff sanity** – Have you reviewed the diff to ensure only the intended changes are included?

Following this style guide will keep the prompts easy to read and modify. When in doubt, match the style of existing files.
