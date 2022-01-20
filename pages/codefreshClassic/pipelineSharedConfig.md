---
layout: default
---

# Pipelines Associated with a Shared Configuration

Replace `CONTEXT_NAME` with the name of the shared configuration.

```bash
codefresh get pip -o json | jq -r '.[] | select(contains({"spec":{"contexts":["CONTEXT_NAME"]}}) )  | .metadata.name' 
```

---

[back](../til.md)
