# Debug Operations in Kubernetes

Kubernetes contains several commands, sometimes we can use these commands to do things. A good command to know is kubectl get pods which is used to get a list of all pods that are available and what their status is. Just rememember that when you use this command tat you may have to specify the `namespace`.

```shell
kubectl get pods --namespace 
```

Speaking of commands, kubectl is the CLI that is used to interact with k8s. The kubectl cli commmunicates with the kubernettes API server.  Another command that is helpful is the kubectl logs command. In Azure, kubernetess is available, just like other cloud providers. This command is used to retrive the logs of a specific pod - do use this when you have to review logs or need to debug a container. Another we will dicuss is the `kubectl exec` command. A command that we can use to debug a container from the inside or to explore the the enviroment of the container itself.  I recommend when debugging you start with kubectl get pods, then `kubectl logs` and lastly we can use `kubectl exec` to explore the inside of the container and review other log files or configurations. 

**Note:** The command `kubectl debug` is another option to considering when debugging a container. This command can be used to create a clone of a pod that does not terminate if an error is experienced inside the container. 



# References

- https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#-strong-getting-started-strong-

- [What is Kubernetes](https://kubernetes.io/docs/concepts/overview/)
