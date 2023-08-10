# Kubernetes CLI Debug Operations
Lorem ipsum dolor.

- [Get a List of Pods](#get-a-list-of-pods)
- [Print a Pod’s Logs](#print-a-pods-logs)
- [Execute a Command](#execute-a-command)
- [Create a Debug Session](#create-a-debug-session)


## Get a List of Pods

Use the `get pods` command to get a list of the default namespace’s pods:

```shell
kubectl get pods
```

To get a list of another namespace’s pods, use the `--namespace` or `-n` flag:

```shell
kubectl get pods --namespace=<namespace> # replace <namespace> with the namespace’s name
```

To get a list of all namespace’s pods, use the `all-namespaces` or `-A` flag:

```shell
kubectl get pods --all-namespaces
```


--------------------------------------------------
## Print a Pod’s Logs

Use the `logs` command to print a pod’s logs:

```shell
kubectl logs <pod> # replace <pod> with the pod’s name
```


--------------------------------------------------
## Execute a Command

Execute a command in a container in a pod:

```shell
kubectl exec <command> # replace <command> with the command’s name
```

<!-- Add a reference to a list of commands. Maybe add a few common commands a user can use. -->

--------------------------------------------------
## Create a Debug Session

Create a debug session for a pod.

```shell
kubectl debug 
```


--------------------------------------------------