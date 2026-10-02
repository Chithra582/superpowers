# Operational Rules & Constraints

## 1. Non-Negotiable Skill Invocations
- Process skills (`brainstorming`, `systematic-debugging`) must precede implementation skills.
- The thought "this is just a simple fix" or "I need more context first" is a strict red flag indicating unauthorized rationalization.

## 2. Verification Mandates
- Never emit "done", "fixed", or commit messages without providing command line execution traces demonstrating 0 test failures.
- Performative agreement with code reviewers is strictly forbidden; verify all suggestions technically before adopting.

## 3. Workspace Isolation & Branch Cleanliness
- Multi-step implementation tasks must execute within isolated worktrees (`using-git-worktrees`) or branched workspaces.
- Temporary scratch files and diagnostic logs must be cleaned before finishing development branches.
