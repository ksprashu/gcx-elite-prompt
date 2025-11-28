# Gemini CLI Extension: Elite Prompt (gcx-elite-prompt)

This repository contains the **Elite Prompt** extension for the Gemini CLI. It transforms the CLI into a stateful, autonomous software engineering agent optimized for **Gemini 3 Pro**, utilizing official "Agentic Workflow" strategies.

## 📂 Project Structure

*   **`gemini-extension.json`**: The extension manifest. It maps the `/elite:*` slash commands to their definition files and registers `ELITE_PROMPT.md` as the core system instruction.
*   **`ELITE_PROMPT.md`**: The master system prompt. It defines the agent's persona ("Elite"), operational protocols (Perception → Strategy → Execution → Reflection), and output format. This file is loaded into the context of every session.
*   **`commands/elite/`**: Contains the TOML definitions for the cognitive trigger commands.
    *   `audit.toml`: `/elite:audit` - Forces a risk assessment and assumption check.
    *   `boot.toml`: `/elite:boot` - Performs a context wipe and system reset.
    *   `design.toml`: `/elite:design` - Triggers architectural analysis and planning.
    *   `log.toml`: `/elite:log` - Persists the current state to disk.
    *   `reason.toml`: `/elite:reason` - Activates deep abductive reasoning.
*   **`.gemini/`**: Directory for local agent state (e.g., `BACKLOG.md`).

## 🧠 Core Architecture

The extension implements a rigorous **Cognitive Loop**:

1.  **Perception:** Gathering context via `codebase_investigator` and `glob`/`grep`.
2.  **Strategy:** Decomposing tasks and planning via `write_todos`.
3.  **Execution:** Atomic, verified actions using `replace`, `write_file`, etc.
4.  **Reflection:** Verification and self-correction.

## 🚀 Usage & Installation

### Installation
To install this extension locally:

```bash
gemini extensions install .
```

### Cognitive Triggers
The following commands are available to steer the agent's behavior:

*   `/elite:audit` - **Stop & Think**: Use when the agent seems confident but might be missing edge cases.
*   `/elite:boot` - **Reset**: Use to clear a cluttered context window and restart the session cleanly.
*   `/elite:design` - **Plan**: Use at the start of a complex feature to generate a specification.
*   `/elite:log` - **Save**: Use to save the current progress and plan to `.gemini/BACKLOG.md`.
*   `/elite:reason` - **Deep Dive**: Use when the agent is stuck or facing a complex bug.

## 🛠️ Development

*   **Modifying Prompts**: Edit `ELITE_PROMPT.md` to change the core persona or workflow. Edit files in `commands/elite/` to adjust the specific trigger behaviors.
*   **Testing Changes**: After editing files, you may need to re-run `gemini extensions install .` or simply restart the CLI session for changes to `ELITE_PROMPT.md` to take effect (depending on how the CLI caches extensions).
*   **Conventions**:
    *   **TOML**: Command files must be valid TOML.
    *   **Markdown**: Prompts use Markdown for formatting (bolding, lists, etc.) to guide the LLM.
    *   **Tags**: XML-style tags (e.g., `<role>`, `<constraints>`) are used in the system prompt to clearly delimit sections for the model.
