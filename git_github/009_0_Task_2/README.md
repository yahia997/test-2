# Task
Let's put `.gitignore` into practice with a more realistic structure. You'll build a small file tree and write a `.gitignore` that handles several different cases at once.

### 1. Create this structure inside your repo
From the root of your repository:
```bash
mkdir -p build
touch build/output.o

touch TODO
touch git_github/TODO

touch debug.log
touch git_github/debug.log
touch lib.log

mkdir -p docs/server
touch docs/notes.txt
touch docs/server/arch.txt

mkdir -p assets/a/b/c
touch assets/a/z
touch assets/a/b/z
touch assets/a/b/c/z
```

### 2. Write a `.gitignore` in the repo root that does all of the following:
- Ignores the entire `build/` directory (and everything inside it)
- Ignores all `.log` files anywhere in the project — **except** `lib.log`, which should still be tracked
- Ignores the `TODO` file **only at the repo root** — `git_github/TODO` should NOT be ignored
- Ignores `docs/notes.txt`, but NOT `docs/server/arch.txt` (single-level glob, not recursive)
- Ignores every `z` file nested any number of levels under `assets/a/` — meaning `assets/a/z`, `assets/a/b/z`, and `assets/a/b/c/z` should all be ignored

> Hint: you'll need `*.log`, `!lib.log`, `/TODO`, `docs/*.txt`, `build/`, and a `**` pattern for the `assets` case. Revisit the rules above if you're stuck.

### 3. Verify with `git status`
Run `git status` and confirm:
- Only `lib.log`, `git_github/TODO`, `docs/server/arch.txt`, and `.gitignore` show up as untracked.
- Nothing from `build/`, `debug.log`, root `TODO`, `docs/notes.txt`, or `assets/` appears.

### 4. Stage, commit, and push
```bash
git add .gitignore lib.log git_github/TODO docs/server/arch.txt
git commit -m "Add gitignore with nested and anchored rules"
git push
```