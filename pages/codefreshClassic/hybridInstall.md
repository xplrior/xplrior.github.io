---
layout: default
---

# Hybrid Installation

This will install the Hybrid Runner via the CLI without any prompts.  Also skips cluster integration and test.

```bash
codefresh runner init --skip-cluster-integration --skip-cluster-test  --set-default-runtime false --exec-demo-pipeline false --name lukas-agent --kube-namespace codefresh --kube-context-name $(kubectl config current-context) --runtime-name lukas-runtime
```

---

[back](../til.md)
