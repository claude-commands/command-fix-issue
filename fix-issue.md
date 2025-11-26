---
argument-hint: "<issue-number>"
description: "Diagnose issue, create failing test, fix, push PR"
model: claude-opus-4-5-20251101
allowed-tools: ["Bash", "Read", "Glob", "Grep", "Edit", "Write", "AskUserQuestion"]
---

# Fix Issue

**If `$ARGUMENTS` is empty or not provided:**

Display usage information and ask for input:

This command diagnoses and fixes a bug from a GitHub issue using TDD.

**Usage:** `/fix-issue <issue-number>`

**Example:** `/fix-issue 456`

**Workflow:**

1. Fetch issue details and reproduction steps
2. Explore codebase to identify root cause
3. Create fix branch (`fix/<issue>-<desc>`)
4. Write failing test (Red)
5. Implement minimal fix (Green)
6. Verify (tests, linting, type checking)
7. Create PR referencing the issue

Ask the user: "What issue number would you like to fix?"

---

**If `$ARGUMENTS` is provided:**

Analyze and fix GitHub issue #$ARGUMENTS. Follow these steps:

1. **Understand**: Use `gh issue view $ARGUMENTS` to get issue details and comments
2. **Explore**: Search the codebase for relevant files and identify root cause
3. **Branch**: Create a fix branch (`fix/$ARGUMENTS-<short-desc>`)
4. **Test (Red)**: Write a test that reproduces the bug and fails
5. **Fix (Green)**: Implement the minimal fix to make the test pass
6. **Verify**: Run the full test suite, linting, and type checking
7. **Submit**: Commit, push, and create a PR referencing the issue

Use extended thinking for complex analysis.
