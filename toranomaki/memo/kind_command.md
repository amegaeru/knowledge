## 1.Kind Cluster
|details|command|
|:--|:--|
|Create Kind Cluster|# kind create cluster --name=sample|
|Delete Kind Cluster|# kind delete cluster --name=sample|
|Verify Contexts|# kubectl config get-contexts|

## 2.Kubernetes Cluster
`#` `vi multi-nodeyaml`
```
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
- role: control-plane
- role: control-plane
- role: worker
- role: worker
```
##### Create Kubernetes Cluster
`#` `kind create cluster --config=multi-node.yaml`
