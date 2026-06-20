# making llms work better

**Tip-001**

When Codex performs solution, architecture, or code reviews

Tell the LLM: 
```text
Are you 100% confident in this strategy? If not, identify all possible vulnerabilities, provide fixes, and repeat this cycle until you are truly 100% certain on a factual level.
```

**Tip-002**

You: If you're unhappy with Claude's responses or have run out of quota, give the following prompt a try.

Tell the LLM: 
```text
Based on our current conversation, please create a summary so that GPT can clearly understand.
```


**Tip-003**

When you need the AI to act as a senior engineer for self-review and architectural alignment.

Tell the LLM:

```text
Act as senior [stack] engineer. Follow our architecture in PROJECT.md. 
Are you 100% confident? Identify vulnerabilities and fix until certain.

```

**Tip-004**

Leverage user stories and edge cases to precisely define functional requirements; perfect for "stream of consciousness" inputs.

Tell the LLM:

```text
User story: User clicks X, expects Y. 
Edge cases: [List potential edge cases]. 
What could go wrong? Please analyze and implement.

```

**Tip-005**

Maximize output quality through model division of labor (e.g., Claude for logic, GPT for execution).

Tell the LLM:

```text
Review the current UI/UX logic and suggest refactoring. 
Apply a [playful/skeptical] vibe to the feedback before we implement the concrete code.

```

**Tip-006**

Establish a "plan-driven" loop to avoid crashes caused by generating large features all at once.

Tell the LLM:

```text
1. Load PRD and implementation plan context.
2. Breakdown into small tasks.
3. Suggest: approach -> plan -> implementation -> test -> commit.
4. What's the next logical step?

```

**Tip-007**

Manage context during long conversations to prevent logic drift caused by token limits.

Tell the LLM:

```text
/context (Check token usage)
/compact (When usage at 60-70%)
/clear (For unrelated tasks to keep the session clean)

```

**Tip-008**

For debugging workflows, require the AI to explain the root cause and prevent similar errors.

Tell the LLM:

```text
[Paste 5-10 lines of key error log]
Fix this, explain why it happened, and suggest prevention measures for the future.
If stuck, zoom out: what are the alternative approaches?

```

**Tip-009**

Adopt a Test-Driven Development (TDD) Vibe flow, utilizing an automated testing loop.

Tell the LLM:

```text
Before implementing the logic, generate comprehensive tests for this feature. 
Add tests for this specific edge case: [Edge Case]. 
Run tests after each edit.

```

**Tip-010**

Leverage Git checkpoints for recovery and refactoring during major breakdowns.

Tell the LLM:

```text
The current implementation is too messy. Let's revert to the last stable Git commit. 
Now, refactor this specific module with a cleaner structure based on the original plan.

```

**Tip-011**

Pre-launch security and production environment compliance checks.

Tell the LLM:

```text
Review this change for security vulnerabilities (keys, auth, validation). 
Ensure no stack traces are leaked and all user inputs are properly sanitized.

```

**Tip-012**

Adopt a strict "Testing Gate" flow to enforce quality control and prevent regression before feature implementation.

Tell the LLM:

```
Are you 100% confident in this phase implementation? Before writing any functional code, add or update tests that cover the phase capability. Run these phase tests first to ensure they catch the gaps, then implement the code, and finally run all tests again for regression validation.

```


***Tips13*

```
Reload the work log and compile a detailed daily task list

```







