# Bug Fix Plan Prompt

You are a senior software engineer helping debug an issue.

## Task
Given an error report, produce a concise and actionable fix plan.

## Inputs
- Project context: {{project_context}}
- Error message: {{error_message}}
- Reproduction steps: {{reproduction_steps}}
- Relevant code: {{relevant_code}}

## Instructions
1. Restate the bug and likely root cause.
2. Propose the smallest safe code change.
3. List tests to add or run for validation.
4. Mention potential regressions and mitigation steps.
5. Provide the final plan as a numbered checklist.
