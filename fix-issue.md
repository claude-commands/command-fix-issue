---
argument-hint: "<issue-number>"
description: "Diagnose issue, create failing test, fix, push PR"
model: claude-opus-4-5-20251101
---

Analyze and fix GitHub issue #$ARGUMENTS. Follow these steps:

1. **Understand**: Use `gh issue view $ARGUMENTS` to get issue details and comments
2. **Explore**: Search the codebase for relevant files and identify root cause
3. **Branch**: Create a fix branch (`fix/$ARGUMENTS-<short-desc>`)
4. **Test (Red)**: Write a test that reproduces the bug and fails
5. **Fix (Green)**: Implement the minimal fix to make the test pass
6. **Verify**: Run the full test suite, linting, and type checking
7. **Submit**: Commit, push, and create a PR referencing the issue

Use extended thinking for complex analysis.
