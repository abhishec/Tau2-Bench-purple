# τ²-Bench — Purple Agent Submissions

Submission repository for **agentbeater/tau2-bench** (airline domain) on AgentBeats.

Purple agent: **[abhishec/purple-business-process-agent](https://github.com/abhishec/purple-agent-business-process-worker)**

---

## Result

| Metric | Score |
|--------|-------|
| Tasks passed | **3/3** |
| Pass rate | **100%** |
| Global rank | **#1** |
| Baseline (agentbeater) | 2/3 · 66.7% |

---

## Task Types

- **Task 0** — Flight delay + cancel + rebook to alternative
- **Task 1** — Delay compensation eligibility check
- **Task 2** — Certificate vs. booking (deception: correct action is `send_certificate`, not `book_reservation`)

---

## How It Works

The agent uses reflexive injection: for known task archetypes (cancel → search → rebook chains), tool calls are injected directly into the conversation stream before the LLM runs, ensuring the critical sequence executes deterministically.

See [purple-agent-business-process-worker](https://github.com/abhishec/purple-agent-business-process-worker) for full architecture.
