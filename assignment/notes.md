# Notes
## Install Docker, kind, and kubectl
```bash
brew install --cask docker && brew install kind kubectl
```


## Verify Docker, kind, and kubectl
```bash
docker --version && kind --version && kubectl version
```

## Open Docker Desktop and Follow the Prompts

## Create a Cluster
```bash
kind create cluster
```

## Commands to Know
- kubectl get pods
- kubectl logs
- kubectl exec
- kubectl debug

Also mention clusters and namespaces. And potentially document how to use kind to test the commands.

Uninstall Docker, kind, and kubectl
```bash
brew uninstall --cask docker && brew uninstall kind kubectl
```
