---
layout: default
---

# Remove Local Branches

This will delete all local branches except `main`.

```bash
git branch | grep -v "main" | xargs git branch -D
```

---

[back](../til.md)
