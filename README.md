# Use Kubernetes CLI to Debug Your Cluster
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

```shell
NAME       READY   STATUS      RESTARTS   AGE
node-pod   1/1     Completed   0          5h10m
```

To get a list of another namespace’s pods, use the `--namespace` or `-n` flag:

```shell
kubectl get pods --namespace=<namespace> # replace <namespace> with the namespace’s name
```

```shell
NAME            READY   STATUS    RESTARTS   AGE
postgres-db     1/1     Running   0          14d
```

To get a list of all namespace’s pods, use the `all-namespaces` or `-A` flag:

```shell
kubectl get pods --all-namespaces
```

```shell
NAMESPACE            NAME                                         READY   STATUS      RESTARTS   AGE
default              node-pod                                     0/1     Completed   0          64s
js                   node-pod                                     0/1     Completed   0          3m
kube-system          coredns-5d78c9869d-h8x5b                     1/1     Running     0          9h
kube-system          coredns-5d78c9869d-v6rm6                     1/1     Running     0          9h
kube-system          etcd-kind-control-plane                      1/1     Running     0          9h
kube-system          kindnet-sr7z2                                1/1     Running     0          9h
kube-system          kube-apiserver-kind-control-plane            1/1     Running     0          9h
kube-system          kube-controller-manager-kind-control-plane   1/1     Running     0          9h
kube-system          kube-proxy-966bh                             1/1     Running     0          9h
kube-system          kube-scheduler-kind-control-plane            1/1     Running     0          9h
local-path-storage   local-path-provisioner-6bc4bddd6b-68brg      1/1     Running     0          9h
database             postgres-db                                  1/1     Running     0          7d
```


## Print a Pod’s Logs
Use the `logs` command to print a pod’s logs:

```shell
kubectl logs <pod> # replace <pod> with the pod’s name
```

```shell
Starting development server...
Server running on http://localhost:3000
Building pages...
Built page: /
```

## Execute a Command
Execute a command in a container in a pod:

```shell
kubectl exec <command> # replace <command> with the command’s name
```

<!-- Add a reference to a list of commands. Maybe add a few common commands a user can use. -->


## Create a Debug Session
Create a debug session for a pod.

```shell
kubectl debug 
```
