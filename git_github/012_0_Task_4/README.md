# Task

## Part 1 — Generate some history to look at
Make three small commits so you have something real to inspect:

```bash
echo "step one" >> git_github/hello.txt
git add git_github/hello.txt
git commit -m "Update hello with step one"

echo "step two" >> git_github/hello.txt
git add git_github/hello.txt
git commit -m "Update hello with step two"

echo "fix typo in hello" >> git_github/hello.txt
git add git_github/hello.txt
git commit -m "Fix typo in hello.txt"
```

## Part 2 — Query the history
Create a folder called `log_reports` in your repo root, and generate three files inside it using the flags from this guide.

1. Save a condensed view of your **last 3 commits** to `log_reports/last_three.txt`:
```bash
mkdir -p log_reports
git log --oneline -3 > log_reports/last_three.txt
```

2. Save every commit whose message mentions **"fix"** to `log_reports/fix_commits.txt`:
```bash
git log --oneline --grep="fix" > log_reports/fix_commits.txt
```

3. Save the full history of `git_github/hello.txt` (its file-specific log) to `log_reports/hello_history.txt`:
```bash
git log --oneline -- git_github/hello.txt > log_reports/hello_history.txt
```

> Take a moment to open each file and compare it against what you'd expect — this is the same output `git log` would show you directly, just saved for reference.

## Part 3 — Commit and push
```bash
git add log_reports
git commit -m "Add log reports"
git push
```