# Task

## Part 1 — Unstaged Changes
1. Make an edit to `git_github/hello.txt` (don't stage it yet):
```bash
echo "a brand new unstaged line" >> git_github/hello.txt
```

2. Save the output of `git diff` (unstaged changes) to a file:
```bash
git diff > diff_reports/unstaged.diff
```
> If `diff_reports` doesn't exist yet, create it first: `mkdir -p diff_reports`

## Part 2 — Staged Changes
3. Now stage that same change:
```bash
git add git_github/hello.txt
```

4. Save the output of `git diff --staged` to a separate file:
```bash
git diff --staged > diff_reports/staged.diff
```

5. Notice `diff_reports/unstaged.diff` still shows the change (it was captured *before* staging), but if you ran plain `git diff` again right now, it would show nothing — because the change has moved from "unstaged" to "staged." Confirm this:
```bash
git diff
```
This should print nothing, since there are no unstaged changes left.

## Part 3 — Commit and Push
6. Commit your actual change to `hello.txt`, along with both diff report files:
```bash
git add diff_reports
git commit -m "Add diff reports and update hello.txt"
git push
```