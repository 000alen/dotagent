---
name: issue-delivery
description: Deliver an approved Linear engineering issue through an isolated Git worktree, implementation, repository-required verification, a GitHub pull request, and Linear review handoff.
---

# Issue delivery

Use this workflow when the user asks to implement or delegate a Linear issue.

1. Read the issue, comments, relations, and linked context before changing state.
2. Inspect repository instructions, branches, worktrees, and the requested base.
3. Assign the issue to the authenticated user and move it to `In Progress`.
4. Create an isolated worktree and issue branch from the requested base.
5. Implement the smallest complete solution while preserving unrelated state.
6. Run focused validation while iterating, then every check required by the
   repository contract.
7. Commit, push, and open a pull request against the requested base.
8. Link the pull request and verification summary in Linear, then move the issue
   to `In Review`. Do not mark it complete before merge.

Do not operate Docker, production systems, credentials, accounts, or destructive
resources without explicit authorization. If verification cannot run, report
the exact limitation rather than implying success.
