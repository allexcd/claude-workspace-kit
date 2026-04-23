---
name: subagent-strategy
description: Subagent delegation strategy. Use when tasks involve research, exploration, or parallel analysis that would clutter the main context window.
allowed-tools: Agent, Read
---

# Subagent Strategy

Implements **§2 Subagent Strategy** from `docs/workflow/workflow-orchestration.md`.

## When to Delegate to a Subagent
- Research or exploration tasks (codebase analysis, dependency investigation)
- Parallel analysis that would bloat the main context
- Complex problems that benefit from focused, isolated reasoning
- Any task that can be expressed as a single, well-defined objective

## Available Agents
- **deep-reviewer** — architecture and quality review, edge case validation (model: opus)
- **fast-implementer** — execute an approved plan with minimal diff (model: sonnet)
- **Explore** — read-only codebase exploration and Q&A (safe to run in parallel)
- **general-purpose** — open-ended research and multi-step tasks

Dispatch via the Agent tool with `subagent_type` set to the agent name.

## Workflow
1. Identify whether the task (or sub-task) can be isolated
2. Write a clear, self-contained prompt with all necessary context
3. Specify exactly what the subagent should return
4. Dispatch to the appropriate agent via the Agent tool
5. Integrate the subagent's result into the main task

## Rules
- Use subagents liberally to keep the main context window clean
- One task per subagent for focused execution
- For complex problems, throw more compute at it via subagents
- Offload research, exploration, and parallel analysis to subagents
- The subagent prompt must be self-contained — it has no shared state
- Run independent subagents in parallel (single message, multiple Agent calls)
