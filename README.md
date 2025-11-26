# command-fix-issue

A Claude Code slash command for fixing bugs using TDD workflow.

## Installation

```bash
# Clone to your claude-commands directory
git clone git@github.com:claude-commands/command-fix-issue.git ~/projects/claude-commands/command-fix-issue

# Create symlink
ln -s ~/projects/claude-commands/command-fix-issue/fix-issue.md ~/.claude/commands/fix-issue.md
```

## Usage

```
/fix-issue 456
```

Where `456` is the GitHub issue number.

## What it does

1. Fetches issue details from GitHub
2. Explores codebase to identify root cause
3. Creates a fix branch (`fix/456-short-desc`)
4. Writes a failing test that reproduces the bug (Red)
5. Implements the minimal fix (Green)
6. Runs full test suite and linting
7. Creates a PR referencing the issue

## TDD Workflow

This command follows Test-Driven Development:
- **Red**: Write a test that fails, proving the bug exists
- **Green**: Write minimal code to make the test pass
- **Refactor**: Clean up if needed (optional)

## Requirements

- `gh` CLI installed and authenticated
- Git repository with GitHub remote
- Claude Code with Opus 4.5 model access

## Updates

```bash
cd ~/projects/claude-commands/command-fix-issue && git pull
```
