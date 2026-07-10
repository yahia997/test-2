# Task

## Part 1 — Amending a Commit
1. Create a new file with a deliberate typo in the commit message:
```bash
echo "first draft" > amend_target.txt
git add amend_target.txt
git commit -m "Add amend target fiel"
```

2. You just noticed the typo (**"fiel"**) — and you also forgot to include a second file. Fix both using `--amend`, without creating a new commit:
```bash
echo "supporting notes" > amend_notes.txt
git add amend_notes.txt amend_target.txt
git commit --amend -m "Add amend target file"
```

3. Push your changes:
```bash
git push
```

## Part 2 — Unstaging a File
4. Make two changes at once: edit `git_github/hello.txt`, and create a new file `scratch.txt`:
```bash
echo "another update" >> git_github/hello.txt
echo "temporary notes, not ready yet" > scratch.txt
git add git_github/hello.txt scratch.txt
```

5. On second thought, `scratch.txt` isn't ready to be committed yet. Unstage it — but keep your edits:
```bash
git restore --staged scratch.txt
```

6. Commit only `hello.txt`:
```bash
git commit -m "Another update to hello.txt"
```

7. Now that `scratch.txt` is ready, stage and commit it separately, then push everything:
```bash
git add scratch.txt
git commit -m "Add scratch notes"
git push
```

## Part 3 — Discarding Changes
8. Make an edit you don't actually want to keep:
```bash
echo "THIS IS A MISTAKE AND SHOULD NOT BE COMMITTED" >> git_github/hello.txt
```

9. Discard it completely:
```bash
git restore git_github/hello.txt
```

10. Confirm the file is back to how it was:
```bash
git status
```
It should show a clean working tree — no pending changes. Push if anything else is pending:
```bash
git push
```