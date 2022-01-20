---
layout: default
---

# Kubectl Commands

## PODS

```bash
kubectl describe pods <POD_NAME>
kubectl get pods --all-namespaces --output wide
kubectl get pods <POD_NAME> --output yaml
kubectl logs <POD_NAME> --all-containers=true
kubectl logs <POD_NAME> -c <CONTAINER_NAME>
kubectl logs <POD_NAME>
kubectl logs <POD_NAME> --previous
kubectl get --raw /apis/metrics.k8s.io/v1beta1/namespaces/<Name Space>/pods/<POD_NAME>
```

## NODES

```bash
kubectl describe nodes <NODE_NAME>
kubectl get nodes --output wide
kubectl get nodes <NODE_NAME> --output yaml
```

Get Instance ID, DNS Name, Kernel Version, Container Runtime Version, Kublet Version, and Kube Proxy Version

```bash
kubectl get nodes --output jsonpath="{range .items[]}{'\nNODE INFORMATION: \n\t INSTANCE INFO: '}{...spec.providerID}{'\n\t INTERNAL DNS: '}{..metadata.name}{'\n\t KERNEL VERSION: '}{..status.nodeInfo.kernelVersion}{'\n\t CONTAINER RUNTIME VERSION: '}{..status.nodeInfo.containerRuntimeVersion}{'\n\t KUBELET VERSION: '}{..status.nodeInfo.kubeletVersion}{'\n\t KUBE PROXY VERSION: '}{..status.nodeInfo.kubeProxyVersion}{'\n\n'}{end}"
```

The Following will require JQ to be installed but is the same as above

```bash
kubectl get nodes --output json | jq '.items[] | {instanceInfo: .spec.providerID, internalDns: .metadata.name, nodeInfo:{kubeletVersion: .status.nodeInfo.kubeletVersion, kubeProxyVersion: .status.nodeInfo.kubeProxyVersion, kernelVersion: .status.nodeInfo.kernelVersion, containerRuntimeVersion: .status.nodeInfo.containerRuntimeVersion}}'
```

## DEPLOYMENTS

```bash
kubectl describe deployments <DEPLOY_NAME>
kubectl get deployments --all-namespaces --output wide
kubectl logs deployment/<DEPLOY_NAME>
```

## DAEMONSETS

```bash
kubectl describe daemonsets <DS_NAME>
kubectl get daemonsets --all-namespaces --output wide
```

## REPLICASETS

```bash
kubectl describe replicasets <RS_NAME_>
kubectl get replicasets --all-namespaces --output wide
```

## SERVICES

```bash
kubectl describe services <SVC_NAME_>
kubectl get services --all-namespaces --output wide
```

## SERVICEACCOUNTS

```bash
kubectl describe serviceaccounts <SA_NAME>
kubectl get serviceaccounts --all-namespaces --output wide
```

## OTHER

```bash
kubectl get --namespace kube-system configmap/aws-auth --output yaml
kubectl exec --namespace <NAMESPACE> -it <POD_NAME> -- /bin/bash
kubectl api-resources --output wide
kubectl get all --all-namespaces --output wide
kubectl get all --all-namespaces --output yaml
kubectl apply -f <FILE_PATH>
```

---

[back](../til.md)
