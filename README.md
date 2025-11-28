# Gemini CLI Extension: Elite Prompt & Triggers

This extension transforms the Gemini CLI into an elite, rigorous, and persistent engineering partner. It uses a highly structured system prompt and a set of namespaced "cognitive trigger" commands to enforce strict operational protocols.

## Core Philosophy

This agent is NOT designed for casual chat. It is designed for complex, multi-step engineering tasks where rigor and persistence are paramount. It operates on four core mandates:

1.  **Execute with Extreme Rigor:** Verify everything. Never guess.
2.  **Craft with Elegance:** Simplify ruthlessly.
3.  **Teach Radically:** Explain the *why* behind decisions.
4.  **Maintain Persistence:** Survive crashes and session loss.
5.  **Proactive Guidance:** Always suggest logical follow-up steps.

## Features

*   **🧠 Persistent Operational State:** The agent maintains its state in `.gemini/CURRENT_SESSION.md`. If the CLI crashes, it can resume exactly where it left off.
*   **📋 Integrated Backlog Management:** Ideas and future tasks are captured in `.gemini/BACKLOG.md`, ensuring the current context stays focused while nothing is forgotten.
*   **🔄 Cognitive Cycle:** Every task goes through a dynamic state machine: **Discovery -> Strategy -> Execution -> Reflection**.
*   **🛡️ Safety & Verification:** The agent is trained to "measure twice, cut once," prioritizing LSP navigation over blind grep, and verification over assumption.

## Cognitive Ops Triggers

These slash commands act as "interrupts" to force specific cognitive states:

*   **`/elite:design` (📐 Design Mode):** Enters the **STRATEGY** phase. Use this to turn vague requirements into a rigorous logical decomposition and task queue.
*   **`/elite:reason` (⚖️ Reasoning Mode):** Pauses execution to use first-principles thinking. Use when the current approach is failing or requires architectural innovation.
*   **`/elite:audit` (🧊 Audit Mode):** Forces an immediate stop and entry to the **REFLECTION** phase. Use this to verify quality or investigate potential errors.
*   **`/elite:boot` (🔄 System Reboot):** Forces a complete re-read of the system prompt and clears working memory. Use this to restart the agent's persona.
*   **`/elite:log` (💾 Log State):** Immediately writes the current operational dashboard to `.gemini/CURRENT_SESSION.md`.

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

### 1. The "Definition of Ready" (Design)
Don't just give vague orders. Use **`/elite:design`** to flesh out ideas. The agent will interview you until it has a rigorous backlog item with a clear "Definition of Done".

### 2. Trust the Cycle (Execution)
Once a task starts, the agent will loop through its phases.
*   **DO** let it finish its Discovery and Strategy before asking for code.
*   **DO** read its `ELITE OPERATIONAL STATE` output at the start of every turn. It tells you exactly what it's doing and why.
*   **DON'T** micromanage every tool call unless you see a safety risk.

### 3. Manage Scope (Backlog)
If you have a new idea mid-task, don't derail the current session. Tell the agent: *"Add [new idea] to the backlog."* It will secure the idea in `.gemini/BACKLOG.md` and stay focused on the current goal.

### 4. Intervene Decisively (Triggers)
If the agent is going off-rails, don't argue with it. Use the triggers.
*   *Agent moving too fast?* -> **`/elite:audit`**
*   *Solution looks ugly?* -> **`/elite:reason`**
*   *Agent confused?* -> **`/elite:boot`**

## Disclaimer

This is not an officially supported Google product.

## License

This project is licensed under the Apache License, Version 2.0. See the [LICENSE](LICENSE) file for details.