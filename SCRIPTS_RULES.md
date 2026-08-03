SCRIPTS_RULES

Purpose

This document collects repository-wide rules, examples, and guidance that contributors and reviewers should follow. It is intended to be the canonical place for simple conventions (commit messages, PR checklist items, and other small policies). Keep entries short and example-driven so contributors can follow them quickly.

Commit message rules (enforced by .gitlint)

Subject format
- Required format: <component>: <short description>
  - component: file/module/area impacted (alphanum, underscore, dash, slash, dot)
  - short description: imperative mood, brief, <= 72 characters
- Example good:
  - py-scripts/lf_wifi_capacity_test.py: Add support to load existing test config
  - ci: Run PR review only on changed files to reduce duplicate runs
- Example bad:
  - fixup something wrong
  - typo

Body rules
- If a body is present, leave a blank line after the subject
- Wrap body lines at ~72 chars for readability

How to fix when gitlint/reviewdog flags your commit message
1. Amend your local commit: git commit --amend
2. Edit the subject to match the "<component>: <short description>" format
3. Push back to the branch: git push --force-with-lease

Local tooling (pre-commit)
- We provide a pre-commit hook that runs gitlint locally (see .pre-commit-config.yaml). To enable locally:
  - pip install pre-commit gitlint
  - pre-commit install
  - (Optional) pre-commit run --all-files

CI enforcement
- PRs are checked by the pr-review workflow: it runs gitlint (config .gitlint) and reports results via reviewdog.

Extending rules
- This file is intended to grow. For new conventions (PR checklist items, file headers, style snippets), add a short section with examples.
- For machine-enforced rules, add corresponding config files (.gitlint, .flake8, .pylintrc) and update the CI workflow to use them.

Feedback
- If a rule is too strict or noisy, propose changes in a PR that updates this file and the corresponding config.
