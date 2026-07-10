# Task

## Part 1 — Viewing and Adding a Remote
1. Add the original class repository as a second remote, named `upstream`:
```bash
git remote add upstream https://github.com/yahia997/public
```

2. Save proof of your remotes to a file:
```bash
git remote -v > remotes_report.txt
```

## Part 2 — Fetching and Merging
3. Fetch the `upstream` remote (downloads its history, but doesn't touch your files yet):
```bash
git fetch upstream
```

4. Merge `upstream/main` into your own `main` branch:
```bash
git checkout main
git merge upstream/main -m "Merge upstream into main"
```
> If you get a conflict, resolve it by keeping your own version of any conflicting files, then run `git add <file>` and `git commit`.

## Part 3 — Pushing a New Branch
5. Create a new branch and push it to your own repo (`origin`):
```bash
git checkout -b remote-practice
echo "practicing with remotes" > remote_notes.txt
git add remote_notes.txt
git commit -m "Add remote practice notes"
git push origin remote-practice
```

6. Switch back to `main` and push everything:
```bash
git checkout main
git push origin main
```