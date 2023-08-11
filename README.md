# Use Kubernetes CLI to Debug Pods In Your Cluster
- Kubernetes and Kubernetes CLI overview.
- `get pods`, `logs`, `exec` overview. Cover recommended order.
- `debug` overview. Mention this is another option.


Kubernetes contains several commands, sometimes we can use these commands to do things. A good command to know is kubectl get pods which is used to get a list of all pods that are available and what their status is. Just rememember that when you use this command tat you may have to specify the `namespace`.

Speaking of commands, kubectl is the CLI that is used to interact with k8s. The kubectl cli commmunicates with the kubernettes API server.  Another command that is helpful is the kubectl logs command. In Azure, kubernetess is available, just like other cloud providers. This command is used to retrive the logs of a specific pod - do use this when you have to review logs or need to debug a container. Another we will dicuss is the `kubectl exec` command. A command that we can use to debug a container from the inside or to explore the the enviroment of the container itself.  I recommend when debugging you start with kubectl get pods, then `kubectl logs` and lastly we can use `kubectl exec` to explore the inside of the container and review other log files or configurations. 

**Note:** The command `kubectl debug` is another option to considering when debugging a container. This command can be used to create a clone of a pod that does not terminate if an error is experienced inside the container.

## Table of Contents
- [Get a List of Pods](#get-a-list-of-pods)
- [Print a Pod’s Logs](#print-a-pods-logs)
- [Execute a Command](#execute-a-command)
- [Create a Debug Session](#create-a-debug-session)
- [Learn More](#learn-more)


## Get a List of Pods
Use the `get pods` command to get a list of the default namespace’s pods:

```shell
kubectl get pods
```

```shell
NAME       READY   STATUS      RESTARTS   AGE
node-pod   1/1     Completed   0          5h10m
```

To get a list of another namespace’s pods, use the `--namespace` (or `-n`) flag:

```shell
kubectl get pods --namespace=<namespace> # replace <namespace> with the namespace’s name
```

```shell
NAME            READY   STATUS    RESTARTS   AGE
postgres-db     1/1     Running   0          14d
```

To get a list of all namespace’s pods, use the `all-namespaces` (or `-A`) flag:

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
Use the `exec` command to execute a command:

```shell
kubectl exec <pod> <command> # replace <pod> with the pod’s name and <command> with the command and its arguments
```

To learn more about the `exec` command, use the `--help` (or `-h`) flag:

```shell
kubectl exec --help
```

```shell
Execute a command in a container.

Examples:
  # Get output from running the 'date' command from pod mypod, using the first container by default
  kubectl exec mypod -- date

...

Options:
    -c, --container='':
	Container name. If omitted, use the kubectl.kubernetes.io/default-container annotation for selecting the
	container to be attached or the first container in the pod will be chosen

    -f, --filename=[]:
	to use to exec into the resource

    --pod-running-timeout=1m0s:
	The length of time (like 5s, 2m, or 3h, higher than zero) to wait until at least one pod is running

    -q, --quiet=false:
	Only print output from the remote session

    -i, --stdin=false:
	Pass stdin to the container

    -t, --tty=false:
	Stdin is a TTY

Usage:
  kubectl exec (POD | TYPE/NAME) [-c CONTAINER] [flags] -- COMMAND [args...] [options]

Use "kubectl options" for a list of global command-line options (applies to all commands).
```


## Create a Debug Session
Use the `debug` command to create a debug session:

```shell
kubectl debug <pod> --image=<image> # replace <pod> with the pod’s name and <image> with the image’s name
```

```shell
Defaulting debug container name to debugger-hbcf9.
```

## Learn More
- [Kubernetes Overview](https://kubernetes.io/docs/concepts/overview/)
- [Kubernetes CLI Cheatsheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [Kubernetes CLI Commands](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands)
