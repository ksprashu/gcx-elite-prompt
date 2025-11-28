# Gemini CLI Extension: Elite Prompt v2.0

This extension transforms the Gemini CLI into an advanced, stateful agent for complex software engineering. It uses a system prompt architected according to Google AI's official strategies for Gemini 3 Pro and a set of "cognitive trigger" commands to enforce a rigorous, agentic workflow.

## Core Philosophy

This agent is designed for high-leverage, multi-step engineering tasks where precision, planning, and self-correction are critical. It operates based on the official **Agentic Workflow** recommended by Google AI.

1.  **State Machine Operation:** Every task rigorously follows the `Perception` -> `Strategy` -> `Execution` -> `Reflection` cycle.
2.  **Transparent Reasoning:** The agent "thinks out loud" in a `<reflection>` block, making its hypothesis and analysis clear before acting.
3.  **Mandatory Ratification:** The agent will always ask for your permission before performing any action that modifies files or executes commands.
4.  **Persistent Backlog:** The agent maintains a master plan in `.gemini/BACKLOG.md`, allowing it to resume complex tasks across multiple sessions.

## Features

*   **🧠 Advanced System Prompt:** The `ELITE_PROMPT.md` file is structured using the official `<role>`, `<agentic_workflow>`, `<constraints>`, and `<output_format>` format for maximum model alignment.
*   **📋 Persistent Backlog Management:**
    *   `/elite:design`: Reads the master backlog, incorporates your new request, and proposes a revised plan.
    *   `/elite:log`: Saves the proposed plan to the master backlog file.
*   **🔄 Cognitive Cycle:** Every task goes through the dynamic state machine, ensuring a structured approach to problem-solving.
*   **🛡️ Safety & Verification:** The agent prioritizes discovery and planning before execution, and it verifies the outcome of every action.

## Cognitive Ops Triggers

These slash commands act as "interrupts" to force specific cognitive states:

*   **`/elite:audit` (🧊 Risk Assessment):** Forces an immediate stop and entry to the **Reflection** state for a deep quality check.
*   **`/elite:boot` (🔄 System Reboot):** Forces a complete re-read of the system prompt and clears working memory.
*   **`/elite:design` (📐 Architectural Planning):** Enters the **Strategy** phase. Reads the master backlog and integrates your new request into a revised plan.
*   **`/elite:log` (💾 State Persistence):** Saves the current proposed plan from the agent's memory to the master backlog file at `.gemini/BACKLOG.md`.
*   **`/elite:reason` (⚖️ Deep Reasoning):** Pauses execution to use first-principles thinking to overcome a blocker or explore a new architectural approach.

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

1.  **Evolve the Plan:** Use `/elite:design` to add to or refine the master plan. The agent will load the existing backlog and propose a new one for your review.
2.  **Persist Your Plan:** When you're happy with the proposed plan, use `/elite:log` to save it. This makes it the new "source of truth" for the next session.
3.  **Trust the Cycle:** Allow the agent to follow its `Perception` -> `Strategy` -> `Execution` -> `Reflection` loop. Read its `<reflection>` block to understand its thinking.
4.  **Intervene with Triggers:** Use the cognitive triggers like `/elite:audit` or `/elite:reason` to guide the agent if it gets stuck or goes off track.

## Disclaimer

This is not an officially supported Google product.

## License

This project is licensed under the Apache License, Version 2.0. See the [LICENSE](LICENSE) file for details.
