# Spectro Cloud Style Guide

Use the following style guide for all writing assignments.

### Simplified English

Use simple English in Spectro Cloud material unless explicitly stated otherwise in this guide. 
More importantly, simple language helps the reader retain information and more readily understand concepts. 

|   Good  ✅                                                          | Bad ❌                                                                   |
|--------------------------------------------------------------------------|----------------------------------------------------------------------------------|
| The core Kubernetes API is flexible and can also be extended to support custom resources. | The interior Kubernetes API is malleable and provides the capability for consumers to extended custom logic and inject custom logical resources. |
| Choose a node to be the cluster master node.                              | Designate a node to be the cluster master node.                                   |
| Drain the node before a version upgrade.                                  | It is essential to drain the node prior to a version upgrade.                     |  


### Present Tense

Users read documentation to perform tasks or gather information. For users, these activities take place in their present, so the present tense is proper in most cases. Additionally, the present tense is simpler to read than the past or future tense.

### Voice


Use the active voice whenever possible. The active voice is usually more direct and vigorous than the passive. When you write a sentence in the active voice, it is also usually shorter than in the passive voice.

Address the user when creating text content. Use the noun, you. Use, we, when providing the user with recommendations. We want to take ownership of our guidance, so avoid hiding using “it is recommended.”

| Good  ✅                                                              | Bad ❌                                                             |
|-------------------------------------------------------------------|-----------------------------------------------------------------|
| Use the kubectl cli to create a namespace titled “mgmt”.                                | The Kubectl CLI can be used to create namespaces titled “mgmt”                         |
| Prior to upgrading, ensure you have carefully reviewed the release notes for deprecation notices.                          | Release notes should be carefully verified for deprecation notices prior to an upgrade.                                         |
|We recommended deploying Palette Enterprise in a highly-available configuration of at least three nodes.                           | It is recommended to deploy Palette Enterprise in a highly-available configuration of at least three nodes.                          ||

### Ableist Language

Don't use ableist language. This avoids biases and harm when discussing disability and accessibility. Ableist language includes words or phrases such as crazy, insane, blind to or blind eye to, cripple, dumb, and others. This also includes action verbs with physical traits like jump and run. Choose alternative words depending on the context.

| Good  ✅                                                              | Bad ❌                                                             |
|-------------------------------------------------------------------|-----------------------------------------------------------------|
| Review all the active containers.                                 | See if all the containers are running.                           |
| Navigate to the tab titled, Settings.                             | Jump to the next tab.                                            |
| Issue the command kubectl get pods.                               | Run the command kubectl get pods.                                |


### Acronyms

Use title case when defining an acronym. Use the same rules that apply to headline styles. Some acronyms are in nature written in a camel case. Example: IaaS, kCh, SaaS.

Although some acronyms are widely understood and preferred to the spelt-out term, others are not well known or are familiar only to a specific group of customers. Define the acronym first.

The exception is when an acronym will appear only once in your content. Spell out the term. Don't introduce it in parentheses after the spelt-out version. If the spelt-out term and acronym are needed for metadata, then it is okay to use both.

| Good ✅               | Bad ❌                 |
|--------------------|----------------------|
| Boot the Virtual Machine (VM).   | Boot the virtual machine (VM).     |
| Boot all the Virtual Machines (VMs).   | Boot all the virtual machine (VMs).    |
| This is called Infrastructure as a Service (IaaS).   | This is called infrastructure as a service (IaaS).     |
| Dynamic-Link Library (DLL).   | dynamic-link library (DLL).     | 

### Gender

Use gender-neutral pronouns. Avoid the following nouns he, him, his, she, or her as gender-neutral pronouns. The same applies to he/she or other such punctuational approaches. Use the singular they.

### Headline Style

Use title case for headings.  If the heading is conceptual or non-task based, then start with a noun. Avoid using a noun that starts with an -ing.

| Good  ✅                                                              | Bad ❌                                                             |
|-------------------------------------------------------------------|-----------------------------------------------------------------|
| Deploy a Pack Registry Server.                                 | Deploying A Pack Registry Server.                           |
| Access Audit Logs.                             | Accessing audit logs                                           |
| Quick Start with Palette App Mode.                              | Quick start with Palette app mode                               |



### Command Output

Show the command output to help the reader follow along and validate they are receiving the expected output.



```shell
kind create cluster
```


```shell
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