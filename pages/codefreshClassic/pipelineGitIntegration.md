---
layout: default
---

# Pipelines Associated with a Git Integration

Replace `GIT_INTEGRATION` with the name of the git integration in codefresh.

```bash
codefresh get pip -o json | jq --arg v "GIT_INTEGRATION" -r '.[] | select(contains({"spec":{"triggers":[{"type":"git", "context":$v}]}}) or contains({"spec":{"specTemplate":{"context":$v}}}) ) | .metadata.name'
```

---

[back](../til.md)
