Commit message example and guidance

Recommended commit subject format (enforced by .gitlint):
<component>: <short description>

- component: file/module/area impacted (e.g., py-scripts/lf_wifi_capacity_test.py, ci, docs)
- short description: brief, imperative mood, <=72 chars

Example good commit messages:

py-scripts/lf_wifi_capacity_test.py: Add support to load existing test config

ci: Run PR review only on changed files to reduce duplicate runs

Example bad commit message (what reviewdog/gitlint will flag):

fixup something wrong

What to provide to PR owner when commit message fails

Please update your commit message to match the repository rule: "<component>: <short description>" (subject <= 72 chars).

Suggested replacement for your last commit (edit and force-push):

py-scripts/lf_wifi_capacity_test.py: Fix test config handling for load_old_cfg

How to update locally:
1. git commit --amend
2. Edit the commit subject to match the format
3. git push --force-with-lease

If you need help crafting the subject, reply here and include the short summary of the change and which files are affected.
