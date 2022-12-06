# Deploy Applications with Kind

Kubernetes is a popular orchestration platform that is used by many organizations to deploy applications. We can use [kind](https://kind.sigs.k8s.io/) to gain practice with kubernetes. Let's deploy an application with kind to see how it works. Start by installing kind from https://kind.sigs.k8s.io/. Be aware that you will need to have Docker installed locally.

Start kind with the command `kind create cluster` and wait for the setup to complete.

```
$ kind create cluster
Creating cluster "kind" ...
 ✓ Ensuring node image (kindest/node:v1.25.3) 🖼
 ✓ Preparing nodes 📦
 ✓ Writing configuration 📜
 ✓ Starting control-plane 🕹️
 ✓ Installing CNI 🔌
 ✓ Installing StorageClass 💾
Set kubectl context to "kind-kind"
You can now use your cluster with:

kubectl cluster-info --context kind-kind

Have a nice day! 👋
```

You should check for connectivity with the Kubernete cluster and the Kubernetes API. A good way to test for connectivity to the cluster and the Kubernetes API is by using the CLI.

```
$ kubectl cluster-info --context kind-kind
```

You should see output that contains the control plane IP address and more. 

## Deploy Application

Create a file named **app.yaml** and insert the following configuration. 

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  creationTimestamp: null
  labels:
    app: web
  name: web
spec:
  replicas: 1
  selector:
    matchLabels:
      app: web
  strategy: {}
  template:
    metadata:
      creationTimestamp: null
      labels:
        app: web
    spec:
      containers:
      - image: gcr.io/google-samples/hello-app:1.0
        name: hello-app
        resources: {}
status: {}
---
apiVersion: v1
kind: Service
metadata:
  creationTimestamp: null
  labels:
    app: web
  name: web
spec:
  ports:
  - port: 8080
    protocol: TCP
    targetPort: 8080
  selector:
    app: web
  type: NodePort
status:
  loadBalancer: {}
```

The configuration file contains a *deployment* configuration and a *service*. We use the deployment to inform Kubernetes the desired state we want for the application. The application, *web*, also has a service definition that exposes the port of the local cluster node to its external Azure network. The exposed *nodePort* is how you will access the application.

Next, deploy the application.

```shell
$ kubectl apply -f app.yaml
```

Now that the application, web, is deployed we can access the application by exposing the nodePort through port forwarding. However, to port forward the container port the container name is required.

To get the container name, issue the following command:

```shell
$ PODNAME=$(kubectl get pods --template '{{range .items}}{{.metadata.name}}{{end}}' --selector=app=web)
```

Now that you have the container name, start the port forwarding with the container to expose the port to the local network.
```
$ kubectl port-forward $PODNAME 8080:8080
Forwarding from 127.0.0.1:8080 -> 8080
Forwarding from [::1]:8080 -> 8080
```

If you visit localhost:8080 you will see the Hello World welcome page.

# Next Steps

As mentioned before Kubernetes is an orchestration platform used to deploy containerized applications. We hope you now better understand how one can deploy applications to Kubernetes and AWS. 


