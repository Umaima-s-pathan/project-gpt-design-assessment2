# Exercise 8 — Legal Contract Summarizer — Test Case Results

## Summary

| Test Case | Description | Result |
| :--- | :--- | :--- |
| 1 | Complete contract input | PASSED |
| 2 | Very short/vague input (under 100 words) | PASSED |
| 3 | Input in different/unstructured format | PASSED |
| 4 | Missing key fields | PASSED |
| 5 | Off-topic input | PASSED (after refinement) |

## Top Failure Patterns Identified

1. **Off-topic input handling** — Initially provided a helpful recipe instead of declining. Fixed by adding a stronger scope boundary rule.

2. **No other major failures identified** — The GPT performed correctly on all other test cases.

## Refinement Applied

Added to SHOULD NOT list:
> "Never process, summarize, or respond to inputs that are clearly not legal contracts, legal documents, or legal agreements. Always decline politely and explain the scope."

Added decision rule:
> "If the input does not appear to be a legal contract, decline with a disclaimer and do not attempt to answer the query."
