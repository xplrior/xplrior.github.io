---
layout: default
---

# Remove Commit History

The below command will remove the commit history on the `main` branch.

```bash
git checkout --orphan newBranch && \
git add -A && \
git commit -m "initial commit" && \
git branch -D main && \
git branch -m main && \
git push -f origin main && \
git gc --aggressive --prune=all
```

---

[back](../til.md)
