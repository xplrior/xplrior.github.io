---
layout: default
---

# Pipelines Triggers Associated with a Git Repository

Replace `REPO_OWNER/REPO_NAME` with your repository information.

```bash
codefresh get pip -o json | jq -r '.[] | select(.spec.triggers[].repo=="REPO_OWNER/REPO_NAME") | .metadata.name'
```

---

[back](../til.md)
