---
layout: default
---

# Pipelines Associated with a Runtime Environment

Replace `RE_NAME` with your runtime information.

```bash
codefresh get pipelines -o json | jq '.[] | select(.spec.runtimeEnvironment.name=="RE_NAME") | .metadata.name'
```

---

[back](../til.md)
