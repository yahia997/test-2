# Task

## Part 1 — Creating Tags
1. Create an **annotated tag** called `v1.0` on your latest commit, with a message:
```bash
git tag -a v1.0 -m "First stable release"
```

2. Go back in your history and tag an **earlier commit** (pick any commit from before this phase — e.g. your very first commit) as `v0.1`, also annotated:
```bash
git log --oneline
git tag -a v0.1 -m "Initial version" <commit-hash>
```

3. Create a **lightweight tag** called `checkpoint` on your latest commit:
```bash
git tag checkpoint
```

## Part 2 — Sharing Tags
4. Push everything, including your tags — remember, tags don't get pushed automatically:
```bash
git push origin main
git push origin --tags
```

## Part 3 — Checking Out a Tag Safely
5. Create a new branch starting from `v0.1`, so you can explore that point in history without risking a detached HEAD:
```bash
git checkout -b from-v0.1 v0.1
```

6. Add a small file here to prove you branched from that point, then push the branch:
```bash
echo "exploring v0.1" > v0_1_notes.txt
git add v0_1_notes.txt
git commit -m "Add notes from v0.1 branch"
git push origin from-v0.1
```

7. Switch back to `main`:
```bash
git checkout main
```