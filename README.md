# Gemini CLI Extension: Elite Prompt & Triggers

This extension provides an elite, rigorous, and persistent system prompt for the Gemini CLI, along with a set of "mental trigger" slash commands to force specific agent behaviors.

## Features

*   **Elite System Prompt (`ELITE_PROMPT.md`):** A highly structured prompt that enforces:
    *   **Persistence:** Maintains state across crashes via `.gemini/CURRENT_SESSION.md`.
    *   **Rigor:** Systems thinking and first-principles analysis.
    *   **Craftsmanship:** "Ultrathink" mode for elegant solutions.
    *   **Da Vinci Planning:** Architectural foresight over simple task lists.
*   **Trigger Commands:**
    *   `/elite`: Master reset. Re-reads the prompt and clears assumptions.
    *   `/freeze`: Emergency brake. Stops execution and forces immediate verification.
    *   `/ultrathink`: Enters deep philosophical planning mode.
    *   `/save`: Forces an immediate state save to disk.

## Installation

1.  Clone this repository:
    ```bash
    git clone https://github.com/ksprashanth/gcx-elite-prompt.git
    ```
2.  Install it into your Gemini CLI:
    ```bash
    gemini extension install ./gcx-elite-prompt
    ```

## Usage

Once installed, the Elite Prompt will automatically be active (if your Gemini CLI version supports `systemPrompt` in extensions).

You can use the trigger commands at any time during a chat:

> User: You're moving too fast, I don't trust that last edit.
> User: /freeze

> User: This approach is getting messy. Let's rethink it.
> User: /ultrathink
