# What is Namespace in Kubernetes?
Namespaces are a way to organize clusters into virtual sub-clusters — they can be helpful when different teams or projects share a Kubernetes cluster. Any number of namespaces are supported within a cluster, each logically separated from others but with the ability to communicate with each other. 
- Namespaces cannot be nested within each other.
- Any resource that exists within Kubernetes exists either in the default namespace or a namespace that is created by the cluster operator.

## What is "default" namespace in Kubernetes?
Basically Kubernetes comes with 3 namespaces out of the box

1. **default**
2. **kube-system**
3. **kube-public**

```
$ kubectl get namespace
```

| NAME | STATUS | AGE |
|------------|-------------|------|
default      |      Active |   8m |
kube-public  |      Active |   8m |
kube-system  |      Active |   8m |
my-namespace |      Active |   3s |

## Why use Kubernetes namespaces?

There are many use cases for k8s namespaces:

- Allowing teams or projects to exist in their own virtual sub-clusters without fear of impacting each other’s work. 
- Enhancing role-based access controls (RBAC) by limiting users and processes to certain namespaces.
- Enabling the dividing of a cluster’s resources between multiple teams and users via resource quotas.


## How to create k8s namespace?
```
$ kubectl create <namespace_name>
```
or you can simply create a namespace using yaml file

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: development
```