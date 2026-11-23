---
name: gh-address-comments
description: |
  Help address review/issue comments on the open GitHub PR for the current
  branch using gh CLI; verify gh auth first and prompt the user to
  authenticate if not logged in.
triggers:
  - "gh address comments"
  - "gh-address-comments"
od:
  mode: design-system
  category: general
  upstream: "https://github.com/openai/skills/tree/HEAD/skills/.curated/gh-address-comments"
  license: "Apache-2.0"
---
> Vendored from [openai/skills](https://github.com/openai/skills/tree/HEAD/skills/.curated/gh-address-comments) under Apache-2.0. Only the frontmatter was normalized for OpenDesign; the instructions below are upstream's.

# PR Comment Handler

Guide to find the open PR for the current branch and address its comments with gh CLI. Run all `gh` commands with elevated network access.

Prereq: ensure `gh` is authenticated (for example, run `gh auth login` once), then run `gh auth status` with escalated permissions (include workflow/repo scopes) so `gh` commands succeed. If sandboxing blocks `gh auth status`, rerun it with `sandbox_permissions=require_escalated`.

## 1) Inspect comments needing attention
- Run scripts/fetch_comments.py which will print out all the comments and review threads on the PR

## 2) Ask the user for clarification
- Number all the review threads and comments and provide a short summary of what would be required to apply a fix for it
- Ask the user which numbered comments should be addressed

## 3) If user chooses comments
- Apply fixes for the selected comments

Notes:
- If gh hits auth/rate issues mid-run, prompt the user to re-authenticate with `gh auth login`, then retry.
