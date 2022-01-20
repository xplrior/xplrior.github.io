---
layout: default
---

# Terminate All Builds for a Single Pipeline

This will terminate All builds for a specifc pipeline. Replace `PROJECTNAME/PIPELINENAME` with the pipeline of choice.

```bash
#!/bin/env bash
for item in $(codefresh get builds --status=running --pipeline-name PROJECTNAME/PIPELINENAME -o id)
  do
    codefresh terminate $item || true
  done 
```

---

[back](../til.md)
