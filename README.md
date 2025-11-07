# Gemini CLI Extension: Elite Prompt & Triggers

This extension provides an elite, rigorous, and persistent system prompt for the Gemini CLI, along with a set of namespaced "mental trigger" slash commands to force specific agent behaviors.

## Features

*   **Elite System Prompt (`ELITE_PROMPT.md`):** A highly structured prompt that enforces:
    *   **Persistence:** Maintains state across crashes via `.gemini/CURRENT_SESSION.md`.
    *   **Rigor:** Systems thinking and first-principles analysis.
    *   **Craftsmanship:** "Ultrathink" mode for elegant solutions.
    *   **Da Vinci Planning:** Architectural foresight over simple task lists.
*   **Trigger Commands (Namespaced):**
    *   `/elite:reset`: Master reset. Re-reads the prompt and clears assumptions.
    *   `/elite:freeze`: Emergency brake. Stops execution and forces immediate verification.
    *   `/elite:ultrathink`: Enters deep philosophical planning mode.
    *   `/elite:save`: Forces an immediate state save to disk.

## Installation

You can install this extension directly from GitHub or from a local directory.

### Option 1: Install from GitHub (Recommended)

```bash
gemini extensions install github.com/ksprashanth/gcx-elite-prompt
```

### Option 2: Install Locally

If you have cloned the repository:

```bash
git clone https://github.com/ksprashanth/gcx-elite-prompt.git
cd gcx-elite-prompt
gemini extensions install .
```

## Usage

Once installed, the Elite Prompt will automatically be active.

You can use the trigger commands at any time during a chat:

> User: You're moving too fast, I don't trust that last edit.
> User: /elite:freeze

> User: This approach is getting messy. Let's rethink it.
> User: /elite:ultrathink
