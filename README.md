# Kubernetes CLI Debug Operations
Lorem ipsum dolor.

--------------------------------------------------
## Get a List of Pods (`get pods`)

Use the `get pods` command to get a list of the default namespace’s pods.

```shell
kubectl get pods
```

To get a list of another namespace’s pods, use the `--namespace` or `-n` flag.

```shell
kubectl get pods --namespace=<namespace>
```

Where `<namespace>` is the namespace’s name.

To get a list of all namespace’s pods, use the `all-namespaces` or `-A` flag.

```shell
kubectl get pods --all-namespaces
```


--------------------------------------------------
## Print a Pod’s Logs (`logs`)

Use the `logs` command to print a pod’s logs.

```shell
kubectl logs <pod>
```

Where `<pod>` is the pods’s name.


--------------------------------------------------
## Execute a Command (`exec`)

Execute a command in a container in a pod.

```shell
kubectl exec <command>
```

Where `<command>` is the command’s name.

<!-- Add a reference to a list of commands. Maybe add a few common commands a user can use. -->

--------------------------------------------------
## Create a Debug Session (`debug`)

Create a debug session for a pod.

```shell
kubectl debug 
```


--------------------------------------------------