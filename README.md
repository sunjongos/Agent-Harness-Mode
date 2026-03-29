<h1 align="center">Harness Mode (Agent Evaluation Framework)</h1>

<p align="center">
  <strong>The Ultimate Self-Improving, Evaluator-Driven Harness for Autonomous AI Agents</strong>
</p>

## 🚀 Overview

**Harness Mode** is a state-of-the-art framework crafted to solve the biggest problem with autonomous AI agents: **Hallucination and lazy code verification.** 

Instead of letting an agent write code and "guess" it works, Harness Mode enforces a strict, multi-persona lifecycle (Orchestrator -> Planner -> Generator -> Evaluator -> Evolver) with an absolute **Evaluation Rubric Board (평가기준표)**. Before any task starts, the agent is forced to define strict test criteria. The code is then empirically tested against this rubric in a continuous feedback loop.

## 🌟 Key Features

### 1. 🛡️ Protective Orchestrator & Rollback
Before an agent touches the codebase, a snapshot (`git stash` / commit) is taken. If the agent hits its maximum failure limit (Max Loop), it immediately reverts to the clean state. No more broken codebases!

### 2. 📋 The Evaluation Rubric (평가기준표)
The Planner generates a strict Markdown table of required items and terminal test commands. The Evaluator *must* execute these commands and stamp a `PASS` or `FAIL`. "Eyeballing" the code is completely banned.

### 3. 🤔 Context Compressor (토큰 최적화)
When an agent fails a script run and gets a 300-line error trace, throwing it back into the loop destroys context quality. Our Orchestrator compresses massive errors into a "3-line Root Cause Summary" before handing it back to the Generator.

### 4. 🧬 Evolver (자가 발전 시스템)
Once the loop finally succeeds, the agent analyzes its own mistakes and permanently records the "Lessons Learned" into `.agent/memory/lessons.md`. The agent gets intrinsically smarter the more you use it.

### 5. ⚖️ Dispute Escalation (중재 요청)
If the agent loops with the exact same error 2+ times, it halts and pings the human developer (The Supreme Court / Escalation) asking for technical direction, avoiding endless token burning.

## 🛠️ Installation & Usage

1. Copy the `SKILL.md` file into your agent's skill directory (e.g., `.agent/skills/harness-mode/SKILL.md`).
2. Add the workflow file `harness_mode.md` to `.agent/workflows/`.
3. In your prompt or chat UI, simply type:
   ```bash
   /harness_mode [Your complex task instruction here]
   ```
4. Watch the agent analyze task difficulty, build a rubric, and vigorously test its own code!

## 📜 Example Run Flow

1. **Orchestrator**: Evaluates difficulty (e.g., Complex -> Max Loops: 5). Backs up the code.
2. **Planner**: Prints out the Evaluation Rubric table.
3. **Generator**: Writes the code.
4. **Evaluator**: Runs `npm test` or `python main.py`. Marks `FAIL` in the table.
5. **Context Compressor**: Summarizes the failure.
6. **Generator**: Fixes the 3-line cause.
7. **Evaluator**: Marks `PASS`.
8. **Evolver**: Writes the debugging knowledge to `lessons.md`.
9. **GitHub Operator (Optional)**: Automatically pushes and creates a PR.

---
*Built with ❤️ for Agents that need higher standards.*
