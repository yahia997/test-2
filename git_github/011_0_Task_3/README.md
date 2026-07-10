# Task

## Part 1 — Removing Files

1. Completely remove `git_github/TODO` from your repo (both from disk and from Git):
```bash
git rm git_github/TODO
git commit -m "Remove TODO from git_github"
```

2. You've decided `lib.log` shouldn't have been tracked after all. Stop tracking it, but **keep the file on your disk**:
```bash
git rm --cached lib.log
```

3. Now make sure it doesn't get accidentally re-tracked in the future, by adding it to `.gitignore`:
```bash
echo "lib.log" >> .gitignore
git add .gitignore
git commit -m "Stop tracking lib.log"
```

## Part 2 — Moving and Renaming Files

4. Rename `git_github/a.txt` to `git_github/hello.txt` using `git mv`:
```bash
git mv git_github/a.txt git_github/hello.txt
git commit -m "Rename a.txt to hello.txt"
```

5. Run `git log --follow -- git_github/hello.txt` and check that Git still shows the history from before the rename — even though the file's name changed.

6. Push everything:
```bash
git push
```