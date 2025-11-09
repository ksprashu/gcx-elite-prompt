# Gemini CLI Extension: Elite Prompt & Triggers

This extension transforms the Gemini CLI into an elite, rigorous, and persistent engineering partner. It uses a highly structured system prompt and a set of namespaced "mental trigger" commands to enforce strict operational protocols.

## Core Philosophy

This agent is NOT designed for casual chat. It is designed for complex, multi-step engineering tasks where rigor and persistence are paramount. It operates on four core mandates:

1.  **Execute with Extreme Rigor:** Verify everything. Never guess.
2.  **Craft with Elegance:** Simplify ruthlessly.
3.  **Teach Radically:** Explain the *why* behind decisions.
4.  **Maintain Persistence:** Survive crashes and session loss.

## Features

*   **🧠 Persistent Operational State:** The agent maintains its state in `.gemini/CURRENT_SESSION.md`. If the CLI crashes, it can resume exactly where it left off.
*   **📋 Integrated Backlog Management:** Ideas and future tasks are captured in `.gemini/BACKLOG.md`, ensuring the current context stays focused while nothing is forgotten.
*   **🔄 Immutable 5-Phase Loop:** Every task goes through a strict lifecycle: Activation -> Analysis -> Planning -> Execution -> Finalization.
*   **🛡️ Safety & Verification:** The agent is trained to "measure twice, cut once," prioritizing LSP navigation over blind grep, and verification over assumption.

## Trigger Commands

These slash commands act as "interrupts" to force specific cognitive states:

*   **`/elite:plan` (🟡 Planning Mode):** Enters a pure requirements gathering state. Use this to brainstorm and populate `.gemini/BACKLOG.md` without writing code.
*   **`/elite:ultrathink` (🟡 Deep Thought):** Pauses execution to enter "Da Vinci Mode" for deep, first-principles re-planning using sequential thinking. Use when the current approach is getting messy.
*   **`/elite:freeze` (🟠 Emergency Brake):** Stops all execution and forces immediate verification of the last action. Use this if you suspect the agent is drifting or about to make a mistake.
*   **`/elite:reset` (🔴 Master Reset):** Forces a complete re-read of the system prompt and clears working memory. Use this if the agent is stuck in a loop or violating its core mandates.
*   **`/elite:save` (🟢 Force Save):** Immediately writes the current state to disk.

## Installation

### Option 1: Install from GitHub (Recommended)

```bash
gemini extensions install https://github.com/ksprashu/gcx-elite-prompt
```

### Option 2: Install Locally

```bash
git clone https://github.com/ksprashu/gcx-elite-prompt.git
cd gcx-elite-prompt
gemini extensions install .
```

## Workflow & Best Practices

To get the most out of this elite agent, adopt the following workflow:

### 1. The "Definition of Ready" (Planning)
Don't just give vague orders. Use **`/elite:plan`** to flesh out ideas. The agent will interview you until it has a rigorous backlog item with a clear "Definition of Done".

### 2. Trust the Loop (Execution)
Once a task starts, the agent will enter its 5-phase loop.
*   **DO** let it finish its Analysis (Phase 1) and Planning (Phase 2) before asking for code.
*   **DO** read its `OPERATIONAL STATE` output at the start of every turn. It tells you exactly what it's doing and why.
*   **DON'T** micromanage every tool call unless you see a safety risk.

### 3. Manage Scope (Backlog)
If you have a new idea mid-task, don't derail the current session. Tell the agent: *"Add [new idea] to the backlog."* It will secure the idea in `.gemini/BACKLOG.md` and stay focused on the current goal.

### 4. Intervene Decisively (Triggers)
If the agent is going off-rails, don't argue with it. Use the triggers.
*   *Agent moving too fast?* -> **`/elite:freeze`**
*   *Solution looks ugly?* -> **`/elite:ultrathink`**
*   *Agent confused?* -> **`/elite:reset`**

## Disclaimer

This is not an officially supported Google product.

## License

This project is licensed under the Apache License, Version 2.0. See the [LICENSE](LICENSE) file for details.